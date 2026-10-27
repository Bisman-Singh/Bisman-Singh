DevOps Engineer. Most of what I do comes down to finding the place where a system said it worked and didn't.

That tends to mean Kubernetes platforms, the CI library everything ships through, GitOps, and monitoring that admits when it has gone blind instead of sitting there green.

#### Things I maintain

[**Pipeline DORA Metrics**](https://plugins.jenkins.io/pipeline-dora-metrics/) is an official Jenkins plugin, hosted in the `jenkinsci` org. It works out deployment frequency, lead time, change failure rate and time to restore from a controller's own build history, so you get the four metrics without wiring up anything new. [Source](https://github.com/jenkinsci/pipeline-dora-metrics-plugin)

[**zeroreads**](https://github.com/Bisman-Singh/zeroreads) finds the log lines nothing ever queries, alerts on or puts on a dashboard. It proves it rule by rule with a witness line rather than asking you to trust it, then writes the Collector, Vector or Fluent Bit config that cuts them.

[**helm-blame**](https://github.com/Bisman-Singh/helm-blame) is `git blame` for Helm values. For any value in a release it tells you which file, subchart or `--set` won, and what got shadowed on the way.

[**kubectl-timeline**](https://github.com/Bisman-Singh/kubectl-timeline) rebuilds what happened during an incident from live cluster state. It sorts findings into confidence buckets instead of inventing a probability, which is more than most tools will own up to.

[**Helm Chart Builder**](https://helm.bisman.org) and [**Compose Builder**](https://compose.bisman.org) are visual editors for charts and compose files, for when a YAML tree is easier to reason about as a diagram.

#### Merged upstream

- [**K8sGPT**](https://github.com/k8sgpt-ai/k8sgpt/pull/1761) gained a `--resource` flag so you can analyse one resource instead of the whole cluster. The name predicate goes into the API server's list options rather than filtering a wide result set after the fact.
- [**Argo CD**](https://github.com/argoproj/argo-cd/pull/27809) stopped failing on HPA v2 to v1 conversion inside structured merge diff.
- [**Argo CD**](https://github.com/argoproj/argo-cd/pull/29469) stopped leaving a sync hook finalizer behind when the live object is already gone, which left resources stuck.
- [**krew**](https://github.com/kubernetes-sigs/krew/pull/909) got its Actions pinned to commit SHAs. It hardened the supply chain and happened to unblock repo CI that had been red for every contributor.
- [**chart-testing-action**](https://github.com/helm/chart-testing-action/pull/208) can now take a custom yamllint config.
- [**kind-action**](https://github.com/helm/kind-action/pull/160) now actually passes the registry port through to the container.
- Tests for paths nobody had covered in [Argo CD](https://github.com/argoproj/argo-cd/pull/29470) and [K8sGPT](https://github.com/k8sgpt-ai/k8sgpt/pull/1769).

#### Elsewhere

[**Wick**](https://play.google.com/store/apps/details?id=org.bisman.wick) is a puzzle game on Google Play. It asks for no network permission at all, which turned out to be the hardest part.

[bisman.org](https://bisman.org) · [LinkedIn](https://in.linkedin.com/in/bisman-singh-b758b91b9)
