# Why GitHub?

GitHub has many benefits when used in conjunction with our courses, including providing our members the ability to fork repositories as a starting point for their own projects, the opportunity to comment and leave feedback, and the chance to submit pull requests to report bugs or issues. In addition, instructors can promote and link to their courses through GitHub, interact with members, and enjoy a more streamlined exercise file workflow, where files are easier to update, and starting and ending states can be created more efficiently.   

# What’s Changing?

GitHub has historically been used by many Lynda.com/LinkedIn instructors through their personal GitHub accounts. However, we now have available a LinkedIn Learning [organization account](https://github.com/LinkedInLearning) where instructors can post their course-related repositories. The organization account will allow us to present a consistent brand to the public, as well as maintain central control of all course-related repositories. As a general rule, all instructors, staff and non-staff, will be encouraged to use only the organization Github account in their courses.

# How Do I Participate?

The Assets team will maintain the LinkedIn Learning Github account, including creating repositories, and inviting instructors, via their personal Github accounts, as outside collaborators. To ensure the process works efficiently, please use the instructions outlined here to participate in the LinkedIn Learning Github organization.

To initiate creation of a course repository on the LinkedIn Learning organization account, please send a request to ldc-prod-assets@linkedin.com and include the following information:

1. Course Name:
1. Course ID:
1. Date repo required
1. Preferred name of repo
1. Instructor’s personal GitHub account name, so instructors can be invited as a collaborator.
1. Producer’s personal GitHub account name.
1. Accept the invite from the LinkedIn Learning organization, and begin posting to your repository. Make sure to create a README file, since Admins will not create any content in your new repo.

Please note, that supplying files via GitHub is not a substitute for including the exercise files on LinkedIn Learning and Lynda.com.

# Production flow

For every course, follow the current production flow to ensure consistency and sanity of the course repository:

## Preparation
0. **Producer + Instructor** Select the appropriate license for the project. The standard license for all LinkedIn Learning course assets is BSD 2 (see [LICENSE](https://github.com/LinkedInLearning/prototype/blob/master/LICENSE). If a [copyleft](https://en.wikipedia.org/wiki/Copyleft) license such as GPL is required, consider split licensing: Copyleft for parts that require such licensing, BSD 2 for everything else.

1. **Producer:** On repo creation, make sure all template assets are present and accounted for (eventually README.md template, ghpages, pull request template, etc).

2. **Instructor:** Fork repo to personal GitHub account. Use personal fork for course development.

## Course recording (instructor)
This procedure should give you a branch structure where the master branch holds the final state of the exercise files and each movie has its own branch off master with each branch holding a sub-branch with the end state of the current movie.

1. Clone personal repo to recording computer.
1. Create and commit README.md file based on template.
1. In the master branch, add files as required for the starting point of the first movie with exercise files for the movie you are currently recording.
1. Commit starting point to master branch.
1. Create branch for the current movie. Branch name will be in the format XX_YY format where XX is chapter number and YY is movie number, so chapter 2 movie 3 has the branch name 02_03.
1. Checkout movie branch.
1. Record movie as normal.
1. If recording is successful and exercise files are complete, create new branch off the current movie branch with the name XX_YY_e.
1. Commit end state to the END branch.
1. Checkout master branch.
1. Merge XX_YY_END branch with master branch.
1. Return to step 5 for the next movie.

## Record complete (instructor)
1. Push finished exercise file branches to personal GitHub repo.
1. Create and submit pull request (follow pull request template) to the Organization repo.
1. Change context to the Organization and accept your own pull request to take the exercise files live.
1. Inform producer that exercise files have been added to the Organization repo.

## Record complete (producer)
1. Verify integrity and completeness of files in Organization repo, including all branches.
1. Verify information in README.md.
1. Communicate any necessary changes to instructor for updates or make basic updates (README.md typos etc) directly in the repo.
1. Download zip of repo (all branches) to be compiled for product course page.

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
