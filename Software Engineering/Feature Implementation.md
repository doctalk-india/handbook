# Feature Implementation
Before writing even a single line of code, write down a brief description of the implementation details [**here**](https://docs.google.com/document/d/1ahK49ZzXtsa4m46LNJYtGWgtdGy6_qvbYjlMei_XKr8/edit). This is the pre-implementation documentation.
  - Everytime a new feature is being built, branch out of develop to create a new feature branch. **No changes should be ever committed directly to the develop branch.**
  - Name the feature branch as following - **feature/DOC-[jira issue number]_[feature name]**
  - For each subtask create a new branch out of the just created feature branch and name it **subtask/[name]/DOC-[jira_sub_task_number]-[sub_task_name]**
  - Keep committing logical pieces of code once you are done working on them. This should become a regular practice rather than committing large chunks at one go.
  - Prefix every commit with **DOC-[jira_subtask_number]**
  - After the sub task has been completed thoroughly tested create a pull request to merge it back into the feature branch
  - After feature development is complete and thoroughly tested create a pull request to merge back into develop.
  - While creating the pull request, assign atleast one reviewer to request for a code review.
  - When you are requested to do a code review, it **must** be done within **24hrs**, if not earlier.
  - When working with firebase always log the listeners and make sure the events being triggered are what you expect them to be.

After implementing a feature, revisit your pre-implementation documentation and add post implementation notes reflecting any changes in the prior and also document the firebase events being triggered.

Some useful git commands when working on features:
```sh
$ git flow feature start [feature-name]
$ git request-pull <start> <url> [<end>]
```
