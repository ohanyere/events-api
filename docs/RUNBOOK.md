# Runbook

## Service

- Name: `events-api`
- Team: `Platform Engineering`
- Owner: `mooref068@gmail.com`
- Cost center: `platform-engineering`

## First Checks

```bash
kubectl get rollout events-api -n events-api-dev
kubectl get pods -l app.kubernetes.io/name=events-api -n events-api-dev
kubectl logs -l app.kubernetes.io/name=events-api -n events-api-dev
```

## Health

```bash
curl https://events-api.dev.platform.ohanyere.internal/healthz
curl https://events-api.dev.platform.ohanyere.internal/readyz
curl https://events-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo events-api -n events-api-dev
```

Escalate to `Platform Engineering` through `mooref068@gmail.com` if rollback does not restore service.
