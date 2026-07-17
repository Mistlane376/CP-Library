# LIS最长递增子序列

$O(n \log n)$ 优化版本：

```cpp
vector<int> LIS;
for (int i = 1; i <= n; i++) {
    auto idx = lower_bound(LIS.begin(), LIS.end(), a[i]);
    if (idx == LIS.end()) {
        LIS.push_back(a[i]);
    } else {
        *idx = a[i];
    }
}
cout << LIS.size() << endl;
```

**算法说明**：
- 使用贪心 + 二分法
- `LIS[i]` 表示长度为 i+1 的递增子序列的最小末尾值
- 时间复杂度：O(n log n)
- 只能求长度，不能直接求出具体序列

**求具体序列**：需要额外记录前驱节点

**变体**：
- 最长递减子序列（LDS）：改为从大到小比较
- 最长非降子序列：`lower_bound` 改为 `upper_bound`
