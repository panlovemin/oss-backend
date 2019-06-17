# 对象数据管理

## 数据清理程序
- 所有的删除对象操作，均只删除引用，以及减少引用计数，真实的数据删除，由定时清理程序完成
> 这里可以考虑设计一个回收站功能，删除后，将引用关系 移动到 回收站表，N天后自动删除,精确到天的23:59:59,N 天之前可以选择恢复 （N = 7 day）

##  数据分布存储
> 目前仅仅实现单机环境

- 如何将数据分片分别存储到不同服务器？

- 考虑机器增加，减少情况下，系统仍具有稳定性，可用性

- 考虑网络异常下，数据分片的丢失处理，每一个分片存储都要收到确切的成功应答

## 大文件上传下载

分片上传，断点续传

