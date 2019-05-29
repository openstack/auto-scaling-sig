============================================
Auto-scale Compute to Balance Resource Usage
============================================

* As a deployer and operator of OpenStack I want to be able to
  configure highly available autoscaling services with Free Open
  Source Software.

* As an operator of OpenStack I want to be able to add additional
  compute nodes to my cluster from a pool of available bare metal
  inventory automatically in response to resource consumption within
  my cloud.

* As an operator of OpenStack I want to be able to remove compute
  nodes from my cluster and return them to the pool of available bare
  metal inventory nodes in response to an excess quantity of compute
  resource availability within my cloud.

* As an app deployer I want to automatically scale-in one app to free
  up physical infra to scale-out another app which needs the resources
  more. More generally, I want to scale various apps in/out/up/down
  based on load/priority/custom policy, subject to some global
  resource constraints.

Problem description
===================

* Global constraints: As an app deployer I want to automatically scale-in one app to free up physical infra to scale-out another app which needs the resources more.

  More generally, I want to scale various apps in/out/up/down based on load/priority/custom policy, subject to some global resource constraints.

  * Sort of like pre-emptible resources or something like that?
  * Yes, but maybe more dynamic and more levels of priority. One workload may be high priority in one load condition, but become low priority under a different load condition.
  * Ah, interesting! Like each autoscale group would have some concept of priority and timeframe (critical from 0900-1700, medium priority 1800->2000, low priority from 2100->0800)
  * Could be something like that. Here's a more concrete example:

    * I have two apps, A and B. Both apps are monitored for request completion time.

      * App A has the targets: good: 0-10ms ; ok: 10-30ms; bad: > 30 ms;
      * App B has the targets: good: 0-100ms ; ok: 100-500ms; bad: > 500 ms;

    * Based on the current load condition and request completion time, I want to allocate the physical compute resource between the two apps based on some optimization criteria.

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
