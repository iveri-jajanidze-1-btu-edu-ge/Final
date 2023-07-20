
what should this script do:

1. Check for changes on that branch every 15 seconds, process all new revisions in chronological order,
only once.
2. For each revision, run unit tests with pytest
2.1 Upload HTML report for pytest to GitHub pages
2.2 Find the exact commit which introduced unit tests fail and include this information into
GitHub issue
3. For each revision, check code style with black
3.1 Upload HTML report for black to GitHub pages
3.2 Find the exact commit which introduced code style check fail and include this information
into GitHub issue
4 If any of the checks failed, create a GitHub issue with detailed description of what happened
4.1 Include a link to failed commit in the GitHub issue text
4.2 Include links to pytest and black HTML reports in the GitHub issue text (requires 2.1 and 3.1)
4.3 Assign the GitHub issue to the author of the failed commit
5. If all the checks pass, mark the commit with a "${DEV_BRANCH_NAME}-ci-success" tag
6. If all tests pass, merge revision into ""${RELEASE_BRANCH_NAME}" branch
6.1 Create a GitHub issue if previous merge fails, include conflict information
7. Perform all tests for a single commit in parallel
