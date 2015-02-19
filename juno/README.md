Install Instructions
--------------------

- Install Brocade OpenStack LBaaS Plugin Driver Code

    - Untar brocade_lbaas_plugin.tar.gz under $NEUTRON_HOME/services/loadbalancer/drivers directory.

    - $NEUTRON_HOME is the location where OpenStack Neutron component is installed. For example, $NEUTRON_HOME could be /usr/local/lib/python2.7/dist-packages/neutron

- Install Brocade LBaaS Device Driver Python Module

    - Copy brocade_neutron_lbaas-1.0.tar.gz to a temporary location 

    - Unpack the file ("tar zxvf brocade_neutron_lbaas-1.0.tar.gz")

    - Change directory ("cd  brocade_neutron_lbaas-1.0")

    - Run "sudo python setup.py install")

- Enable Brocade OpenStack LBaaS Plugin Driver as the service provider for LOADBALANCER service in neutron.conf

    - Comment the Haproxy (typically the default service provider for LOADBALANCER) under service_provider section 

    - Specify Brocade as the service provider for LOADBALANCER (as shown below)

      service_provider = LOADBALANCER:brocade:neutron.services.loadbalancer.drivers.brocade.plugin_driver_v1.BrocadePluginDriverV1:default

- Restart the Neutron Server
