# e-commerce-monitoring
Repo to test monitoring practies on Kubernetes cluster

# Steps to install on kubernetes cluster
# must have kubectl installed and pointing to the correct
# cluster. Also requires helm, curl, and envsubst on local
# systems. The cluster must also have tiller and docker installed.
# These are all installed into the 'default' namespace,
# though this can be changed with a simple 'ctrl + H' to
# whichever namespace you prefer.

1. Create metrics agent configmap.
  a. grafana-agent_configmap.sh
2. Create Agent StatefulSet
  a. grafana-stateful_set.sh
3. Deploy kubernetes state metrics.
  a. grafana-kubernetes-state-metrics.sh
4. Deploy logging agent's configmap.
  a. grafana-logs_Agent_configMap.sh
5. This finally installs the Grafana agent to the cluster
    and configures the RBAC permissions.
  b. grafana-agent_daemonset.sh
  
All done! You've just deployed monitoring to your Grafana Cloud!

Jenkins Integration:
