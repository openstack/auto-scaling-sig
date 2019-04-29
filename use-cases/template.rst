..
  This template is intended to encourage a certain level of
  consistency between different use cases.  Adherence to the structure
  of this template is recommended but not strictly required.

  This template should be in ReSTructured text.  For help with syntax,
  see <http://sphinx-doc.org/rest.html>. To test out your formatting,
  see <http://www.tele3.cz/jbar/rest/rest.html>.

=======================================
The title of your auto-scaling use case
=======================================

..
  Please fill in the blanks in this use case statement, or rephrase
  as appropriate.

As a cloud operator, whenever one of my cloud's ____________________,
I want ____________________________.


Problem description
===================

..
  A more detailed description of the auto-scaling scenario;
  however it is not advised to duplicate details covered in the
  sections below.  If the problem is not too complex, it may be more
  appropriate to simply delete this section and provide the details in
  the sections below.


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
