# KMP算法

**核心作用**：字符串查找（在文本中查找模式串）

**核心思想**：保证文本串的指针永不回溯，利用已经匹配成功的部分信息，跳过绝不可能匹配成功的中间位置。

## 四大作用

| 作用 | 说明 | 对应函数 |
|------|------|----------|
| 精准定位 | 返回模式串在文本中所有出现位置 | `searchAll()` |
| 重叠计数 | 统计重叠出现的次数 | `countOccurrences()` |
| 最长前缀匹配 | 计算文本与模式串的最长匹配长度 | `longestPrefixMatch()` |
| 寻找循环节 | 判断字符串是否由重复子串组成 | 利用前缀函数 |

## C++ KMP通用模板

```cpp
#include <bits/stdc++.h>
using namespace std;

class KMP {
private:
    string pattern;
    vector<int> pi;  // 前缀函数数组
    int m;

    // 构建前缀函数
    void buildPrefix() {
        pi.resize(m);
        int j = 0;
        for (int i = 1; i < m; ++i) {
            while (j && pattern[i] != pattern[j]) {
                j = pi[j - 1];
            }
            if (pattern[i] == pattern[j]) ++j;
            pi[i] = j;
        }
    }

public:
    KMP(const string& p) : pattern(p), m(p.size()) {
        if (m > 0) buildPrefix();
    }

    // 返回所有匹配的起始下标
    vector<int> searchAll(const string& text) const {
        vector<int> positions;
        if (m == 0) return positions;

        int j = 0;
        for (int i = 0; i < (int)text.size(); ++i) {
            while (j > 0 && text[i] != pattern[j]) {
                j = pi[j - 1];
            }
            if (text[i] == pattern[j]) ++j;
            if (j == m) {
                positions.push_back(i - m + 1);
                j = pi[j - 1];  // 支持重叠匹配
            }
        }
        return positions;
    }

    // 统计匹配次数
    int countOccurrences(const string& text) const {
        return (int)searchAll(text).size();
    }

    // 最长前缀匹配
    int longestPrefixMatch(const string& text) const {
        if (m == 0) return 0;
        int j = 0, res = 0;

        for (char c : text) {
            while (j > 0 && c != pattern[j]) {
                j = pi[j - 1];
            }
            if (c == pattern[j]) {
                ++j;
                res = max(res, j);
                if (j == m) j = pi[j - 1];
            }
        }
        return res;
    }
};
```

**算法说明**：
- `pi[i]`：模式串前 i+1 个字符的最长相等前后缀长度
- `buildPrefix()`：构建前缀函数数组
- 时间复杂度：O(m) 构建，O(n) 匹配

**使用示例**：
```cpp
KMP kmp(pattern);
auto positions = kmp.searchAll(text);  // 获取所有匹配位置
int count = kmp.countOccurrences(text);  // 统计匹配次数
int prefixLen = kmp.longestPrefixMatch(text);  // 最长前缀匹配
```
