# Releases

## Android
- After a feature branch's pull request is merged back into develop and the app is ready for an update, create a new release branch.
- Bump the version number on this branch and test the app thoroughly.
- On android
    - Generate the signed APK.
    - Test the signed APK.
    - Upload to play store.
- Tag the release branch as the version number and jot down the release notes as the description. [git flow takes care of the tag, but not the description]
- After the app is uploaded to the store, merge the release branch into master using git flow.

Vijay is currently in charge of Android releases.


## iOS
* Make sure everything is ready on the develop branch.
* Check the build number in the project settings of XCode.
* Run `git flow release start [insert version number + 1 here]
* Once on the release branch, go into project settings and increase the version number. In most cases, you will be incrementing the patch number. Occasionally, the minor version and rarely the major version.
* Commit the updated build number.
* Now go to the GitHub repository. Start at the last merge of a release branch that was not a beta release branch.
* Look at all the major changes that users would understand and write them down line by line in release_notes.txt.
* Commit the release notes.
* Test all the features you saw.
* Fix any problems if necessary.
* Commit and push the branch.
* Run `fastlane release`
* Sit back and relax :)
* Once the release is done, run `git flow release finish [insert version number here]`

Sourav is currently in charge of iOS releases.


### Some useful git commands when releasing an update:
```sh
$ git flow release start [version-number]
# Bump version number and do your final testing before release.
# Make sure release notes are updated
$ git flow release finish [version-number]
$ git push --tags
```
PS: Version number should always follow the following format:    **[major-version].[minor-version].[build]**
