# GCD与LCM

## 最大公约数（GCD）

```cpp
int gcd(int a, int b) {
    return b ? gcd(b, a % b) : a;
}

// 迭代版本
int gcd(int a, int b) {
    while (b) {
        int t = a % b;
        a = b;
        b = t;
    }
    return a;
}

// C++17 标准库版本
#include <numeric>
int g = std::gcd(a, b);
```

## 最小公倍数（LCM）

```cpp
int lcm(int a, int b) {
    return a / gcd(a, b) * b;
}

// C++17 标准库版本
#include <numeric>
int l = std::lcm(a, b);
```

## GCD性质

$$\gcd(a+c, b+c) = \gcd(a+c, b-a)$$

**性质解释**：
对于任意整数 $x, y$，有：
$$\gcd(x, y) = \gcd(x, y-x)$$

这是因为 $\gcd(x, y)$ 整除 $x$ 和 $y$，所以也整除 $y-x$；反过来，任何整除 $x$ 和 $y-x$ 的数也能整除 $x + (y-x) = y$。因此两个数对的公约数集合完全相同。

**常见应用**：
1. **欧几里得算法（辗转相除法）**：不断用大数减小数（或取模）
2. **化简GCD问题**：当两个数同时加上同一个数 $c$ 时，它们的差保持不变
3. **求解线性丢番图方程**：若 $\gcd(a, b) = d$，则存在整数 $x, y$ 使 $ax + by = d$
4. **判断互质**：若 $|a-b| = 1$，则两数一定互质
