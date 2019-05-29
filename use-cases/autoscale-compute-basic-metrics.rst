..
  This template is intended to encourage a certain level of
  consistency between different use cases.  Adherence to the structure
  of this template is recommended but not strictly required.

  This template should be in ReSTructured text.  For help with syntax,
  see <http://sphinx-doc.org/rest.html>. To test out your formatting,
  see <http://www.tele3.cz/jbar/rest/rest.html>.

====================================================
Auto-scale Compute based on Consumption of Resources
====================================================

As a user of OpenStack I want to define a logical group of compute
resources which are increased or decreased automatically based on the
consumption of discrete physical resources within my instances, for
example CPU or Memory utilization; Disk IOPS, etc.


Problem description
===================

..
  A more detailed description of the auto-scaling scenario;
  however it is not advised to duplicate details covered in the
  sections below.  If the problem is not too complex, it may be more
  appropriate to simply delete this section and provide the details in
  the sections below.

In many ways, this is the basic use case for Auto-Scaling in OpenStack.

An OpenStack user, whether admin or operator, defines logic for triggering
the auto-scaling based on the consumption of resources in the cloud.
The resources could be CPU cycles, storage, memory, network, or a combination.
The logic will typically define both scale up and scale down thresholds,
and include an upper and lower bound for scaling.
An orchestration engine for the cloud will be instructed to perform the
scale up or scale down operations as specified.

This use case was called out in the Denver 2019 PTG - https://etherpad.openstack.org/p/DEN-auto-scaling-SIG

OpenStack projects used
=======================

..
  Please provide a list of projects (OpenStack and otherwise) which
  may be used in order to implement this use case.  If no
  implementation exists yet, suggestions are sufficient here.

* ...
* ...


Inputs and decision-making
==========================

..
  Describe how decisions about when/how to auto-scale are taken.  In
  particular list any other components or inputs which may provide
  additional context to help determine the correct action.

The resources monitoring used to determine auto scaling can be any monitored metric.

A few classic examples of metrics are:

* Overall CPU percentage on a host of Virtual Machines
* CPU percentabe utilization averaged across a group of Virtual Machines
  See https://github.com/sjamgade/monasca-autoscaling/blob/master/autoscaling.yaml
  for an example.
* System memory average utilization percentage
* Storage or disk space utilization percentage

In most cases, a high and a low threshold for the metric are determined to correspond
with scale up or scale down actions.


Auto-scaling
============

..
  Describe how the auto-scaling may occur.  If there may be different
  approaches available, please list them all.


Existing implementation(s)
==========================

..
  If there are one or more existing implementations of this use case,
  please give as many details as possible, in order that operators can
  re-implement the use case in their own clouds.  However any
  information is better than no information!  Linking to external
  documents is perfectly acceptable.

* Monasca and Heat

  Monasca can monitor the physical resources and generate alarms if a
  resource usage exceeds a threshold.  The alarm notification can then
  trigger a Heat template and scale the topology appropriately.

* <TODO: record other options>

Future work
===========

..
  Please link from here to any relevant specs.  If a cross-project
  spec is required, it can be placed under ../specs/ in this
  repository.

  Please also make sure that any linked specs contain back-links
  to this use case for maximum discoverability.


Dependencies
============

..
  - Include specific references to specs and/or blueprints in
    auto-scaling-sig, or in other projects, that this one either depends
    on or is related to.

  - Does this feature require any new library dependencies or code
    otherwise not included in OpenStack? Or does it depend on a specific
    version of library?
