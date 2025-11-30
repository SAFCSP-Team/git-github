# GitHub Collaboration 
Collaboration means working together to build, improve, and maintain code or content. On GitHub, collaboration is at the core of every project, enabling teams to contribute, review, discuss, and deploy code from anywhere in the world.


### Collaboration Workflow


![This is an example image](images/Git-steps-cards_1.jpg)
![This is an example image](images/Git-steps-cards_2.jpg)


## Inviting People and Setting Roles
You can invite others to collaborate on your repositories, and each person can have a specific role:    
**Owner**: Full administrative access to the repository or organization.   
**Collaborator**: Can push to branches and manage issues/pull requests.   

This is an example of a project we are going to invite collaborators to
![This is an example image](images/01-project-page.png)


### How to Invite Collaborators
1. Go to your repository on GitHub.
2. Click on Settings → Collaborators.
![This is an example image](images/02-how-to-invite-01.png)
3. Enter the GitHub username or email and send an invite.
![This is an example image](images/03-how-to-invite-02.png)
![This is an example image](images/04-how-to-invite-03.png)
4. Assign a role to the invited collaborator, then click the **Add selection** button.
![This is an example image](images/05-how-to-invite-04.png)
You can find the invited collaborator on the list with the role assigned to him.
![This is an example image](images/06-how-to-invite-05.png)







## Forking a Repository
A fork is a personal copy of someone else's repository on your GitHub account that allows you to experiment with changes without affecting the original project. You can submit your improvements back to the original project using a pull request.

### How to Fork
1. Click the Fork button at the top right of a repository page.
![This is an example image](images/07-how-to-fork-01.png)
2. Click Create fork
![This is an example image](images/08-how-to-fork-02.png)
You can find this message on your forked repository, it informs you whether you are up to date with the main repository or not. If you are not up to date, you can click the **Sync** button to fetch the last update. **Contribute** button allows you to open a pull request.
![This is an example image](images/09-how-to-fork-03.png)




## Issues 
Issues are GitHub’s way to track **tasks**, **bugs**, **feature requests**, or **questions**. Anyone can open an issue to report a bug or suggest enhancements. Issues can be **assigned**, labeled, and discussed to facilitate project management and collaboration.


### How to Create an Issue 
Assign a task to a collaborator by creating an issue.

1. Click on the issue button at the top.  
![This is an example image](images/10-how-to-issue-01.png)
2. Click **new issue**
![This is an example image](images/11-how-to-issue-02.png)
3. Add a **title**, **description** and an **assignee** who will be responsible for this task.
![This is an example image](images/12-how-to-issue-03.png)



## Making Commits
A commit is a snapshot of your changes, with a message describing what you did. Each commit should be focused and clearly described to help collaborators understand the changes.

### How to Commit
The collaborator wants to add an `index.html` file to the forked repository.

1. After adding the changes, click on **Commit changes**.
![This is an example image](images/13-changes-pull-01.png)
2. Add a **Commit message**, then click **Commit changes**.
![This is an example image](images/14-changes-pull-02.png)


## Pull Requests  
A pull request (PR) is how you propose changes from your branch or fork to the original repository. Pull requests show a “diff” of what you've changed and initiate discussions, feedback, and reviews before merging.

### How to Create a Pull Request
1. Push your changes to GitHub.
After pushing the changes, you can see the message "1 Commit ahead" of the main repository.
2. Click on **Contribute**.
![This is an example image](images/15-changes-pull-03.png)
3. Click on **Open pull request**
![This is an example image](images/16-changes-pull-04.png)
4. Add **title**, **description**, and a **reviewer** who is a collaborator and will be responsible for reviewing your changes.
![This is an example image](images/17-changes-pull-05.png)




## Code Review
Ensuring Quality.    
Code review is an integral part of the pull request workflow. Team members can review the code, add comments, suggest changes, and approve or request more changes.


### Example 
1. After requesting a pull request and assigning a reviewer to it, a timeline will appear providing information about any updates regarding it.
![This is an example image](images/18-changes-pull-06.png)

2. The reviewer can highlight a specific line of code and add a comment on it.
![This is an example image](images/19-review-01.png)
3. The reviwer can add **comment**, **approve** or **request a change** from the collaborator.
![This is an example image](images/20-review-02.png)
4. The collaborator can view the reviewer-requested change from the pull request timeline.
![This is an example image](images/21-review-03.png)
5. The collaborator then makes the requested changes, commits, pushes the changes, and waits for the reviewer updates. The reviewer approves the changes.
![This is an example image](images/22-review-04.png)
6. Merge the approved updates to the main repository.
![This is an example image](images/23-review-05.png)
![This is an example image](images/24-review-06.png)



## GitHub Actions
GitHub Actions lets you automate tasks directly from your repository. 

