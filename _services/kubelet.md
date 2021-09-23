---
title: "Containerized Kubelet"
date: 2018-11-18T12:33:46+10:00
featured: true
weight: 1
---

Containerized kubelet for embedded Linux.


This project aims to build multi-arch `kubelet` images and help get rid of dependencies to the local filesystem,
especially for custom or embedded Linux distros. 

It also tries to optimize on image size to work on devices that have limited storage capacity.
Unlike k3s, it doesn't compress dependencies into binaries and extract them after installing.
It tries to identify necessary components in different scenarios and provide just the required binaries.
Users can pull images that just match their requirements.
It also compresses non-daemon binaries via upx, such as cni-plugins, crictl, and kubeadm,
those binaries will be only extracted in executing. 

All images are based on alpine:3.13 with CGO enabled. 
They are available on [cloudtogo4edge/kubelet](https://hub.docker.com/r/cloudtogo4edge/kubelet).

We also provide a multi-arch kube-proxy image based on alpine3.13. Its size is less than half of the size of the official one.
It is available on [cloudtogo4edge/kube-proxy](https://hub.docker.com/r/cloudtogo4edge/kube-proxy).

[More](https://github.com/cloudtogo/containerized-kubelet)
