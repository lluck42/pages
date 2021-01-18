---
title: "kubeadm config image 阿里云镜像"
date: 2019-01-17T17:11:04+08:00
draft: false
---


这个脚本无意中看到了，要和 ```kubeadm config image list``` 配合使用
用于 kubeadm 的阿里云镜像下载，还是挺重要的
```
images=(
    kube-apiserver:v1.13.2
    kube-controller-manager:v1.13.2
    kube-scheduler:v1.13.2
    kube-proxy:v1.13.2
    pause:3.1
    etcd:3.2.24
    coredns:1.2.6
)
for imageName in ${images[@]} ; do
    docker pull registry.cn-hangzhou.aliyuncs.com/google_containers/${imageName}
    docker tag registry.cn-hangzhou.aliyuncs.com/google_containers/${image} k8s.gcr.io/${imageName}
    docker rmi registry.cn-hangzhou.aliyuncs.com/google_containers/${imageName}
done
```