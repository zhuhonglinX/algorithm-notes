题目要求利用常数空间
第一种做法利用常数空间，但是时间复杂度达到 $O(n^2)$。

第二种做法使用常数空间，时间复杂度 $O(n)$：

利用已经建立的 next 作为队列，从而完成常数空间，线性遍历。

父节点建立子节点的 next，即在遍历 level 层的时候，建立 level + 1 层的 next。下一步遍历 level + 1 层，建立 level + 2 层的 next。每一层的遍历通过上一层建立的 next 来完成。