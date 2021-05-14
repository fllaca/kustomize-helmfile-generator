# HelmfileGenerator plugin for Kustomize

Simplest proof of concept of combining [Helmfile](https://github.com/roboll/helmfile) and [Kustomize](https://kubectl.docs.kubernetes.io/guides/introduction/kustomize/) to manage K8s configuration

## Example usage

Generate resources:

```
PLUGIN_ROOT=$HOME/.config/kustomize/plugin kustomize build --enable_alpha_plugins
```

Apply resources:

```
PLUGIN_ROOT=$HOME/.config/kustomize/plugin kustomize build --enable_alpha_plugins   | kubectl apply -f -
```

## Limitations

* HelmfileGenerator plugin uses `helmfile template` to generate Kubernetes resources, so no Helm hooks nor Helmfile hooks can be used

## Future work

* Add parameters to HelmfileGenerator to provide extra flags to `helmfile` command
