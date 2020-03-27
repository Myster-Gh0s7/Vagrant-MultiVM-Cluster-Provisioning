# Vagrant-MultiVM-Cluster-Provisioning

## Start

```bash
$ git clone https://github.com/Myster-Gh0s7/Vagrant-MultiVM-Cluster-Provisioning && cd Vagrant-MultiVM-Cluster-Provisioning

$ vagrant up
```

## Usage

* **BOX_IMAGE** is currently default with "geerlingguy/ubuntu1604" box which is custom box created which can be used for setting up the cluster  
  with basic dependencies for kubernetes node.
* Set **SETUP_MASTER** to true if you want to setup the node. This is true by default for spawning a new cluster. You can skip it for adding 
  new minions.
* Set **SETUP_NODES** to true/false depending on whether you are setting up minions in the cluster.
* Specify **NODE_COUNT** as the count of minions in the cluster
* Specify the **MASTER_IP** as static IP which can be referenced for other cluster configurations
* Specify **NODE_IP_NW** as the network IP which can be used for assigning dynamic IPs for cluster nodes from the same network as Master

# What is remained

* Needs to add bootstrap for additional setup inside master and node.


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
