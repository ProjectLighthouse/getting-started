# Contributors Guide

Thank you for being a part of Project Lighthouse! :heart:

We’ve already attracted a small team of dedicated contributors, but the need is great and we would love for you to join us as we make the vision become a reality. Join us as we change the world together, here’s how to get started!

1. Visit project-lighthouse.org/developers and fill out the form.
1. We'll reach out, then following a quick intro we will send the Contributors Agreement.
1. Sign the Contributor Agreement and we'll invite you to Github.
1. Find an issue or a story to work on and let us know in the comments.
1. Pull down the code and take a look around.
1. Work your magic and submit a pull request.
1. Congratulations 🎉, together we can serve our communities better!

Feel free to reach out on Slack to ask for help or clarification.

[Join us on Slack](http://bit.ly/2vfoURo)

## Table of Contents
* Sign the Contributor Agreement
* Find a Story or Issue that Needs Help
* Make a Pull Request

## 1. Sign the Contributor Agreement
We know, you love reviewing and signing legal documents in your spare time, but, our lawyers made us promise we’d collect a signed contributor agreement before accepting Pull Requests. The process is quick and simple, we promise!

* For individuals, we have a docusign document ready to send you.
* For corporations, use this docusign document to get started.

## 2. Find a Story or Issue that Needs Help
To-Do.

## 3. Make a Pull Request

Good pull requests - patches, improvements, new features - are a fantastic
help. They should remain focused in scope and avoid containing unrelated
commits.

**Please ask first** before embarking on any significant pull request (e.g.
implementing features, refactoring code), otherwise you risk spending a lot of
time working on something that the project's developers might not want to merge
into the project.

#### For new Contributors

If you never created a pull request before, welcome [Here is a great tutorial](https://egghead.io/series/how-to-contribute-to-an-open-source-project-on-github)
on how to send one :)

1. [Fork](http://help.github.com/fork-a-repo/) the project, clone your fork,
   and configure the remotes:

   ```bash
   # Clone your fork of the repo into the current directory
   git clone https://github.com/<your-username>/<repo-name>
   # Navigate to the newly cloned directory
   cd <repo-name>
   # Assign the original repo to a remote called "upstream"
   git remote add upstream https://github.com/ProjectLighthouse/<repo-name>
   ```

2. If you cloned a while ago, get the latest changes from upstream:

   ```bash
   git checkout master
   git pull upstream master
   ```

3. Create a new topic branch (off the main project development branch) to
   contain your feature, change, or fix:

   ```bash
   git checkout -b <topic-branch-name>
   ```

4. Make sure to update, or add to the tests when appropriate. Patches and
   features will not be accepted without tests. Run `npm test` to check that
   all tests pass after you've made changes. Look for a `Testing` section in
   the project’s README for more information.

5. If you added or changed a feature, make sure to document it accordingly in
   the `README.md` file.

6. Push your topic branch up to your fork:

   ```bash
   git push origin <topic-branch-name>
   ```

8. [Open a Pull Request](https://help.github.com/articles/using-pull-requests/)
    with a clear title and description.

#### For Members of the Lighthouse Contributors Team

1. Clone the repo and create a branch

   ```bash
   git clone https://github.com/ProjectLighthouse/<repo-name>
   cd <repo-name>
   git checkout -b <topic-branch-name>
   ```

2. Make sure to update, or add to the tests when appropriate. Patches and
   features will not be accepted without tests. Run `npm test` to check that
   all tests pass after you've made changes. Look for a `Testing` section in
   the project’s README for more information.

3. If you added or changed a feature, make sure to document it accordingly in
   the `README.md` file.

4. Push your topic branch up to our repo

   ```bash
   git push origin <topic-branch-name>
   ```

5. Open a Pull Request using your branch with a clear title and description.

Optionally, you can help us with these things. But don’t worry if they are too
complicated, we can help you out and teach you as we go :)

1. Update your branch to the latest changes in the upstream master branch. You
   can do that locally with

   ```bash
   git pull --rebase upstream master
   ```

   Afterwards force push your changes to your remote feature branch.

2. Once a pull request is good to go, you can tidy up your commit messages using
   Git's [interactive rebase](https://help.github.com/articles/interactive-rebase).
   Please follow our commit message conventions shown below, as they are used by
   [semantic-release](https://github.com/semantic-release/semantic-release) to
   automatically determine the new version and release to npm. In a nutshell:

   ##### Commit Message Conventions

   - Commit test files with `test: ...` or `test(scope): ...` prefix
   - Commit bug fixes with `fix: ...` or `fix(scope): ...` prefix
   - Commit new features with `feat: ...` or `feat(scope): ...` prefix
   - Commit breaking changes by adding `BREAKING CHANGE: ` in the commit body
     (not the subject line)
   - Commit changes to `package.json`, `.gitignore` and other meta files with
     `chore(filenamewithoutext): ...`
   - Commit changes to README files or comments with `docs: ...`
   - Cody style changes with `style: standard`

**IMPORTANT**: Before submitting a patch, improvement, or feature, you must first agree to and sign the Contributor Agreement.
