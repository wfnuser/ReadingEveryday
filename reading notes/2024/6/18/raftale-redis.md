redis性能优化：
1. 不使用复杂度较高(O(N)以上)的命令
2. 避免bigkey
3. 避免集中过期导致缓存雪崩
4. 内存到达上限：实例拆分
5. fork耗时严重：控制redis实例的内存小于10G；合理配置数据持久化策略
6. 避免开启内存大页：写时复制耗时。
7. SSD
8. 避免使用Swap
9. 合适设置内存碎片整理
10. 避免网络宽带过载
11. 避免短链接
12. 监控要做好
