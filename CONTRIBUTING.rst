:orphan:

=============================================
Contributing to OpenStack's auto-scaling SIG
=============================================

If you would like to participate in discussions or contribute in any
way to the design and development of auto-scaling in OpenStack, please
first see the following documentation to understand the SIG's mission, scope,
and other supporting information:

  https://docs.openstack.org/auto-scaling-sig

Many forms of contribution are valuable to the community, including but not
limited to the following:

- `Documentation of use cases <#use-cases>`_, including implementation details if available
- `Design specs`_
- `Code`_
- `Report tasks/bugs in our StoryBoard`_
- `Review on Gerrit`_
- `Discussions`_ on all the above and other topics

Everyone is warmly encouraged to get involved in whatever capacity you
see fit.

Discussions
-----------

Discussions take place:

- on `the openstack-discuss mailing list
  <http://lists.openstack.org/cgi-bin/mailman/listinfo/openstack-discuss>`_
  with ``[auto-scaling-sig]`` in the Subject header,
- `the SIG's storyboard
  <https://storyboard.openstack.org/#!/project/openstack/auto-scaling-sig>`_,
- on IRC channel ``#openstack-auto-scaling``,
- in our `biweekly meeting <http://eavesdrop.openstack.org/#Auto-scaling_SIG_Meeting>`_
  (or office hour if no need for meeting),
- in patch reviews, and
- at face to face events such as the Summit and PTG.

Join us in any of these places to provide your feedback and ideas so we can work on
them together.

Use cases
---------

The SIG serves to facilitate the discussion and documentation of auto-scaling
use cases at all stages of development from a seed idea to a fully tested use
case.

To call attention to a use case, please start the discussion in `one
of the established communication channels <#discussions>`_.

Alternatively, directly submit a patch to document the use case,
following the format laid out in the `template file
<https://opendev.org/openstack/auto-scaling-sig/src/branch/master/use-cases/template.rst>`__
in `the use-cases/ directory
<https://opendev.org/openstack/auto-scaling-sig/src/branch/master/use-cases>`_
of `the auto-scaling-sig repository
<https://opendev.org/openstack/auto-scaling-sig>`_.

See `Submitting a change`_ for more information.

Design specs
------------

Design specs are proposed implementations of auto-scaling
functionality across projects. To author a new design spec, please
follow the format laid out in the `template file
<https://opendev.org/openstack/auto-scaling-sig/src/branch/master/specs/template.rst>`__
in `the specs/ directory
<https://opendev.org/openstack/auto-scaling-sig/src/branch/master/specs>`_
of `the auto-scaling-sig repository`_.

See `Submitting a change`_ for more information.

Code
----

`The auto-scaling-sig repository`_ also holds any relevant
cross-project code, tests, and documentation that do not naturally
belong in a single project repository.

See `Submitting a change`_ for more information.

Submitting a change
-------------------

To submit a change to this repository, please follow the steps in this page:

   http://docs.openstack.org/infra/manual/developers.html

If you already have a good understanding of how the system works and your
OpenStack accounts are set up, you can skip to the development workflow
section of this documentation to learn how changes to OpenStack should be
submitted for review via the Gerrit tool:

   http://docs.openstack.org/infra/manual/developers.html#development-workflow

Pull requests submitted through GitHub will be ignored.

Report tasks/bugs in our StoryBoard
-----------------------------------

Auto-scaling SIG uses
`StoryBoard <https://storyboard.openstack.org/#!/project/openstack/auto-scaling-sig>`_
to manage all tasks. If you're planning any kind of tasks related to this SIG,
you can create a story and link the task to other projects if needed.
For example, the story
`"Build integration tests" <https://storyboard.openstack.org/#!/story/2005752>`_
has tasks that link to other projects. This way we can track all auto-scaling work in
one place with references to the actual implementation. You might also create stories
for bug reports regarding auto-scaling across OpenStack (or auto-scaling integration
with other community tools).

Review on Gerrit
----------------

We would like to have more people to help on
`review patches <http://review.openstack.org/#/q/status:open+project:openstack/auto-scaling-sig>`_
so we can make sure the quality of it and confirm that whatever we put in is helpful.
