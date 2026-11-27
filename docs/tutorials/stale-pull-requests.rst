Review a stale pull request
===========================

This tutorial walks through an alert using the repository's existing workflow.
You need access to the repository's Actions tab and an open pull request that
has been inactive for at least 30 days. Running the workflow affects all
eligible pull requests, not just the one you choose.

1. Once the workflow is on the default branch, open **Actions** and select
   **Alert on stale pull requests**.
2. Select **Run workflow** and run it on the default branch. The workflow also
   runs daily without manual intervention.
3. Open the completed run and inspect its logs. If it reaches the operation
   limit, another run may be needed to process the remaining pull requests.
4. Open an eligible pull request. The workflow adds the ``stale`` label and
   posts a comment asking for a review. It does not close the pull request.
5. Add a meaningful update or comment. On a subsequent run the action can
   remove the stale label. A new period of inactivity can result in another
   alert.

If there is no eligible pull request, wait for one to reach the threshold.
Commenting merely to test the workflow resets its inactivity timer. See the
:doc:`how-to guide </how-to/stale-pull-requests>` to adjust recipients or
exemptions.
