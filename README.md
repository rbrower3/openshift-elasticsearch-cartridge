OpenShift ElasticSearch **2.2.1** Cartridge
=================================
Downloadable ElasticSearch cartridge for OpenShift.

This is an working attempt at updating to 2.2.1 use at your own risk. I have had a three node cluster running since 3.28.2016
Below is obviously not the method for instaling the app - if things are stable for a bit longer i'll request a git pull from rbrower's branch.

I've moved some things around and made small changes to the rbrower branch:

  - set cluster.name as a (modifiable) env variable which is based on namesspace and app name rather than app uuid
  - moved config to templates **I found this neccessary because occasionaly cors settings etc. need to be set in config**
  - updated install for marvel in plugins.txt this includes instructions for adding the required license.
  - set the ``ES_HEAP_SIZE`` to the correct settings (1/2 of gear memory) this is also set as an env variable and should change per gear size.

there is currently a manifest.yml you can use for insatll at:

    http://wwwwwwwww.un.salted.nu/manifest.yml

To create your scalable ElasticSearch app, run:

    rhc app create <your app name> http://cartreflect-claytondev.rhcloud.com/github/rbrower3/openshift-elasticsearch-cartridge -s

**NOTE:** your app currently must be a scalable app or this cartridge will not run.


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
