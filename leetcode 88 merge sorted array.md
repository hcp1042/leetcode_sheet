起初想法，从左到右，十分困难

原因：
1）从左到右需要频繁插入，然后指针需要移位
2） 不知道何时停止


好的思路：因为nums1 后面有充足的空间，并且存储的都是0或无意义字符，所以从后往前可以大幅度简化问题，同时检查过的值可以不用操心
