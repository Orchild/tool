# **Jenkins slave tool** 

## python

各个工具基础python环境

```shell
docker build -t jenkins-slave/python .
```

## tscancode

依赖于基础python环境镜像

```shell
docker build -t jenkins-slave/tscancode .
```

## cloc

依赖于基础python环境镜像

```shell
docker build -t jenkins-slave/cloc .
```

## eslint

依赖于基础python环境镜像

```shell
docker build -t jenkins-slave/eslint .
```