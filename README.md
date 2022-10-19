# helmreleases-repro

## Steps taken

1. Install the most recent version of FluxV2.

```bash
brew install fluxcd/tap/flux
```

2. Generate Flux components manifests:

```bash
flux install \
    --version="v0.35.0" \
    --toleration-keys="workload,nodetaint/blocking" \
    --export > "./aws/sbox/cicd/1.22/flux-system/gotk-components.yaml"
```

3. Push updated manifests to remote repository.

4. Source reconciliation:

```bash
flux reconcile source git flux-system
```
