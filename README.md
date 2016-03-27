OpenShift ElasticSearch **2.2.0** Cartridge
=================================
Downloadable ElasticSearch cartridge for OpenShift.

To create your scalable ElasticSearch app, run:

    rhc app create <your app name> http://cartreflect-claytondev.rhcloud.com/github/rbrower3/openshift-elasticsearch-cartridge -s

**NOTE:** your app currently must be a scalable app or this cartridge will not run.

**Haven't tested scaling...**

This is an working attempt at updating to 2.2.1 use at your own risk.



Adding additional cluster nodes
===============================
To add more nodes to the cluster, simply add more gears:

    rhc cartridge scale -a <your app name> elasticsearch <number of total gears you want>


Plugins
=======
To install ElasticSearch plugins -
* create new app in openshift
* edit the `plugins.txt` file 
* commit
* push your changes to openshift.

The above steps have been tested in OpenShift Online (v2). For Openshift Enterprise, in case it does not have internet access, you may need to copy the plugins and install them.
