# Add day2 worker nodes

Base manifests to create one single worker node for day 2 operations using RHACM on an already existent 3-node cluster.

## Defaults for 1-worker 

- base BareMetalHost on the workload cluster with all common data inside.
- base secret to be customized for BMC access. 
- base NMStateConfig to be fully configured.
- static network configuration provisioning able to watch allnamespaces

Note that for the day2 worker nodes to join the cluster the CSRs need to be approved. If the CSRs were not approved the user will have to approve manually. To approve all pending CSRs, run the following command:

```console
oc get csr -o go-template='{{range .items}}{{if not .status}}{{.metadata.name}}{{"\n"}}{{end}}{{end}}' | xargs --no-run-if-empty oc adm certificate approve
```