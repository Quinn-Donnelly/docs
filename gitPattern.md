# Git Pattern
The following is a discription of a git pattern that will minimize merge conflicts.

<!-- TOC -->

- [Git Pattern](#git-pattern)
    - [Setup](#setup)
- [Usage](#usage)
    - [I AM WORKING ON A FEATURE / FIX](#i-am-working-on-a-feature--fix)
        - [Steps to Begin](#steps-to-begin)
    - [UPDATE PROJECT](#update-project)

<!-- /TOC -->

## Setup

1. Navigate to the main [Trackforce repository](https://github.com/revaturelabs/trackforce) and fork it
    - The fork button is found in the top right.
    - Once you click it the fork will either begin immediately or show a popup prompting you to select an account to fork to. You should select your personal account if this happens.
        - This will only occur if you have multiple accounts on your Github account (ie. Organizations)
2. (This step should happen automatically) Once the repository has been forked navigate to the copy of the repository on your account page.
    - The URL will be the following
    - [https://github.com/{YOUR USERNAME}/trackforce]()

3. Clone this repository to your local machine
    1. On the right side of the file window there is a green button that says clone or download
    2. Copy this path and do the following
        1. Using a terminal navigate to the directory you would like to keep your projects in
        2. Clone the repository using the path you have copied
            ```sh
            git clone {PATH}
            ```
    3. Verify this worked
        1. In the directory you have just run git clone in there should now be a trakforce folder
        2. Navigate into this folder
            ```sh
            cd trackforce/
            ```
        3. Check that the git repository is pointing to your copy
            ```sh
            git remote -v
            ```
            - This should print to the terminal the following
            ```sh
            origin  https://github.com/{YOUR USERNAME}/trackforce.git (fetch)
            origin  https://github.com/{YOUR USERNAME}/trackforce.git (push)
            ```

4. Get a reference to the main repository
    1. Navigate to the main [Trackforce repository](https://github.com/revaturelabs/trackforce)
    2.  On the right side of the file window there is a green button that says clone or download
    3. Copy this path and do the following
        1. In a terminal navigate to the trackforce folder that you just cloned
        2. Run the following command to add a reference to the main repository
            - The path used below is the correct path you may copy this command as is if you don't want to go to Github to copy it
            ```sh
            git remote add upstream https://github.com/revaturelabs/trackforce.git
            ```
        3. Verify everything is set up
            1. Run the command below 
            ```sh
            git remote -v
            ```
            - This should print to the terminal the following
            ```sh
            origin  https://github.com/{YOUR USERNAME}/trackforce.git (fetch)
            origin  https://github.com/{YOUR USERNAME}/trackforce.git (push)
            upstream        https://github.com/revaturelabs/trackforce.git (fetch)
            upstream        https://github.com/revaturelabs/trackforce.git (push)
            ```
5. Update your local copy to have all information for both remotes
    ```sh
    git fetch upstream
    ```
    

# Usage

Below will be a description of commonly performed tasks and how to do them


## I AM WORKING ON A FEATURE / FIX

This means that you are going to write code to complete some task for the project

### Steps to Begin
1. Create a branch off of the dev branch for our sprint
2. Ensure your local copy is up-to-date
    - See [Update Project](#update-project)


## UPDATE PROJECT
1. Ensure that you are on the dev branch for our sprint
   ```sh
   git checkout dev1807
   ```
2. Update dev branch with upstream
   ```sh
   git pull upstream dev1807
   ```
3. Update your repositories copy of dev
   ```sh
   git push origin dev1807
   ```
4. Update your feature branch
   - This is this only time that a merge confilict can occur
   ```sh
    git rebase origin/dev1807
   ```
