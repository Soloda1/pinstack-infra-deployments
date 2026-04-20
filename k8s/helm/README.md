# Helm structure for pinstack

This folder contains Helm charts and environment values for local and future deployments.

## Layout

- `charts/` - individual service charts
- `environments/dev/` - values for local kind
- `environments/stage/` - values for stage
- `environments/prod/` - values for prod
- `scripts/create-charts.sh` - idempotent chart scaffold generator

## Generate base charts

```bash
cd /home/solo/GolandProjects/pinstack-infra-deployments
./k8s/helm/scripts/create-charts.sh
```

## Install one chart (example)

```bash
helm upgrade --install user-db ./k8s/helm/charts/user-postgres -n pinstack --create-namespace
```

## Render templates only (example)

```bash
helm template user-db ./k8s/helm/charts/user-postgres -n pinstack
```

