模拟

从左往右遍历 rains 数组，用一个 map 记录湖下雨的日子，湖编号为 key，下雨的日子为 value。遇到 0 时，用 set 记录不下雨的日子。当某个湖下雨且发现 map 中已经有记录（之前下过雨），那么必须从不下雨的日子里面选一天排干该湖，前提条件时之前下雨的日子在不下雨的日子的前面，如下：

```
[1, 0, 1] -> 可以
[0, 1, 1] -> 不可以，不下雨的日子在 1 号湖第一次下雨前
```

set 记录不下雨的日子频繁面临两个操作，插入和查找，因此使用平衡二叉搜索树，单次插入和查找达到 $O(logn)$，整体的时间复杂度 $O(nlogn)$

c++ 中的集合利用红黑树实现，可以达到这个要求，但在 python 中没有内置实现，所以我使用 list 充当 set，这样时间复杂度达到 $O(n)$，整体达到 $O(n^2)$

