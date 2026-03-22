# Concilium-CD

Kustomize deployment manifests for [Concilium](https://github.com/KofTwentyTwo/Concilium).

## Structure

```
base/           -- Base K8s manifests (deployment, service, ingress, postgres, minio)
overlays/
  dev/          -- Dev environment overlay
  staging/      -- Staging (future)
  production/   -- Production (future)
```

## How it works

Munitor CI pushes image tags to this repo. ArgoCD (via the app-of-apps pattern in k8s-app-of-apps) syncs the manifests to the cluster.

## Images

| Image | Purpose |
|---|---|
| `ghcr.io/koftwentytwo/concilium` | Backend (QQQ + Javalin) |
| `ghcr.io/koftwentytwo/concilium-migrations` | Liquibase database migrations |