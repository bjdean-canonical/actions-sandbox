Configure stale pull request alerts
===================================

Edit ``.github/workflows/stale.yml`` and merge the change to the default
branch. The schedule and the ``workflow_dispatch`` button use the workflow
there. The workflow includes commented examples for optional settings.

Change the message and recipients
---------------------------------

Edit ``stale-pr-message`` to change the comment. To notify a known person or
team explicitly, add ``@username`` or ``@organization/team-slug`` in the
message text, replacing the examples with real accounts. Each alert uses the
same text: there are no per-PR recipient variables or built-in lookup of
authors, assignees, reviewers, or organization membership.

PR participants and subscribers may receive the comment through their normal
GitHub notification settings. A mention is not a guarantee of delivery:
repository access, team visibility and mention permissions, and personal
notification settings matter. See GitHub's documentation on
`notifications <https://docs.github.com/en/subscriptions-and-notifications/concepts/about-notifications>`_
and `mentions <https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#mentioning-people-and-teams>`_.
Do not assume that every internal participant was notified.

Plan escalation
---------------

The workflow comments contain an example escalation table. Replace it with
your agreed owners and thresholds; it is a human playbook, not executable
configuration. For example, a maintainer can inspect PRs labelled ``stale``
and mention the review team, then a team lead, then a manager at agreed
intervals. Confirm that recipients can access the repository before mentioning
them. A static team mention in ``stale-pr-message`` alerts that team at the
initial stale event only; it does not implement later stages.

For automatic staged escalation or discovery of internal participants, a
separate implementation must determine eligible recipients and membership,
track escalation stages, and send notifications with appropriate permissions.
Assess privacy, delivery, rate limits, and duplicate alerts before enabling it.
Do not use the action's close settings to implement escalation.

Change eligibility or troubleshoot
-----------------------------------

Adjust ``days-before-pr-stale`` and the message together. Optional
``exempt-pr-labels`` and ``exempt-draft-pr`` examples are in the workflow.
Keep both close thresholds at ``-1`` and issue staling disabled. Check the
Actions logs for permissions or operation-limit warnings; consult the upstream
`options and troubleshooting <https://github.com/actions/stale/blob/v11.0.0/README.md#all-options>`_
for further settings.
