### 基于GCN的技术路线——ST-GCN++**

**2.1 GCN——Key Points**
（1）GCN以骨骼关键点序列作为输入，输入形状为T × V × C

​		T：序列长度

​		V：一个Skeleton里关键点的个数

​		C： 维度。2D或者3D。

​	（2）存在多个人时，GCN取所有人特征的平均作为特征，如图所示

!{Img}(https://github.com/Mrhahaa/Data-Mining/blob/94a6d410c9793bf639b9047a5370b7c2f42f5eba/22411d850e3509b32bf5bbf93b11497.png)

​	（3）GCN网络由多个GCN Block堆叠而成。类似于Bottleneck→ResNet。

​	**2.2 ST-GCN结构**
​	随着网络的加深，特征的通道数（C）不断加深，时序维度（T）上不断地降采样。

​	最后一层的输出会经过一个global average pooling得到输出特征。

​	最后，经过线性层分类器，得到分类结果。

![image-20240426210222194](assets/image-20240426210222194.png)

- 关于GCN Block的设计
