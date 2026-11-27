Stale pull request workflow reference
=====================================

The repository workflow is ``.github/workflows/stale.yml``. For the complete
list and semantics of inputs, permissions, and outputs, see the
`actions/stale v11 documentation <https://github.com/actions/stale/tree/v11.0.0>`_.

.. list-table::
   :header-rows: 1

   * - Setting
     - Repository policy
   * - Trigger
     - Daily at 03:17 UTC; also manually dispatchable
   * - ``days-before-pr-stale``
     - 30 days of inactivity
   * - ``days-before-issue-stale``
     - ``-1``: do not mark issues stale
   * - ``days-before-close``
     - ``-1``: disable automatic closure
   * - ``days-before-pr-close``
     - ``-1``: explicitly disable PR closure
   * - ``stale-pr-label``
     - ``stale``
   * - ``remove-pr-stale-when-updated``
     - ``true``
   * - ``stale-pr-message``
     - Request a review; state that no auto-close occurs

The action is pinned to a commit of v11.0.0. It uses the default GitHub token
with ``actions: write`` for persisted processing state and ``issues: write``
and ``pull-requests: write`` for the action's operations. It does not request
``contents: write`` or delete branches. The default operation limit can delay
processing across runs. Scheduled runs can also be delayed by GitHub.

The message is a PR comment, not an email or a configurable escalation
service. GitHub handles delivery to subscribers and explicitly mentioned
eligible users or teams. There are no default mentions, automatic recipient
discovery, repeated timed reminders, or escalation stages.
