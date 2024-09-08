# Intro to Git and GitHub
## A guide to version control for students
### Introduction
Over the course of a programming project, you've likely created several different versions of your program. As you've probably experienced, it can be difficult to keep track of the different versions of your project with naming schemes alone. Today, you'll learn a better way to handle versioning than naming the latest copy of your project `Project Final v2`. 

This guide introduces two version control tools – Git and GitHub. These are widely used by programmers, from students like yourself to professional software engineers in the tech industry. One simple form of version control that you might already be familiar with is in applications like Google Docs or Google Slides, which track edit history and allow the naming of discrete versions of documents. Version control systems like Git have a steeper learning curve than these tools, but are much more powerful.

By the end of this guide, you should have a basic idea of how to utilize Git, and GitHub for your programming assignments. You'll also learn how to use these tools to work effectively in a team environment, and find out why so many professionals choose Git for collaborative coding. You'll install Git and GitHub Desktop on your computer to prepare for your future assignments, and you'll learn how to use GitHub Desktop to complete an assignment from GitHub Classroom.

Also provided are supplementary resources and suggested next steps. If you've been given an assignment on GitHub Classroom based on this repository, ask your instructor about the completion criteria for the assignment. 

### Text editors
Before installing Git, you should ensure a suitable text editor is installed on your machine. By default, Git uses `vi` or Vim as its default text editor. If you are not already familiar with `vi` or its derivatives, you should install a suitable replacement. [Visual Studio Code](https://code.visualstudio.com/download) is recommended since it is cross-platform, extensible, and supports nearly any programming language with the right extensions.

## Git 
Git is a free, fast, and open-source distributed[^1] **Version Control System (VCS)**. A VCS is a tool for tracking changes to files over time. With Git, you can easily track changes to your code over time, so that you always have a record of what you've worked on and can revert to an older version if something breaks. Git also has powerful tools for collaboration and parallel development. 

By creating a Git *repository*,[^2] you can record changes to your project as *commits*, which include information like a timestamp and description. When looking back on a commit, Git shows exactly what changes were made in the *diff* format, which provides you the ability to easily compare two files by highlighting the changes between them. Additionally, you can work on multiple features simultaneously by using *branches*, which are essentially parallel tracks of development on a project.

[^1]: With Git, "distributed" essentially means that each contributor to a project has a full copy of the project, including all its history. So not only do you have redundant *distributed* backups, but the full history also helps when contributors try to change the same code (more on this later).

[^2]: A repository is basically the Git term for a project - more on this later.

## GitHub :octocat: 
GitHub allows hosting and sharing Git *repositories* (like this one). It's an easier way to use Git and also provides additional features like GitHub Organizations and GitHub Classroom. Many teams, developers, and open-source projects use GitHub to organize their collaboration efforts. As a student, you'll find it useful for group projects - as a service designed specifically for programming, it's much easier to code collaboratively using GitHub than with alternatives like sharing zip files of your project through Dropbox or Google Drive.

To use GitHub, you’ll need to [create an account](https://github.com/signup). As a student, you should create an account using your professional or university email, if you haven’t already.

## Installing Git
To get started with Git and GitHub, you'll need to install Git on your computer. If you're using a university lab computer, Git may already be installed. You can check if Git is installed by running the following command (on any OS): `git --version`. If you don't have terminal or command prompt access, try searching from your Start Menu (Windows) or use Finder (Mac). If you have Git installed, you can proceed to installing GitHub Desktop in the next section. Otherwise, follow the steps below:

1. Navigate to the [Git download portal](https://git-scm.com/downloads).
2. Download the appropriate version for your device's operating system. ![Git Install Page](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/b4c54b3c-ace7-4d79-a8f5-4c160016576d)

3. Once downloaded, run the Git installer. 
4. Navigate through the installation wizard. 
	- You may want to add a desktop icon, if applicable.
	- **If you do not already know how to use `vi` or Vim, change the default editor from `vi`/Vim to another editor installed on your machine.** Again, Visual Studio Code is recommended.
		- If installing Git from a visual installer (such as the Git for Windows installer), one page of the installer should prompt you to change this.
		- If installing Git from the command line, you may have to modify its settings manually with the command `git config --global core.editor "code --wait"`.
	- If prompted to choose a default branch name, `main` is currently recommended by GitHub. If you have previous VCS experience, you can choose a name you are familiar with, or just leave it as the default.
	- Otherwise, most default settings should be fine to leave as is.

Once the installer is complete, you can proceed to the next section. If you're having trouble installing Git, ask your instructor for assistance, or try consulting [this documentation page](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

## Installing GitHub Desktop
At its core, Git is a command-line utility. Using a graphical interface like GitHub Desktop makes using Git much easier. GitHub Desktop also allows easy management of and contribution to repositories hosted on GitHub. This guide will cover usage of Git through GitHub Desktop to contribute to repositories, such as assignments from GitHub Classroom. To install GitHub Desktop, follow the steps below:

1. Navigate to the [GitHub Desktop download portal](https://desktop.github.com/).
2. Again, download the appropriate version for your device and OS. ![GH Desktop DL Page](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/be204228-764c-40e0-b876-a78cea2a90b1)

3. Once downloaded, run the installer. You'll be prompted to sign in to your GitHub account. ![GitHub Desktop Installer](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/3e4f5212-c3d5-47e9-aabd-4b563c2bfa59)

4. Once you've logged in, you'll be asked to configure Git with the username and email that you prefer to use. You can also use the email associated with your GitHub account (which should be your professional or university email). Alternatively, you can allow GitHub to automatically generate an email that keeps your personal email private.
	- The email provided is associated with changes you make so that others can contact you about them if need be. Displaying your university email may make it easier for instructors to identify you.

At this point, the installation should be complete, and you can move on to the next section.

### Setting your default editor
Optionally, you can set the default editor or IDE in GitHub Desktop. When on the main page of a repository, GitHub Desktop will offer to open the repo in this editor, like so:

![GitHub Desktop Preferred Editor 1](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/23ae5b3e-cdbf-434f-9df1-04072671ca74)

If you wish to use a different editor than the one shown by your GitHub Desktop instance, you can change this as follows:

1. Click `File` on the top bar at the left.
2. Click `Options...`, then `Integrations` (second tab down on the left)
3. From here, you can select your preferred editor from a dropdown showing all supported editors installed on your device. ![GitHub Desktop Preferred Editor 2](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/eab1ec29-bd54-4865-8c69-24dc34fbd453)

4. You can also select your preferred shell from this menu if you are familiar with the terminal, but this guide will not use it.

### Two-factor authentication
You are strongly encouraged to enable two-factor authentication on your GitHub account. You can follow [GitHub's instructions here](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication) to do so.

#### GitHub mobile app
GitHub provides a mobile application that can be used as a second factor of authentication, and also for certain actions you will learn about shortly (issue and pull request management, mostly). You may optionally install the app if you would like to have an additional sign-in method.


## Git and GitHub Terminology
### Repositories
A repository, or repo for short, is basically the folder housing your project and all the relevant code. On your computer, your *local* copy of a repository is a folder which you've set up Git in. On GitHub, a *remote* copy of your repository is housed under your account [dashboard](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-personal-account-settings/about-your-personal-dashboard). You can work alone on a project or invite others to collaborate with you. Later, you'll learn how to create and manage repositories. [Learn more about repositories here](https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories).

#### A popular open-source repository on GitHub
![GH Guide Repo](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/022c5243-307f-470c-ae09-2f234445e632)


### READMEs and Markdown
In addition to code, repositories usually contain a file named `README.md`, like this one. A `README` is typically used to summarize your project or provide usage instructions. If a file named `README.md` is present in a repository uploaded to GitHub, it will be displayed on the main page of your repository.

You may have noticed the `.md` extension - this stands for Markdown, a markup language (similar to HTML) that allows you to easily format your `README` and other areas on GitHub. [Learn more about using Markdown on GitHub here](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Cloning
When you create a repository on the GitHub website or if someone else created the repository, you won't have a local copy on your machine. This will also be the case for assignment repositories created by GitHub Classroom. Once you've navigated to a repository on the GitHub website, you can *clone* it to create a local copy on your computer as follows: 

1. On the repository page, click the green Code button: ![GH Guide Cloning 1](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/a938b6d7-1df1-4975-bb53-0b86d4f13d0d)

2. Then, open the repo in GitHub Desktop: ![GH Guide Cloning 2](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/c9832014-331f-4fde-9f6d-3a7ac0bb5812)

3. You may have to accept a prompt from your browser to open a link with GitHub Desktop. Once it opens, you can choose a directory to clone the repository into. You should pick a folder you'll remember where you can organize your repositories. ![GH Guide Cloning 3](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/0fb30c58-d731-4ed3-a454-755bbd2dbcdc)

4. Finally, press Clone, and wait for the repository files to download. Once complete, you can begin making changes.

[Learn more about cloning here](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/cloning-a-repository-from-github-to-github-desktop).

Alternatively, if you know the name of the repository you want to clone, you can also clone directly from GitHub Desktop by [following this documentation page](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/cloning-and-forking-repositories-from-github-desktop).

### Commits
A Git *commit* is a "snapshot" of the repository at a specific point in time. A commit is also a set of differences, or *diffs*, from the last commit. You can also think of a commit as a list of changes that have been made. For instance, when you create a project, your "initial commit" might be to add a `README.md` file. In this case, the *diff* is relative to an empty project - you've added the entire file. But if you make another commit changing only one line in your `README`, the commit will only reference that specific line. This is how the history of a repository is structured - as a set of commits over time. 

Commits are accompanied by a message and, optionally, a description. If you're changing more than a few lines of code, you should write a description that tells others what you changed in the commit. Then, briefly summarize your changes in the commit message. Commits also record a timestamp (when the changes were made) and an author (who made the changes). [Learn more about making commits here.](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/committing-and-reviewing-changes-to-your-project-in-github-desktop)

You should make commits frequently to save your work. Making commits often makes it easier to describe what you've done in the commit message and description, since there are fewer changes to summarize. In GitHub Desktop, you can select certain files or even certain lines of code to be included in a commit. This allows you to make more granular commits. To select all changes for the current commit, check the highlighted box below.

![GH Guide Commits 1](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/b5e18ede-82ce-43af-a07a-5532919cde78)
![GH Guide Commits 2](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/7f8bbdc2-826d-40f9-9584-7cfe79e489d4)

You can also discard unwanted changes by right-clicking (or an equivalent action for your OS) on a file that has been changed, and selecting "Discard Changes" or "Discard Selected Changes." You can press `Shift` to select multiple changes.

[Learn more about commits here](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/committing-and-reviewing-changes-to-your-project-in-github-desktop).

### Pushing, Fetching, and Pulling
Once you've made changes, you'll need to *push* them to the remote repository on GitHub. This is how you update the remote repo so that your teammates or instructor can view your changes. 

Before you can push any changes, GitHub Desktop will *fetch* updates from the remote repository. This tells Git if changes have been made to the remote version since you last fetched. If there are changes, you must *pull* them and update your local copy before pushing your changes. If the changes on the remote conflict with your changes, you'll have to resolve them - this is known as a *merge conflict*. More details on that soon.

[Learn more about pushing, fetching, and pulling here](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/pushing-changes-to-github-from-github-desktop).

### Branches
A branch is an independent line of development in a repository. You can decide to "branch off" from a specific commit. Then, you can safely make changes, fix bugs, or experiment with new features on a working copy of your repository separate from your `main` branch.[^3] Once you're done making changes, fixing bugs, or developing a new feature, you can *merge* the branch back into the `main` branch. 

The most important usage for branches is collaboration. Since branches are independent from their origin, you and your teammates can each work on a single feature in your own separate branches, then merge back into `main` when you're done. 

Best practice is to create a new branch for any non-trivial change. If you're updating one line in the README or fixing a comment typo, there's no need to create a new branch. However, rewriting a function or reworking an entire class merits the creation of a branch. [Learn more about branching here](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/managing-branches-in-github-desktop).[^4]

![Git Branching Atlassian](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/a055c26d-d897-48e2-9704-a3db647b8e51)


#### Merge Conflicts
If there have been changes to the `main` branch since you created the new branch, you may encounter a *merge conflict*. This occurs when Git can't automatically merge commits because they change the same lines of code. Merge conflicts require manual resolution. GitHub Desktop has a straightforward UI for merge conflict resolution that appears when it detects a merge conflict. You must choose to either keep one set of changes or manually resolve the conflict - perhaps by combining the changes. [Learn more about resolving merge conflicts here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github).

![Git Merging Atlassian](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/dcbd5c4d-35ab-4654-af57-9a71154e71f8)



[^3]: The original branch of a GitHub repository is typically called `main` (the default) or similar.

[^4]: Images in this section from https://www.atlassian.com/git/tutorials/using-branches and https://www.atlassian.com/git/tutorials/using-branches/git-merge. These are helpful resources, but use Git from the command line, so they aren't particularly applicable to this tutorial.

### Pull Requests
While it is possible to merge a branch directly, when collaborating on a project, you should first consult your teammates and ask them to review your changes. When finished working on a branch, you can create a *pull request* to discuss the changes with collaborators and fix any issues before merging into `main`. Once your teammates agree that your changes are good, you can merge them into `main`, close the pull request, and delete the branch.

You can create a pull request either from GitHub Desktop or from the repository homepage. The former is often easier, as GitHub Desktop will prompt you to preview a pull request once you've pushed changes on your branch to the remote copy of the repository.

![GH Guide PR](https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/760acf48-69c3-42e0-9887-d6f6acec46f8)

When creating a pull request, be careful to ensure that you are merging the correct source branch (the one you were working on) into the appropriate destination branch (usually `main`). [Learn more about pull requests here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests).

### Issues
Issues are a way to track enhancements, tasks, or bugs related to your repository and project. On the GitHub website, you can open an issue from the Issues tab of your repository. This is especially helpful for larger or open-source projects, but you can also use it for group projects. [Learn more about issues here](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues).

## Using GitHub Classroom
### Accepting assignments
- Your instructor will provide you with a link to each assignment via one of the following mediums:
	- your class's GitHub Organization
	- your learning management system (Canvas, Moodle, Google Classroom, etc.)
	- email
- It is not recommended to accept assignments from your mobile device, since GitHub Classroom's interface is not fully compatible with mobile devices.

### Joining your classroom's GitHub Organization
- Your instructor will have prepared a GitHub Organization to house materials relevant to the course (ex. a syllabus or example code) and your programming assignments.
	- Once you accept an assignment via the link provided by your instructor, a repository will be automatically created for you (or your group).
		- You can view your copy of each assignment from the `Repositories` tab of your class's GitHub Organization.
	- Essentially, the GitHub Organization mostly contains code for assignments and projects, while lecture materials will most likely be provided via your learning management system (Canvas, Moodle, Google Classroom, etc.) if applicable.
- When you accept your first assignment, you should automatically receive an email inviting you to join your classroom's GitHub Organization.
	- Follow these instructions alongside your instructor's direction so that you can access the appropriate class materials.

### Completing assignments
- To complete assignments from GitHub Classroom you will need to utilize Git and GitHub as detailed in this guide.
- For additional assistance, see the video below ([available for download here](./First%20Assignment%20Tutorial.mp4)).

https://github.com/rzn-example-classroom/git-and-github-intro/assets/16062019/20494780-e636-46f1-bc09-1f8459ffbba8

### Submitting assignments
- **There is no "submit button" in GitHub Classroom. Assignments will only appear as "submitted" to your instructor or TA(s) once a commit has been pushed to the repository.**
	- Thus, remember to save your work by creating and pushing commits often. Make sure to use a descriptive message.

## Recommended Next Steps
* Create a new markdown file in this repository summarizing what you've learned. Try experimenting with markdown formatting and styling.
* Create a new repository from your user dashboard. Try cloning the repo and adding a `README.md` or a simple Hello World program.
* Sign up for the [GitHub Student Developer Pack](https://education.github.com/pack) - it gives free GitHub Pro and many other benefits from various partner companies.

## Resources 
* [A short video explaining what GitHub is](https://www.youtube.com/watch?v=w3jLJU7DT5E&feature=youtu.be) 
* [Git and GitHub learning resources](https://docs.github.com/en/github/getting-started-with-github/git-and-github-learning-resources) 
* [Understanding the GitHub flow](https://guides.github.com/introduction/flow/)
* [How to use GitHub branches](https://www.youtube.com/watch?v=H5GJfcp3p4Q&feature=youtu.be)
* [Interactive Git training materials](https://githubtraining.github.io/training-manual/#/01_getting_ready_for_class)
* [GitHub's Learning Lab](https://lab.github.com/)
* [Education community forum](https://education.github.community/)
* [GitHub community forum](https://github.community/)
* [GitHub Student Developer Pack](https://education.github.com/pack)
