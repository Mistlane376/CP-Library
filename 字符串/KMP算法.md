# KMP算法

```cpp
class KMP {
private:
    string pattern;
    vector<int> pi;
    int m;

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
};
```

**算法说明**：
- `pi[i]`：模式串前 i+1 个字符的最长相等前后缀长度
- `buildPrefix()`：构建前缀函数数组
- 时间复杂度：O(m) 构建，O(n) 匹配

**使用示例**：
```cpp
KMP kmp(pattern);
// kmp.pi 存储前缀函数
// 用于字符串匹配、模式查找等
```
