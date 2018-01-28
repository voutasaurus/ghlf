# ghlf

Deploy and manage Hyperledger Fabric on GKE.

# usage:

Login to Google Cloud

	$ ghlf login	 
	API Token: ****

Provision k8s cluster

	$ ghlf provision <clustername>

Define HyperLedger Fabric config

	$ ghlf config generate -cluster=name > hlf.conf
	$ vim hlf.conf # to edit

Deploy HyperLedger Fabric to cluster

	$ ghlf deploy -config=hlf.conf

Modify existing deployment

	$ sed -ie s/^VERSION=.*$/VERSION=v1.1.0-preview/ hlf.conf 
	$ ghlf deploy -config=hlf.conf

# Configure

Example hlf.conf:

	PROJECT=newproject
	CLUSTER=clustername
	VERSION=v1.0.5
	MODE=kafka
	KFN=4
	ZKN=5

# TODO

* Google Cloud Login
* GKE Cluster Provisioning
* Kubernetes Deployment
* Configuration Generation

# Components

* Secret Management (cloud encrypted key value store)
* Observability
* Resilience
