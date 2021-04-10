# Chapter02

This is demo codes about Blue/Green Deployment using Argo Rollouts.

## Usage

### Install

```bash
$ kubectl apply -f argocd-config.yml
```

add following IP & Host with your `/etc/hosts`

```
<IP of LB> blue-green-preview.dev.argoproj.io
<IP of LB> blue-green.dev.argoproj.io
```

### Change Container Image

```bash
$ kubectl argo rollouts set image bluegreen-demo bluegreen-demo=argoproj/rollouts-demo:green
```

### Promote

```bash
$ kubectl argo rollouts promote bluegreen-demo
```

### Watch progress

```bash
$ kubectl argo rollouts get rollout bluegreen-demo --watch
```
