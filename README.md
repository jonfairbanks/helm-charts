# Helm Charts

Helm charts published as public OCI artifacts in GitHub Container Registry.

## Rick

```sh
helm install rick oci://ghcr.io/jonfairbanks/charts/rick --version 2.0.0
```

Upgrade an existing release after reviewing the [Rick 2.0.0 breaking changes](#rick-200-breaking-changes):

```sh
helm upgrade rick oci://ghcr.io/jonfairbanks/charts/rick --version 2.0.0
```

## docker-node-app

```sh
helm install my-app oci://ghcr.io/jonfairbanks/charts/docker-node-app --version 3.0.1
```

The docker-node-app chart is maintained and published from
[jonfairbanks/docker-node-app](https://github.com/jonfairbanks/docker-node-app).

## Rick 2.0.0 breaking changes

- Kubernetes 1.25 or newer is required.
- The container now serves application traffic on port 8080 and health checks on port 9090. The Service remains on port 80.
- Ingress is disabled by default. Ingress paths now use `path` and `pathType` fields.
- Service-account creation and PodDisruptionBudget creation are disabled by default.
- The image defaults to the immutable digest for the upstream `1080p` image. Clear `image.digest` when overriding `image.tag`.

## Legacy repository retirement

The former GitHub Pages repository at `https://jonfairbanks.github.io/helm-charts`
has been retired. Historical packages were not migrated. OCI charts are installed
directly and do not use `helm repo add` or `helm repo update`.
