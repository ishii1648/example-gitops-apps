# Chapter02

This is demo codes about Blue/Green Deployment using Argo Rollouts.

## Demo

## Usage

### Install

```bash
$ kubectl apply -f argocd-config.yml
```

add following IP & Host with your `/etc/hosts`

```
35.236.164.44 blue-green-preview.dev.argoproj.io
35.236.164.44 blue-green.dev.argoproj.io
```

### Change Container Image

```bash
$ kubectl argo rollouts set image bluegreen-demo bluegreen-demo=argoproj/rollouts-demo:green
```

### Promote

```bash
$ kubectl argo rollouts promote bluegreen-demo
```
