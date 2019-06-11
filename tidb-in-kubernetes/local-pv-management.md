---
title: 本地 PV 管理
category: how-to
---

# 本地 PV 管理

TiDB 是高可用数据库，存储层 TiKV 会对数据进行复制，容忍节点不可用。TiKV 使用高
IOPS、吞吐量的本地存储，比如 Local SSDs 时，可提高数据库性能。

Kubernetes 当前支持静态分配的本地存储。可使用
[local-static-provisioner](https://github.com/kubernetes-sigs/sig-storage-local-static-provisioner) 项目中的
local-volume-provisioner 程序创建本地存储对象。流程如下：

- 参考[操作文档](https://github.com/kubernetes-sigs/sig-storage-local-static-provisioner/blob/master/docs/operations.md)在集群节点预分配本地存储
- 参考[部署例子](https://github.com/kubernetes-sigs/sig-storage-local-static-provisioner/tree/master/helm)部署 local-volume-provisioner 程序

更多可了解 [Kubernetes 本地存储](https://kubernetes.io/docs/concepts/storage/volumes/#local) 和 [local-static-provisioner 文档](https://github.com/kubernetes-sigs/sig-storage-local-static-provisioner#overview)。
