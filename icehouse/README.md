- Untar brocade_lbaas_plugin.tar.gz under <neutron_home>/services/loadbalancer/drivers directory.
  Example: <neutron_home> typically would be /usr/local/lib/python2.7/dist-packages/neutron

- Untar brocade_neutron_lbaas-1.0.tar.gz to a temporary location and unpack the contents.
  After that, Execute 'sudo python setup.py install'. This iwll install the Brocade Neutron LBaaS 
  Device Driver in the python dist-packages