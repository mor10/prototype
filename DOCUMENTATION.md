# Why GitHub?

GitHub has many benefits when used in conjunction with our courses, including providing our members the ability to fork repositories as a starting point for their own projects, the opportunity to comment and leave feedback, and the chance to submit pull requests to report bugs or issues. In addition, instructors can promote and link to their courses through GitHub, interact with members, and enjoy a more streamlined exercise file workflow, where files are easier to update, and starting and ending states can be created more efficiently.   

# How Do I Participate?

To initiate a course repository, send an email to `ldc-prod-assets@linkedin.com`. Include the following information:

```
Course Name:
Course ID:
Repo Name:
Github Account Name:
Producer GitHub Account Name:
Instructor GitHub Account Name:
```

*Note:* The repo names should have an identifier, a short name (i.e. bootstrap4), a short identifier (i.e. esst for Essential Training) and the course id at the end. So a course for Bootstrap Essential Training with a course id of 123456 would have a name `bootstrap4-esst-123456`

Producer(s) and instructor(s) will be added as CODEOWNERS to the repo in the `./.github/CODEOWNERS` file.

Once the request is processed, you'll receive an invitation from the LinkedIn Learning organization. This repository will be an empty shell with only a basic README file.

1. Fork the repository you were invited to

1. Clone the forked repository to your hard drive

1. Go to [this repository](https://github.com/planetoftheweb/prototype) to download the repository template

1. Copy the files from the `prototype-master` folder into the cloned repository. You don't need to copy all of the files from the `prototype` repository, however you MUST copy at least these files:
  - LICENSE
  - NOTICE

*Notes:* 
- There are other template files that might be useful, so feel free to copy them if you need them for your project.
- Copying files from the desktop will not copy invisible files like the `.gitignore` file, so you may need to create those yourself or copy them manually.

# Production flow

For every course, follow the current production flow to ensure consistency and sanity of the course repository:

## Preparation
1. **Producer/Instructor** The standard license for all LinkedIn Learning course assets is BSD 2 (included in the prototype repository). If a [copyleft](https://en.wikipedia.org/wiki/Copyleft) license such as GPL is required, consider split licensing: Copyleft for parts that require such licensing, BSD 2 for everything else.

1. **Instructor:** Fork repo to personal GitHub account. Use personal fork for course development.

## Course recording (instructor)
This procedure should give you a branch structure where the master branch holds the final state of the exercise files and each movie has its own branch off master with each branch holding a sub-branch with the end state of the current movie.

1. `git add --all`
  In the master branch, add files and libraries as required for the starting point of the first movie with exercise files for the movie you are currently recording.

1. `git commit -m "MY FIRST COMMIT"`
  Commit starting point to master branch.
  
1. `git checkout -b "02_01"`
  Create and checkout a branch for the current movie. Branch name will be in the format XX_YY format where XX is chapter number with leading 0's and YY is movie number, so chapter 2 movie 1 has the branch name 02_01

1. `git checkout -b "02_01e"`
  Create and checkout a new branch for the finished version of the movie with the format XX_YYe (e means this is the end state for the current video)

1. Record movie as normal.

1. `git add --all`
   `git commit -m "RECORDED 02_01 SUCCESSFULLY"`
  If recording is successful and exercise files are complete, add all of the changes and commit them to the finished branch. Otherwise, you may use `git checkout .` to revert the files to their starting state and record again.

1. `git checkout master` 
  Checkout master branch.

1. `git merge 02_01e`
  Merge 02_01e with master branch.

1. Return to step 3 for the next movie.

1.  `git push --all`
  Push the finished branches to repo

## Record complete (instructor)

1. `git remote add upstream https://github.com/LinkedInLearning/YOURREPO`
Set up an upstream branch to the original repo

1. `git push upstream --all`
Makes sure finished branches are pushed to personal GitHub repo. You may do this sequentially as you work through each video `git push upstream 02_01`, etc. 

## Record complete (producer)
1. Verify integrity and completeness of files in Organization repo, including all branches.

1. Verify information in README.md.

1. Communicate any necessary changes to instructor for updates or make basic updates (README.md typos etc) directly in the repo. These may be edited directly in the repo as a pull request.

## Small update procedure (instructor)

1. For beta fixes before release and small changes that do not require course updates.

1. Perform upstream sync with Organization repo to ensure you are working with the latest version of the repo.

1. Make changes as necessary (**NB:** If a change is made in code in a movie and that code carries forward, all subsequent branches must be updated including the END branches.)

1. Update change log and version number.

1. Commit changes to the correct branch.

1. Push updates to personal repo.

1. Create and submit pull request to Organization repo.

1. Change context to the Organization and accept your own pull request.

1. Inform producer that exercise files have been updated.

1. **Producer:** Download new zips of affected branches and submit to product.


## Large update procedure (instructor and producer)


1. For post-release updates that have an impact on course content.

1. Discuss what updates need to be made and document what branches of the repo need to be updated.

1. Follow steps 1 through 5 of Small update procedure above.

1. **Producer:** Change context to the Organization and accept the pull request from the instructor.

1. Download new zips of affected branches and submit to product.

## Handling 3rd party pull requests (instructor and/or producer)

1. 3rd party pull requests should be regarded as unsafe by default and never accepted directly to the Organization repo. If a 3rd party pull request is deemed relevant, follow the procedure below:

1. Respond to the pull request in the Organization repo to gather information about the issue addressed, the person submitting the pull request, etc. Acknowledge receipt and outline further steps etc.

1. Perform upstream sync with Organization repo to ensure you are working with the latest version of the repo.

1. Pull pull request to local repo and check for validity. Assume code is unsafe until proven otherwise.

1. If pull request is sound, commit to local branch and perform updates to subsequent branches and end branches as required.

1. Push local changes to personal repo.

1. Update change log and version number.

1. Create and submit pull request to Organization app referencing original pull request.

1. **Producer:** Change context to the Organization and accept the pull request from the instructor.

1. Close original pull request with reference to accepted pull request from instructor to notify original contributor their request was accepted.

1. Download new zips of affected branches and submit to product.
