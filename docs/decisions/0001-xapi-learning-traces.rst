Design Considerations for Standardizing on xAPI for Learning Analytics
----------------------------------------------------------------------

Status
======

Proposal

Context
=======

Currently this document is only for capturing the design consideration for making xAPI the canonical event format for platform learning analytics.

This work would evolve from `this high-level proposal <https://discuss.openedx.org/t/proposal-embargo-and-replace-the-native-open-edx-eventing-subsystem/7353`_

Design Considerations:

#. We will need to develop a point of view on whether our xAPI representation of the native event logs should strive to comprehensively represent all data currently available in the event logs.
#. We should have a system where users can opt-in to emmiting particular events of portions of events.  For example, a deployer might want to opt our of generating login related events.  Or, a deployer might choose to not include specific optional parts of a statement, for example, hint data for problems.
#. We should use established xAPI extensions when they exist and their semantics match Open edX semantics.
#. We can consider creating our own xAPI profiles where we are innovating in ways that might be valuable to the wider community.
#. It may make sense for a single Open edX native event to create multiple xAPI statements.
#. We need to consider what idiomatic standards exist for xAPI statements.  Comprehensive statements may best be represented as multiple linked statements.  An example of this might be a statement containing the details of a problem and a statement representing a particular students interaction with that problem.  `This PR <https://github.com/openedx/data-wg/pull/17>`_ represents a comprehensive single statement representing both the question and the answer.
#. Need to understand the rationale for `the decision <https://github.com/openedx/event-routing-backends/blob/master/docs/event-mapping/xAPI_mapping.rst#problem_check-event_source_server>`_ in the `event-routing-backends <https://github.com/openedx/event-routing-backends>`_ project for having client side and server side problem check are mapped to different xAPI statements.
#. Which type is preferable for problems?  http://adlnet.gov/expapi/activities/cmi.interaction or http://adlnet.gov/expapi/activities/question?

Decision
========


