# cubejs-helm
A helm chart to deploy cubejs in kubernetes. This helm chart allows for deployment
of cube components in a cluster mode instead of the single node test mode.
All components are setup as per the docs here: https://cube.dev/docs/product/deployment

## Usage
To use the chart, execute

```$> helm install cubejs ./```

from the root of this repo.

To install to a specific namespace

```$> helm install cubejs ./ --create-namespace -n <name of the namespace>```

## Deployments created
The chart creates the following deployments with the associated services
* Cube API pods
* Cube refresh worker
* Cubestore router
* Cubestore worker

The env variables are present in the respective sections in values.yaml.

 ## List of improvements

 1) Ability to load schemas from git or other sources with init containers
 2) Ability to dynamical create replicas for the Cubestore workers and add them to the Cube router and worker deployment.
 3) Extend this to an operator method of deployment (May become another Repo altogether) 
