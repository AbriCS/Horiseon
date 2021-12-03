### 11. Everyone Do: Git (20 min)

* Students have already reviewed the basics of creating a remote repository on GitHub as well as commonly used Git commands. This Git activity will focus on configuring the local Git default branch to `main`, using `git init` to create a local repository, and reviewing the `git pull` command (because they will use it frequently to pull down the class repository before every class).

* Open [Git Basics—Getting a Git Repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository) in your browser and explain the following:

  * Git is an important tool that allows developers to track and store versions of content. Using a Git repository, we can save different versions of a project's code.

  * Creating a repository is an important part of the development process and should be done each time you start a new project.

  * We can create a repository and use it on a local machine in two ways&mdash;we can create the remote repository on GitHub first and then use `git clone` to clone it onto the local machine, or we can turn a local directory or project and into a Git repository using `git init`.

  * We already covered how to clone a remote repository, so today we will learn how to turn an existing local project into a Git repository.

  * But first we will need to configure the local Git default branch to `main`.

* Direct students to the activity instructions found in `21-Evr_Git-Guide/README.md`.

* Open your command line and demonstrate the following:

  * 🔑 Before you begin, you need to ensure that the default branch is `main`. If you have not done so yet, follow the instructions in the Git Guide and use `git config` to make that switch. If you have any issues, ask a TA for help or stay for office hours:

    ```bash
    git config --global init.defaultBranch main
    ```

* Open your command line and demonstrate the following:

  * Alternatively, we can use `git init` to create a repository. The results will be similar to if we used `git clone`, except that we start by creating a repository locally via the command line.

  * 🔑 Start by creating a new project directory named `git-init-sample` on your local machine. Ideally, you should store all of your coding projects for this course in a parent directory. Create this project directory inside that parent directory:

    ```bash
    mkdir git-init-sample
    ```

  * We use `cd` to navigate into new project directory and `touch` to add an `index.html` file:

    ```bash
    cd git-init-sample
    touch index.html
    ```

  * To initialize this folder as a Git repository, we will use `git init`&mdash;we need to be in the project folder when we run this command!

    ```bash
    git init
    ```

  * This creates a new subdirectory named `.git` that contains all of the necessary repository files&mdash;a Git repository skeleton.

  * To start version-controlling the existing files in the project, we need to start tracking those files and do an initial commit.

  * First let's run `git status` to check the status of the files:

    ```bash
    git status
    ```

  * We should see that `index.html` is currently untracked. Let's stage that file for commit:

    ```bash
    git add -A
    ```

  * Now if we run `git status` again, we should see that the file is being tracked and is ready to be committed:

    ```bash
    git commit -m "initial commit"
    ```

  * 🔑 Using `git init` adds version control locally to a project, but it doesn't create a remote repository. Let's do that now.

* Open [GitHub](https://github.com/) in your browser and demonstrate the following:

  * Click on the New button to create a new repository.

  * Enter the same name as the local repository, `git-init-sample`.

  * 🔑 Do not check any of the boxes, because we are importing an existing repository!

  * Click the Create Repository button.

  * Copy the code under the header "…or push an existing repository from the command line".

* Open your command line and demonstrate the following:

  * Back in your project directory, paste the commands copied from GitHub. This will sync your local repository with the repository that you just created on GitHub.

* Open the `git-init-sample` repository on GitHub in your browser and demonstrate the following:

  * The repository has been updated on GitHub!

* Open your command line and demonstrate the following:

  * You will need to pull down the class repository before each class in this course to have that day's activities ready.

  * To perform a `git pull`, first navigate to the project directory using `cd`:

    ```bash
    cd git-init-sample
    ```

  * Next, use `git pull` to pull down the changes from the remote. Just like when we did a `git push`, we use `origin` to represent the original directory&mdash;or more precisely, the original repository's URL&mdash;followed by the name of the branch, which is `main`:

    ```bash
    git pull origin main
    ```

  * You can view any changes by opening the project directory in VS Code.

* Answer any questions before students go on break.