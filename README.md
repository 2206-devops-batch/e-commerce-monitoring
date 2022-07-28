# e-commerce-monitoring

Repo to test monitoring practies on Kubernetes cluster

## Steps to install on kubernetes cluster

- Have `kubectl` installed and pointing to the correct cluster.
- Also requires `helm`, `curl`, and `envsubst` on `local systems`.
- The `cluster` must also have `tiller` and `docker` installed.
  - These are all installed into the `'default' namespace`,
  - though this can be changed with a simple `'ctrl + H'` to
  - whichever namespace you prefer.

1. Create metrics agent configmap.

   > grafana-agent_configmap.sh

2. Create Agent StatefulSet

   > grafana-stateful_set.sh

3. Deploy kubernetes state metrics.

   > grafana-kubernetes-state-metrics.sh

4. Deploy logging agent's configmap.

   > grafana-logs_Agent_configMap.sh

5. This finally installs the Grafana agent to the cluster
   and configures the RBAC permissions.

   > grafana-agent_daemonset.sh

All done! You've just deployed monitoring to your Grafana Cloud!

Jenkins Integration:

<https://grafana.com/docs/grafana-cloud/data-configuration/integrations/integration-reference/integration-jenkins>
