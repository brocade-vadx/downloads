- Untar brocade_lbaas_plugin.tar.gz under $NEUTRON_HOME/services/loadbalancer/drivers directory.
  Example: $NEUTRON_HOME typically would be /usr/local/lib/python2.7/dist-packages/neutron

- Untar brocade_neutron_lbaas-1.0.tar.gz to a temporary location and unpack the contents.
  After that, Execute 'sudo python setup.py install'. This will install the Brocade Neutron LBaaS 
  Device Driver in the python dist-packages

- Enable the Brocade LBaaS Plugin Driver in neutron.conf

comment the Haproxy (which is the default service provider for LOADBALANCER) under service_provider section and specify Brocade as the service provider for LOADBALANCER (as shown below)

    service_provider = LOADBALANCER:brocade:neutron.services.loadbalancer.drivers.brocade.plugin_driver_v1.BrocadePluginDriverV1:default


To use this plugin driver, you must:
 - Install Brocade Neutron LBaaS Device Driver (from the Brocade Git Hub Location). Basically, download the  brocade_neutron_lbaas-1.0.tar.gz, unpack it in a temporary locaion and run sudo python setup.py install.
 - Create a driver config file, under /etc/neutron/services/loadbalancer/brocade/devices.json.

Sample Configuration File:
[
    {
        "name" :"Device 1",
        "ip":"10.24.143.168",
        "user":"admin",
        "password":"brocade",
        "subnet_id":[
            "<subnetwork_id>"]
    }
]


- Restart the Neutron Server
