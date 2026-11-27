Why alert on stale pull requests?
=================================

An inactive pull request can need a reviewer, a decision, or an update from
its author. A visible label and a comment prompt a human to investigate while
preserving work that may still be valuable. Staleness is not a decision to
close: this repository's workflow never automatically closes pull requests.

The action uses GitHub activity to detect inactivity, not the actual state of
the work. Activity can reset the timer without resolving a blocker, while a
quiet pull request may be intentionally waiting. Updating a stale PR allows
the action to remove its label on a later run; another inactive period can
lead to a fresh alert. See the upstream
`action documentation <https://github.com/actions/stale/tree/v11.0.0>`_ for
the detailed lifecycle.

The initial 30-day threshold and daily schedule are assumptions, not a
service-level agreement. The policy assumes maintainers will monitor the
comment or label and decide what to do. It includes draft PRs unless an
exemption is configured, and does not process issues. No recipient list or
management hierarchy is assumed. The action cannot identify everyone
internal to the organization or perform timed escalation; notification
delivery depends on GitHub permissions and subscriptions. See
:doc:`the configuration guide </how-to/stale-pull-requests>` for options.