### Components

You can set up a GitHub Actions **workflow** to trigger when specific **events** happen in your repository, such as opening a pull request or creating an issue. Each workflow consists of one or more **jobs** that can execute either sequentially or in parallel. Each job runs in its own virtual machine **runner** or within a container and comprises several steps. These steps can either execute a script that you define or utilize an **action**, which is a reusable extension designed to streamline your workflow.

![This is an example image](images/27-workflow-01.jpg)


### Workflow
A workflow is an automated process that can execute one or more jobs and is configurable to suit your needs. Workflows are defined in a **YAML file** stored in your repository and can be triggered by specific events, manually, or based on a predetermined schedule.

These workflows are located in the `.github/workflows` directory of a repository. A single repository can contain multiple workflows, each capable of executing a different set of tasks, such as:

- Building and testing pull requests.
- Deploying your application whenever a new release is created.
- Adding a label whenever a new issue is opened.



### Example
Create a workflow that checks for file names length to be less than 20 characters.
![This is an example image](images/28-workflow-02.jpg)



1. Create a YAML file named `check-file-name` inside a `.github/workflows` directory.

![This is an example image](images/25-workflow-example-01.png)

2. YAML file content


```yaml
name: Check File Names
```
**Purpose:** This line sets the name of the workflow as "Check File Names." This name will be displayed in the GitHub Actions interface.


```yaml
on: 
  pull_request:
```
**Trigger:** This specifies that the workflow should run when a **pull request** event occurs. This includes **events** like opening, editing, or reopening a pull request.


```yaml
jobs:
  check-file-names:
```
**Job Definition:** This begins the definition of a job named `check-file-names`. Jobs are sets of steps that execute on the same runner.

```yaml
    runs-on: ubuntu-latest
```
**Environment:** This indicates that the job will run on the latest version of Ubuntu available in GitHub Actions. It specifies the operating system environment for the job.

```yaml
    steps:
```
**Step Declaration:** This indicates that a sequence of steps will follow. Each step will perform a specific action.

```yaml
    - name: Checkout code
      uses: actions/checkout@v2
```
**Checkout Step:** This step checks out the repository code so that the workflow can access it. The actions/checkout@v2 action is used, where @v2 specifies the version of the action.

```yaml
    - name: Check for file name length
      run: |
```
**File Name Check Step:** This step is where the actual checking of file names will take place. The run: command allows you to specify a shell command to execute. The | indicates that a block of script is following.

```bash
        echo "Checking file names for length..."
```
**Output Message:** This line prints a message to the console, indicating that the file name length check process has started.

```bash
        files_exceeding_limit=$(git diff --name-only ${{ github.event.before }} ${{ github.sha }} | awk 'length($0) > 20')
```
**File Length Check:** This line checks for file names that exceed a length of 20 characters.    
`git diff --name-only ${{ github.event.before }} ${{ github.sha }}`: This command gets the names of files that have changed between two commits (the previous commit and the current commit).    
`awk 'length($0) > 20'`: This filters the list of file names to include only those whose length exceeds 20 characters.
The result is stored in the variable `files_exceeding_limit`.
```bash
        if [ ! -z "$files_exceeding_limit" ]; then
```
**Check Variable:** This line checks if the files_exceeding_limit variable is not empty (i.e., there are file names exceeding the length limit).
```bash
          echo "Error: The following files exceed 20 characters in their names:"
```
**Error Message:** If there are file names that exceed the specified length, this line prints an error message notifying the user.

```bash
          echo "$files_exceeding_limit"
```
**List Exceeding Files:** This line prints the list of files that exceed the 20-character limit.

```bash
          exit 1
```
**Exit with Error:** This command causes the script to exit with a status code of 1, indicating that there was an error (due to the file name length issue). This will cause the workflow to fail.

```bash
        else
          echo "All file names are within the limit."
        fi
```
**Success Message:** If there are no file names exceeding the length limit, this part of the code prints a success message. The fi indicates the end of the if statement.

3. Make a pull reuqest with a new file added to the repository named `documentation` which consist of 13 characters.

The workflow is trggered by the pull request event, checks the file name and finds no error.
![This is an example image](images/26-workflow-example-02.png)


#### Official GitHub Documentation:


- [GitHub Actions Documentation](https://docs.github.com/en/actions): A comprehensive resource that covers everything about GitHub Actions, including getting started guides, workflow syntax, and configuration options.

- [Workflow Syntax for GitHub Actions](https://docs.github.com/en/actions/reference/workflows-and-actions/workflow-syntax): Detailed information on how to write workflow YAML files, including examples and options.- Creating Actions:

- [Creating Actions](https://docs.github.com/en/actions/how-tos/reuse-automations): Learn how to create your own custom actions to reuse in workflows.
