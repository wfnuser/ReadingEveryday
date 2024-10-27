以太坊 挖矿算法

核心思想是：不能像比特币一样，主要进行哈希运算。比特币也不是取了一次哈希，是取了两次。但是不够，要增强对内存访问的需求。要设计一个对asic芯片不友好的，让普通计算机能够参与的。就要设计的任务更像是普通计算机做的，而不像挖矿专用的asic芯片做的。普通计算机内存很大，还有其他的特性。利用这个特性，设计这个puzzle对这个需求特别像是普通计算机对资源的配对比例。

这个puzzle好的地方，对矿工来说挖矿是memory hard。坏的地方，对轻节点也是memory hard。设计puzzle的原则是：difficult to solve, but easy to verify。求解puzzle很难，验证puzzle很容易。但是验证和求解的区域几乎一样大。验证也要保存数组，否则计算复杂度很高。对于litecoin而言，不是问题，它没有轻节点验证的问题。但对我们这个场景而言，是不行的。这样造成的结果是，litecoin真正使用的时候，内存区域不敢设置太大。对于计算机1G不大，手机就太大了。实际使用的时候，数组只有128K，非常小。连1M都不到，就是为了照顾轻节点。