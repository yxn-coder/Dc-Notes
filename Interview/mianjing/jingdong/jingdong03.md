## 京东一，二面面经，许愿offer！！！
- [原文](https://www.nowcoder.com/discuss/419687)

### hashmap数据结构
#### put
**1.7**
直接上图：
![hashmap-put-1.7](http://media.dreamcat.ink/uPic/hashmap-put-1.7.png)
**1.8**
直接上图：
![hashmap-put-1.8](http://media.dreamcat.ink/uPic/hashmap-put-1.8.png)

#### 100个结点，hashmap初始容量多少合适？
> Map在使用过程中不断的往里面存放数据，当数量达到了16 * 0.75 = 12就需要将当前16的容量进行扩容，而扩容这个过程涉及到rehash（重新哈希）、复制数据等操作，所有非常消耗性能。

#### 为什么1.8要引入红黑树，红黑树是平衡树吗？
- 当 Hash 冲突严重时，在桶上形成的链表会变的越来越长，这样在查询时的效率就会越来越低；时间复杂度为 O(N)。
- 是

#### 红黑树为什么要分红节点和黑节点？
> 红黑树的查询性能略微逊色于AVL树，因为他比avl树会稍微不平衡最多一层，也就是说红黑树的查询性能只比相同内容的avl树最多多一次比较，但是，红黑树在插入和删除上完爆avl树，avl树每次插入删除会进行大量的平衡度计算，而红黑树为了维持红黑性质所做的红黑变换和旋转的开销，相较于avl树为了维持平衡的开销要小得多

### JVM的内存模型
1.8之前：
![JVM内存模型-1.8之前](http://media.dreamcat.ink/uPic/JVM内存模型-1.8之前.png)

1.8:
![JVM内存模型-1.8](http://media.dreamcat.ink/uPic/JVM内存模型-1.8.png)