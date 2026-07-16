# CP-Library 快速开始

欢迎使用 CP-Library！这是一个面向 C++ 竞赛与算法学习的模板合集。

## 📂 项目结构

```
CP-Library/
├── README.md              # 项目说明
├── CONTRIBUTING.md        # 贡献指南
├── LICENSE                # MIT 许可证
├── SUMMARY.md            # 完整目录索引
├── QUICKSTART.md         # 本文件
│
├── 基础工具/             # 常用库、函数、基础算法
├── 数论/                 # 素数、GCD、快速幂等
├── 图论/                 # 最短路、连通性、匹配等
├── 字符串/               # KMP、哈希等
├── 数据结构/             # 线段树、树状数组等
├── 动态规划/             # LIS、背包问题等
└── 杂项/                 # 高精度、位运算等
```

## 🎯 如何使用

### 方法 1：在线浏览（推荐）

直接在 GitHub 上浏览各个文件夹，点击对应的 `.md` 文件即可查看模板代码，一键复制使用。

### 方法 2：本地查看

1. 克隆仓库：
   ```bash
   git clone https://github.com/你的用户名/CP-Library.git
   cd CP-Library
   ```

2. 使用任意 Markdown 编辑器（如 VS Code）打开查看

### 方法 3：快速定位

使用 `SUMMARY.md` 快速定位所需模板，或使用 README 中的目录链接。

## 💡 使用建议

### 1. 建立个人模板库

建议将常用的模板保存到自己的模板文件中，这样在比赛中可以快速调用：

```cpp
#include <bits/stdc++.h>
using namespace std;

// 在这里添加你常用的模板代码

int main() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);

    // 你的代码

    return 0;
}
```

### 2. 理解而非死记

每个模板都要理解其原理和适用场景，不要盲目复制。建议：

- 自己实现一遍
- 理解时间复杂度和空间复杂度
- 知道什么情况下使用

### 3. 根据题目调整

模板是通用的，需要根据题目要求调整：

- 数组大小是否足够
- 模数是否正确
- 输入输出格式是否符合

## 📝 常用模板速查

### 最常用的几个

1. **快速幂** - 处理大数幂运算
2. **线段树** - 区间查询与修改
3. **并查集** - 处理连通性问题
4. **KMP** - 字符串匹配
5. **背包问题** - 动态规划经典

### 推荐的学习顺序

1. **基础工具** → 掌握常用函数和基础算法
2. **数论** → 理解质数、GCD、快速幂等基础概念
3. **数据结构** → 学习常用数据结构
4. **图论** → 掌握图的基本算法
5. **动态规划** → 学习 DP 思想和经典模型
6. **字符串** → 学习字符串匹配算法
7. **杂项** → 了解特殊技巧

## 🔍 搜索技巧

在 GitHub 仓库中可以使用搜索功能：

- 按文件名搜索：`filename:KMP`
- 按内容搜索：`线段树`
- 按语言搜索：`language:markdown`

## 📚 学习资源

### 推荐书籍

- 《算法竞赛入门经典》（刘汝佳）
- 《算法竞赛进阶指南》（李煜东）
- 《算法导论》（CLRS）

### 在线平台

- [Codeforces](https://codeforces.com/) -  contests, blog
- [Luogu](https://www.luogu.com.cn/) - 题库
- [AtCoder](https://atcoder.jp/) - 比赛
- [LeetCode](https://leetcode.com/) - 练习

### 其他优质仓库

- [OI-wiki](https://oi-wiki.org/) - 算法知识库
- [ competitive-programming-resources](https://github.com/lnishan/competitive-programming-resources)

## 🤝 贡献

发现错误或有更好的模板？欢迎提交 Pull Request！

详见 [CONTRIBUTING.md](CONTRIBUTING.md)

## 📄 许可证

MIT License - 详见 [LICENSE](LICENSE)

---

**祝你刷题愉快，RP 爆发！** 🎉🏆
