# helm-starters

> helm charts基础模板

## 1、安装Helm

- [如何安装](https://helm.sh/zh/docs/intro/install/)

在Windows下，下载helm二进制文件，并添加至环境变量PATH

```bash
$ helm version
version.BuildInfo{Version:"v3.6.0", GitCommit:"7f2df6467771a75f5646b7f12afb408590ed1755", GitTreeState:"clean", GoVersion:"go1.16.3"}
```

## 2、clone本项目至`$USER_HOME/AppData/Roaming/starters`

> 例如我的是`C:\Users\gcdd1993\AppData\Roaming\helm\starters\dockerize-svc`目录

```bash
$ cd C:\Users\gcdd1993\AppData\Roaming\helm
$ git clone git@github.com:gcdd1993/helm-starters.git starters
$ ls
repositories.lock  repositories.yaml  starters/
```

## 3、新建`helm-charts`

```bash
$ helm --starter dockerize-svc create your-helm-charts
```

## 4、打包`helm-charts`

> 建议在helm-charts同级目录新建packages，以存放打包后的*.tgz文件

```bash
$ ls 
charts/my-helm-charts
$ mkdir ../packages && cd ../packages
$ helm package ../charts/my-helm-charts
```

## 5、生成`index.yaml`

> index.yaml文件作为helm-charts的入口文件，记录了本仓库可以提供的helm-charts索引信息

```bash
$ cd packages
$ helm repo index .
$ ls 
my-helm-charts-0.0.1.tgz
...
```

# 其他

- [Spring Cloud Kubernetes 改造心路]()

