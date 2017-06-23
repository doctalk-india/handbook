# Release
- After a feature branch's pull request is merged back into develop and the app is ready for an update, create a new release branch.
- Bump the version number on this branch and test the app thoroughly.
- On android
    - Generate the signed APK.
    - Test the signed APK.
    - Upload to play store.
- Tag the release branch as the version number and jot down the release notes as the description. [git flow takes care of the tag, but not the description]
- After the app is uploaded to the store, merge the release branch into master using git flow.

Some useful git commands when releasing an update:
```sh
$ git flow release start [version-number]
# Bump version number and do your final testing before release.
$ git flow release finish [version-number]
$ git push --tags
```
PS: Version number should always follow the following format:    **[major-version].[minor-version].[build]**
