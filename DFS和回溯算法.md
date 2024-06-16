# DFS和回溯算法

## 1 DFS
DFS常用在树或者图结构遍历上。网格是比树结构稍复杂的结构，下面以岛屿问题为例进行讲述网格问题的DFS解法，比如
- [200. 岛屿数量 （Easy）](https://leetcode.cn/problems/number-of-islands/)
- [463. 岛屿的周长 （Easy）](https://leetcode-cn.com/problems/island-perimeter/)
- [695. 岛屿的最大面积 （Medium）](https://leetcode.cn/problems/max-area-of-island/description/)
- [827. 最大人工岛 （Hard）](https://leetcode.cn/problems/making-a-large-island/)

### 1.1 DFS的基本结构
以二叉树为例，说明DFS基本结构

```C++
void Dfs(TreeNode root)
{
    //判断base case
    if (root == NULL)
    {
        return;
    }

    //访问两个叶子节点：左叶子节点、右叶子节点
    Dfs(root.left);
    Dfs(root.right);
}
```

可以看出，DFS两个要点：**[访问相邻节点]** 和 **[判断bad case]**
第一个要点是**访问相邻节点**。二叉树比较简单，只有两个叶子节点。同时二叉树自身就是一个递归结构，二叉树的叶子接地那也是一颗二叉树。
第二个要点是**判断bad case**。可以理解为“先污染后治理”，即先调用了Dfs接口后，再判断root是否为空，为空即返回。

### 1.2 网格问题基本概念
网格是由m*n个小方格组成的一个网络，每个小方格与其**上下左右**相邻,需要在这样的网格上进行搜索。
岛屿问题就是网格问题的一种，每个格子中的数字可能0或者1。0视作海洋格子，1视作陆地格子，这样相邻的陆地格子就连接成了一个岛屿
![网格说明](https://github.com/superman1122/leetcode/blob/main/IMG/%E7%BD%91%E6%A0%BC.png)
在这样的设定下就出现了各种岛屿问题，包括面积、周长、数量等，都可以用DFS来解决。

### 1.3 网格问题的DFS结构
网格结构比二叉树复杂一些，其实是一种简化版的图结构。通过类比二叉树的DFS结构来推导网格的DFS结构
第一个要点，网格的相邻节点是上、下、左、右四个，对(r,c)格子类说，相邻格子即(r-1,c)、(r+1,c)、(r,c-1)、(r,c+1)四个格子

第二个要点，类比叶子节点的左右节点为空，网格遍历的base case即为相邻格子超过网格范围，即数组越界，同样会“陷入玩后治理”
















参考https://leetcode.cn/problems/number-of-islands/solutions/211211/dao-yu-lei-wen-ti-de-tong-yong-jie-fa-dfs-bian-li-/

https://github.com/Rancho86/leetcode/blob/master/DFS%E5%92%8C%E5%9B%9E%E6%BA%AF%E7%AE%97%E6%B3%95%E5%8C%BA%E5%88%AB.md
