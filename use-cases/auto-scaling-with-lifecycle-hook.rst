=========================================
Auto-scaling Compute with Lifecycle Hooks
=========================================

As a user of OpenStack, I want to define a cluster of VMs which is increased or decreased
automatically based on the consumption of discrete physical resources within my VMs.
When the compute resources are decreased, I want applications running in the VM selected for deletion to be
notified using a lifecycle hook.  Once the application receives a lifecycle hook notification,
it will perform any draining or clean-up tasks.  Once the draining has completed,
I want the VM to complete the lifecycle hook by signaling that it is ready for removal.


Problem description
===================

Applications that use stateful connections require the application to drain
the existing connections before they are terminated.  In order to auto-scale those
types of applications, the application must be notified before the underlying
instances are scaled-in by the clustering service.  The notification received by
the application to perform the draining is called lifecycle hook.
Once the draining has completed, the application signals to the orchestration /
clustering service that the VM is ready for deletion.  This signal is called lifecycle hook completion.


OpenStack projects used
=======================

* Senlin
* Zaqar


Other projects used
===================

* Monitoring and alerting service


Inputs and decision-making
==========================

The metric used to determine auto-scaling can be any monitored metric.  E.g.:

* CPU usage
* custom defined load

Lifecycle hooks are defined for clusters that are running workloads which require draining.


Auto-scaling
============

Scale-In Scenario
-----------------

1. When the monitoring and alerting service detects that the auto-scaling metric
has crossed below the pre-defined minimum threshold, it makes a requests to
the orchestration/clustering service to scale-in the cluster.

2. If the VM selected for deletion belongs to a cluster that has lifecycle hooks defined, the
clustering service notifies the VM of the lifecycle hook.

3. The application running in the VM receives the lifecycle hook notification and begins draining.

4. Once the draining has completed, the application completes the lifecycle hook.

5. When the clustering services receives the lifecycle hook completion, it
deletes the VM.


Existing implementation(s)
==========================

Senlin
-------

* Lifecycle hooks are defined in a Senlin deletion policy and attached to clusters.
* Lifecycle hooks are implemented as a message notification on a Zaqar queue.
* The application subscribes to the Zaqar queue to receive lifecycle hook notifications.
* Lifecycle hook completion is implemented as a Senlin API that accepts a lifecycle action token.
* The lifecycle action token is stored in the lifecycle hook notification sent to the Zaqar queue.


Future work
===========

* Allow application defined webhooks as a lifecycle hook notification option.


Dependencies
============

N/A
