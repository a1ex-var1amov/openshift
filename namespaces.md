| Namespace | What it contains / why it exists | Key objects you should expect (default) | Doc link |
|-----------|----------------------------------|-----------------------------------------|----------|
| **kube-node-lease** | Node heartbeat Leases | `Lease/*` objects only | <https://kubernetes.io/docs/concepts/architecture/nodes/#node-heartbeats> |
| **kube-public** | World-readable bootstrap info | `ConfigMap/cluster-info`, misc. docs | <https://kubernetes.io/docs/reference/access-authn-authz/rbac/#user-facing-roles> |
| **kube-system** | Upstream control-plane add-ons | `DaemonSet/kube-proxy`, `ConfigMap/kube-proxy` | <https://kubernetes.io/docs/concepts/overview/components/> |
| **openshift** | Global templates & images | `ImageStream/*`, `Template/*` samples | <https://docs.openshift.com/container-platform/latest/openshift_images/using_images/images-other-jenkins.html#images-other-jenkins-openshift_project> |
| **openshift-apiserver** | OpenShift aggregated API | `Deployment/openshift-apiserver`, `Service/openshift-apiserver` | <https://docs.openshift.com/container-platform/latest/architecture/control-plane.html#openshift-apiserver> |
| **openshift-apiserver-operator** | Manages ↑ | `Deployment/openshift-apiserver-operator`, `Secret/installer-*` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#openshift-apiserver-operator> |
| **openshift-authentication** | OAuth server | `Deployment/oauth-openshift`, `Route/oauth-openshift`, `Secret/signing-key` | <https://docs.openshift.com/container-platform/latest/authentication/understanding-authentication.html> |
| **openshift-authentication-operator** | Manages ↑ | `Deployment/authentication-operator` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#authentication-operator> |
| **openshift-catalogd** | New catalog service | `Deployment/catalogd-controller-manager` | <https://docs.openshift.com/container-platform/latest/operators/understanding/olm/olm-understanding-olm.html#olm-catalogd> |
| **openshift-cloud-controller-manager** | External CCM | `DaemonSet/cloud-controller-manager`, cloud-specific `Secret/*` | <https://docs.openshift.com/container-platform/latest/installing/installing-azure-clouds.html#about-cloud-controller-manager-operator> |
| **openshift-cloud-controller-manager-operator** | Manages ↑ | `Deployment/cloud-controller-manager-operator` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#cloud-controller-manager-operator> |
| **openshift-cloud-credential-operator** | IAM credential minting | `Deployment/cloud-credential-operator`, `Secret/*-credentials` | <https://docs.openshift.com/container-platform/latest/storage/understanding-persistent-storage.html#cloud-credential-operator> |
| **openshift-cloud-network-config-controller** | Cloud-net tweaks | `Deployment/cloud-network-config-controller` | <https://docs.openshift.com/container-platform/latest/networking/cloud-network-config-controller.html> |
| **openshift-cluster-csi-drivers** | Red Hat CSI drivers | One or more `Deployment/*-csi-*`, `CSIDriver` CRs | <https://docs.openshift.com/container-platform/latest/storage/container_storage_interface/persistent-storage-csi.html> |
| **openshift-cluster-machine-approver** | CSR auto-approver | `Deployment/cluster-machine-approver` | <https://docs.openshift.com/container-platform/latest/authentication/certificate-types-descriptions.html#kubelet-serving-profiles> |
| **openshift-cluster-node-tuning-operator** | Performance tuning | `Deployment/cluster-node-tuning-operator`, `DaemonSet/tuned` | <https://docs.openshift.com/container-platform/latest/scalability_and_performance/using-node-tuning-operator.html> |
| **openshift-cluster-olm-operator** | Installs OLM | `Deployment/cluster-olm-operator` | <https://docs.openshift.com/container-platform/latest/operators/understanding/olm/olm-understanding-olm.html> |
| **openshift-cluster-samples-operator** | Sample imagestreams | `Deployment/cluster-samples-operator`, imagestream `ConfigMap/samples-?` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#cluster-samples-operator> |
| **openshift-cluster-storage-operator** | Storage meta-operator | `Deployment/cluster-storage-operator` | <https://docs.openshift.com/container-platform/latest/storage/understanding-persistent-storage.html#cluster-storage-operator> |
| **openshift-cluster-version** | CVO & upgrade history | `Deployment/cluster-version-operator`, `ClusterVersion/version` CR | <https://docs.openshift.com/container-platform/latest/updating/updating-cluster.html> |
| **openshift-config** | Cluster-wide config CRs | `Proxy/cluster`, `Image.config.openshift.io/cluster`, etc. (no pods) | <https://docs.openshift.com/container-platform/latest/architecture/control-plane.html#cluster-configuration-resources> |
| **openshift-config-managed** | Auto-generated config | Various `ConfigMap/managed-*` (no pods) | same link |
| **openshift-config-operator** | Manages ↑ | `Deployment/cluster-config-operator` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#cluster-config-operator> |
| **openshift-console** | Web console UI | `Deployment/console`, `Service/console`, `Route/console` | <https://docs.openshift.com/container-platform/latest/web_console/web-console-overview.html> |
| **openshift-console-operator** | Manages ↑ | `Deployment/console-operator` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#console-operator> |
| **openshift-console-user-settings** | Per-user prefs | `ConfigMap/user-settings-*` created on demand | — |
| **openshift-controller-manager** | Build/Quota controllers | `Deployment/openshift-controller-manager` | <https://docs.openshift.com/container-platform/latest/architecture/control-plane.html#openshift-controller-manager> |
| **openshift-controller-manager-operator** | Manages ↑ | `Deployment/openshift-controller-manager-operator` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#openshift-controller-manager-operator> |
| **openshift-dns** | CoreDNS service | `DaemonSet/dns-default`, `Service/dns-default` | <https://docs.openshift.com/container-platform/latest/networking/dns-operator.html> |
| **openshift-dns-operator** | Manages ↑ | `Deployment/dns-operator` | same link |
| **openshift-etcd** | etcd cluster | Static `Pod/etcd-*`, `Service/etcd` | <https://docs.openshift.com/container-platform/latest/scalability_and_performance/etcd-performance.html> |
| **openshift-etcd-operator** | Manages snapshots & guard pods | `Deployment/etcd-operator`, `Pod/etcd-quorum-guard-*` | same link |
| **openshift-host-network** | Host-network criticals | `DaemonSet/nodeip-*`, `Pod/ip-allocator` | — |
| **openshift-image-registry** | Internal registry | `Deployment/image-registry`, `Route/default-route` | <https://docs.openshift.com/container-platform/latest/registry/architecture-component-imageregistry.html> |
| **openshift-ingress** | HAProxy routers | `DaemonSet/router-default`, `Service/router-internal` | <https://docs.openshift.com/container-platform/latest/networking/ingress-operator.html> |
| **openshift-ingress-canary** | Canary checker | `Deployment/ingress-canary`, `Service/ingress-canary` | same link |
| **openshift-ingress-operator** | Manages routers | `Deployment/ingress-operator` | same link |
| **openshift-insights** | Telemetry collectors | `Deployment/insights-operator`, `CronJob/gather-*` | <https://docs.openshift.com/container-platform/latest/support/remote_health_monitoring/about-remote-health-monitoring.html> |
| **openshift-kni-infra** | Bare-metal perf | `DaemonSet/sriov-network-device-plugin`, etc. | <https://docs.openshift.com/container-platform/latest/scalability_and_performance/cnf-numa-aware-scheduling.html> |
| **openshift-kube-apiserver** | kube-apiserver | Static `Pod/kube-apiserver-*`, `Service/kubernetes` | <https://docs.openshift.com/container-platform/latest/architecture/control-plane.html#kubernetes-api-server> |
| **openshift-kube-apiserver-operator** | Manages ↑ | `Deployment/kube-apiserver-operator` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#kube-apiserver-operator> |
| **openshift-kube-controller-manager** | kube-controllers | Static `Pod/kube-controller-manager-*` | <https://docs.openshift.com/container-platform/latest/architecture/control-plane.html#kube-controller-manager> |
| **openshift-kube-controller-manager-operator** | Manages ↑ | `Deployment/kube-controller-manager-operator` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#kube-controller-manager-operator> |
| **openshift-kube-scheduler** | kube-scheduler | Static `Pod/kube-scheduler-*` | <https://docs.openshift.com/container-platform/latest/architecture/control-plane.html#kube-scheduler> |
| **openshift-kube-scheduler-operator** | Manages ↑ | `Deployment/kube-scheduler-operator` | <https://docs.openshift.com/container-platform/latest/operators/operator-reference.html#kube-scheduler-operator> |
| **openshift-kube-storage-version-migrator** | API migrator jobs | `Job/storage-version-migration-*` | <https://docs.openshift.com/container-platform/latest/updating/updating-cluster.html#update-storage-migration> |
| **openshift-kube-storage-version-migrator-operator** | Manages ↑ | `Deployment/kube-storage-version-migrator-operator` | same link |
| **openshift-machine-api** | MachineSets & MAPI ctrl | `Deployment/machine-api-controllers`, `DaemonSet/machine-config-server` | <https://docs.openshift.com/container-platform/latest/machine_management/creating_machinesets/creating-machineset-aws.html#machineset-about_machine-api> |
| **openshift-machine-config-operator** | OS updates | `DaemonSet/machine-config-daemon`, `Deployment/machine-config-controller` | <https://docs.openshift.com/container-platform/latest/architecture/control-plane.html#machine-config-operator> |
| **openshift-marketplace** | Operator catalogs | `Deployment/marketplace-operator`, `Pod/redhat-operators*` | <https://docs.openshift.com/container-platform/latest/operators/understanding/olm/olm-understanding-olm.html#olm-marketplace> |
| **openshift-monitoring** | Cluster metrics | `StatefulSet/prometheus-k8s`, `Deployment/alertmanager-main`, `Deployment/thanos-*`, `DaemonSet/node-exporter` | <https://docs.openshift.com/container-platform/latest/monitoring/monitoring-overview.html> |
| **openshift-multus** | Multus CNI | `DaemonSet/multus` | <https://docs.openshift.com/container-platform/latest/networking/multiple_networks/understanding-multiple-networks.html> |
| **openshift-network-console** | Net-UI plugin | `Deployment/network-console-plugin` | — |
| **openshift-network-diagnostics** | Net tests | `Job/network-check-target`, `Job/network-check-source` | — |
| **openshift-network-node-identity** | Egress IP IDs | `DaemonSet/network-node-identity` | — |
| **openshift-network-operator** | CNO | `Deployment/network-operator`, `ClusterNetwork` CRs | <https://docs.openshift.com/container-platform/latest/networking/cluster-network-operator.html> |
| **openshift-node** | kube-proxy, etc. | `DaemonSet/kube-proxy` (when not in `kube-system`) | — |
| **openshift-nutanix-infra** | Nutanix CSI | `StatefulSet/nutanix-csi-controller`, `DaemonSet/nutanix-csi-node` | <https://docs.openshift.com/container-platform/latest/installing/installing_nutanix/installing-nutanix-installer-provisioned.html> |
| **openshift-oauth-apiserver** | OAuth API | `Deployment/oauth-apiserver` | <https://docs.openshift.com/container-platform/latest/authentication/understanding-oauth.html#oauth-apiserver> |
| **openshift-openstack-infra** | Kuryr, Cinder CSI | `DaemonSet/openstack-cinder-csi-node`, `Deployment/kuryr-controller` | <https://docs.openshift.com/container-platform/latest/installing/installing_openstack/installing-openstack-installer-owned.html> |
| **openshift-operator-controller** | OLM ctrl mgr | `Deployment/operator-controller-manager` | <https://docs.openshift.com/container-platform/latest/operators/understanding/olm/olm-understanding-olm.html> |
| **openshift-operator-lifecycle-manager** | Core OLM | `Deployment/olm-operator`, `Deployment/catalog-operator`, `Deployment/packageserver` | same link |
| **openshift-operators** | Global Operator installs | Varies: your own `Subscription/*`, `Deployment/<operator>` | <https://docs.openshift.com/container-platform/latest/operators/olm-managing-custom-catalogs.html#olm-target-operator-install-ops_olm-managing-custom-catalogs> |
| **openshift-ovirt-infra** | oVirt CSI | `StatefulSet/ovirt-csi-controller`, `DaemonSet/ovirt-csi-node` | <https://docs.openshift.com/container-platform/latest/installing/installing_ovirt/installing-ovirt-installer-provisioned.html> |
| **openshift-ovn-kubernetes** | OVN components | `DaemonSet/ovnkube-node`, `Deployment/ovnkube-master`, `Deployment/ovnkube-db` | <https://docs.openshift.com/container-platform/latest/networking/ovn_kubernetes_network_provider/about-ovn-kubernetes.html> |
| **openshift-route-controller-manager** | Route ↔ ingress sync | `Deployment/route-controller-manager` | — |
| **openshift-service-ca** | Serving-cert injection | `Deployment/service-ca` | <https://docs.openshift.com/container-platform/latest/security/certificates/service-serving-certificate.html> |
| **openshift-service-ca-operator** | Manages ↑ | `Deployment/service-ca-operator` | same link |
| **openshift-user-workload-monitoring** | User metrics stack | When enabled: `StatefulSet/prometheus-user-workload`, `Deployment/than
os-ruler-user-workload` | <https://docs.openshift.com/container-platform/latest/monitoring/enabling-monitoring-for-user-defined-projects.html> |
| **openshift-vsphere-infra** | vSphere CSI | `StatefulSet/vsphere-csi-controller`, `DaemonSet/vsphere-csi-node` | <https://docs.openshift.com/container-platform/latest/installing/installing_vsphere/installing-vsphere-installer-provisioned.html> |
