收集导航信息，预先知道操作是否会导致分裂或合并

导航信息包含从根节点一路下来的引用，用于反向回溯



推迟分裂，将元素转换到同级的另一个节点，腾出空间（如，两个节点和拆分成三个节点）



-   按页压缩数据
-   仅压缩数据
    -   按行
    -   按列
