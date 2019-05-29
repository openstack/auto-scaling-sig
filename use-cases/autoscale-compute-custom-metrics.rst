============================================================
Auto-scale Compute based on Custom Metrics from Applications
============================================================

As a user of OpenStack I want to define a logical group of compute
resources which are increased or decreased automatically based on
metrics which are emitted from an application running in the cloud.


Problem description
===================

..
  A more detailed description of the auto-scaling scenario;
  however it is not advised to duplicate details covered in the
  sections below.  If the problem is not too complex, it may be more
  appropriate to simply delete this section and provide the details in
  the sections below.

An Application developer will define metrics which their application
can emit to a Monitoring Service.  This could be a report of RPS from
a web application.  Or information about distribution of objects reported
by Swift.  The Monitoring Service would generate alarms based on the
metrics or report them to a Decision Service for analysis.  Commands
would be passed to an Orchestration Engine to scale up or down.

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

* Monasca and Heat

  Monasca can receive metrics from an application and generate alarms
  if a metric exceeds a threshold.  The alarm notification can then
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
