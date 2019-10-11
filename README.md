# cStor Examples

## set up a cStor storage class
​
1. Install OpenEBS
2. Identify disks to use
3. Create a StoragePoolClaim matching those disks
4. Create a StorageClass matching that claim


### 1. Install OpenEBS

#### Always check your context!
* `kubectl config get-contexts`
* `kubectl config use-context CONTEXT_NAME`

#### Pull down and inspect the operator manifest:

* `wget https://openebs.github.io/charts/openebs-operator-1.2.0.yaml`

Setup disk filters for Node Disk Manager if needed (you may want to
ignore some devices).  You can search for the 'exclude' line, and
update the comma-separated list of device node paths:

"exclude":"loop,/dev/fd0,/dev/sr0,/dev/ram,/dev/dm-"

#### Install OpenEBS:

* `kubectl apply -f openebs-operator-1.2.0.yaml`
* `kubectl get pods -n openebs -w

### 2. Identify disks to use
