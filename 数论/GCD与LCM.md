# GCD与LCM

## 最大公约数（GCD）

```cpp
int gcd(int a, int b) {
    return b ? gcd(b, a % b) : a;
}
```

## 最小公倍数（LCM）

```cpp
int lcm(int a, int b) {
    return a / gcd(a, b) * b;
}
```
