Deploy
------

ie.
```
for i in landrush vagrant-hostmanager vagrant-registration vagrant-sshfs ; do vagrant plugin install $i ; done

for i in `seq 1 15` ; do
  DEPLOYMENT_TYPE=openshift-enterprise SUB_USERNAME='warsztaty-openshift-azure@linuxpolska.pl' SUB_PASSWORD='xxx' RHSM_POOL='Red Hat OpenShift, Standard Support (10 Cores, NFR, Partner Only)' CLUSTER_ID=$i vagrant up
  vagrant landrush set apps.lab$i.example.com master1.lab$i.example.com
done
```

Test
----

```
kaminskypavel/mario
```
