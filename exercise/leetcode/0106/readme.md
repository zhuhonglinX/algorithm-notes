
从二叉树的中序遍历和后序遍历序列中还原二叉树

采用递归建树的方式，后续遍历的最后一个元素即二叉树的根的值，于是在中序遍历中找到这个值，该值的左边就是所有左子树的中序遍历序列，右边就是右子树的中序遍历序列，于是递归求左子树的根节点和右子树的根节点。

Solution 采用这一思路，但是在中序遍历序列中找根节点这一步操作用的是顺序遍历，因此复杂度为 $O(n)$ ，整体的时间复杂度为 $ O(n^2) $ 。

Solution2 进行改进，首先遍历中序序列，建立 hashmap，key 为节点值，value 为该值在中序遍历序列中的位置，这样后续查找根节点可以以 $O(1)$ 的复杂度实现，因此整体的时间复杂度下降到 $O(n)$。
