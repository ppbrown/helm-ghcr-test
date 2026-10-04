# ghcr-test

Helm chart for [ppbrown/ghcr-test](https://github.com/ppbrown/ghcr-test), a tiny
`python3 -m http.server` image used to test image loaders/registries.

## Install

```
helm install ghcr-test . --set image.tag=main-<run_id>
```

No `latest` tag is published (tags are `main-<run_id>` / `staging-<run_id>`
per the source repo's GitHub Actions workflow), so `image.tag` must be set.

## Values

| Key | Description | Default |
| --- | --- | --- |
| `image.repository` | Image repository | `ghcr.io/ppbrown/ghcr-test` |
| `image.tag` | Image tag (required) | `""` |
| `image.pullPolicy` | Image pull policy | `IfNotPresent` |
| `customContent` | Text injected into the served page via `CUSTOM_CONTENT` | `""` |
| `service.type` | Service type | `ClusterIP` |
| `service.port` | Service port | `8080` |
| `replicaCount` | Number of replicas | `1` |
