# MaaResourcesSync

适用于Windows平台的Maa资源增量更新脚本，基于 Git `SSH Fetch` 方案。  

[MaaResources镜像仓库](https://github.com/LaviniaFalcone/MaaResourceMirror) | [下载地址](https://github.com/LaviniaFalcone/MaaResourceSync/releases)

## 常见问题

### 这个东西有什么用
> 用于更新 `Maa` 自动战斗等功能所需的资源等。

### 如何使用 
> 解压到 `Maa` 所在目录，运行 `sync.bat` 即可更新资源。


### 资源下载速度慢
> 如果实在是太慢（`≤100KB/s`）可以试试关掉脚本重新打开。

### 其它问题
> 请提交 [Issue](https://github.com/LaviniaFalcone/MaaResourceSync/issues)

## 如何修改更新源
如果你想让MRS从自己的仓库拉取更新，需要自己生成一个公钥添加到自己仓库的 `Deploy keys` 列表中，然后将 `sync.bat` 中的：
```shell
git remote add mirror git@github.com:LaviniaFalcone/MaaResourceMirror
```
更改为：
```shell
git remote add mirror git@github.com:你的用户名/你的仓库
```
