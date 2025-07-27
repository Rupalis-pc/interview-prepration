# GitHub Interview Preparation

This file contains important interview questions related to GitHub, version control, and workflows.

## Core Concepts

1. What is Git and how is it different from GitHub?
   - Git is a distributed version control system for tracking changes in source code. GitHub is a web-based platform that hosts Git repositories and provides collaboration features like pull requests and issues.
2. Explain the difference between a fork and a clone.
   - Fork creates a copy of a repository under your GitHub account for independent changes. Clone copies a repository to your local machine.
3. What is a pull request and how does it work?
   - A pull request is a request to merge your changes from one branch or fork into another branch or repository. It allows code review and discussion before merging.
4. How do you resolve merge conflicts in Git?
   - By manually editing the conflicted files to choose or combine changes, then marking them as resolved with `git add` and completing the merge.
5. What is the difference between `git fetch` and `git pull`?
   - `git fetch` downloads changes from the remote but does not merge them. `git pull` fetches and then merges the changes into your current branch.
6. How do you revert a commit that has already been pushed?
   - Use `git revert <commit>` to create a new commit that undoes the changes. For multiple commits, use `git revert <oldest>^..<newest>`.
7. What is a branch and why are branches useful?
   - A branch is an independent line of development. Branches allow you to work on features or fixes without affecting the main codebase.
8. How do you squash commits before merging a pull request?
   - Use `git rebase -i` to interactively squash commits locally, then force-push. On GitHub, you can also select "Squash and merge" when merging a pull request.
9. What is the purpose of `.gitignore`?
   - `.gitignore` specifies files and directories that should not be tracked by Git, such as build artifacts or sensitive files.
10. How do you undo the last commit but keep the changes locally?
   - Use `git reset --soft HEAD~1` to undo the last commit and keep the changes staged, or `git reset --mixed HEAD~1` to keep them unstaged.

## Collaboration & Workflow

1. Describe the typical workflow for contributing to an open-source project on GitHub.
   - Fork the repository, clone it locally, create a new branch, make changes, push to your fork, and open a pull request.
2. What are GitHub Actions and how can they be used?
   - GitHub Actions is a CI/CD tool for automating workflows like testing, building, and deploying code directly from your repository.
3. How do you protect the main branch in a repository?
   - Enable branch protection rules in repository settings to require pull requests, reviews, and passing checks before merging.
4. What is a release in GitHub and how do you create one?
   - A release is a snapshot of your code at a point in time, often tied to a tag. Create one from the Releases tab or with `git tag` and push the tag.
5. How do you review and approve pull requests?
   - Review code changes, leave comments, request changes or approve, and merge if everything is satisfactory.
6. What are issues and how are they used in project management?
   - Issues are used to track bugs, enhancements, tasks, and questions. They help organize and prioritize work.
7. How do you use labels and milestones in GitHub?
   - Labels categorize issues and pull requests. Milestones group issues and PRs by project phase or release.
8. What is a GitHub gist?
   - A gist is a simple way to share code snippets, notes, or single files with others via GitHub.
9. How do you set up a repository for continuous integration?
   - Add a workflow file (e.g., `.github/workflows/ci.yml`) to define CI steps, such as running tests on push or pull requests.
10. How do you handle sensitive information in a public repository?
   - Use environment variables, secrets, and `.gitignore` to avoid committing sensitive data. Remove secrets from history if accidentally committed.

## Advanced Topics

1. What is Git rebase and when should you use it?
   - `git rebase` moves or combines commits from one branch onto another. Use it to maintain a linear history or update a feature branch with the latest main branch changes.
2. How do you cherry-pick a commit from one branch to another?
   - Use `git cherry-pick <commit-hash>` to apply a specific commit from one branch onto your current branch.
3. Explain the difference between `git merge` and `git rebase`.
   - `git merge` combines histories and creates a merge commit. `git rebase` moves your branch commits on top of another branch, creating a linear history.
4. How do you revert a merge commit?
   - Use `git revert -m 1 <merge-commit-hash>` to revert a merge commit, specifying the parent branch to keep.
5. What are submodules in Git?
   - Submodules allow you to include and manage external repositories within a parent repository.
6. How do you sign commits and why is it important?
   - Sign commits with GPG or SSH to verify authorship and integrity. It helps ensure code authenticity.
7. What is the difference between annotated and lightweight tags?
   - Annotated tags store extra metadata (author, date, message) and are recommended for releases. Lightweight tags are simple pointers to a commit.
8. How do you use GitHub CLI?
   - Install GitHub CLI (`gh`), then use commands like `gh repo clone`, `gh pr create`, and `gh issue list` to interact with GitHub from the terminal.
9. How do you automate releases with GitHub Actions?
   - Set up a workflow that triggers on tag creation or release events to build and publish releases automatically.
10. How do you manage large files in GitHub repositories?
   - Use Git Large File Storage (LFS) to track and store large files outside the main repository history.
