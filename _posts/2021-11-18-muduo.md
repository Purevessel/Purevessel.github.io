##c++多线程##
作者认为：C/C++无法高效地辨认一个指针是否合法是指针问题的根源。Java可以凭借垃圾回收机制中是否有GC Root引用(即reference不为NULL)来判断，而C/C++由于对象如果已经释放，那么该地址空间就不能访问了，这时显然无法判断对象的状态。(因为有可能该地址上又创建了新对象，而且还可能和原对象不一样)

##插曲：快速学习语言涉及的方面##
[https://blog.csdn.net/myan/article/details/3144661](https://blog.csdn.net/myan/article/details/3144661 "语言的快速学习")