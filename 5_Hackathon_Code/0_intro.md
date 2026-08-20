# Contributing Code During the Ocean Hackathon

Please add your hackathon work under `5_Hackathon_Code/`.

## Open the Repository

The EDC workspace git-puller link is:

**TBD**

This link will clone the repository if it is not already available in your workspace and open the introductory notebook.

The main Ocean Hackathon repository is:

https://github.com/ESA-EarthCODE/ocean_site

## Fork the Repository

After the repository is open in your workspace, create your own fork of the main repository on GitHub. Your fork will look like:

```text
https://github.com/<your-github-username>/ocean_site
```

[GitHub Docs: Fork a repository](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo)

Then change the local workspace repository so `origin` points to your fork:

```bash
git remote -v
git remote set-url origin https://github.com/<your-github-username>/ocean_site.git
git remote -v
```

Keep the main hackathon repository as `upstream` so you can pull updates:

```bash
git remote add upstream https://github.com/ESA-EarthCODE/ocean_site.git
```

If `upstream` already exists, skip that line.

[GitHub Docs: Managing remote repositories](https://docs.github.com/en/get-started/git-basics/managing-remote-repositories)

## Commit Your Work

Run these commands in a terminal, not inside a notebook:

```bash
git switch -c <branch-name>
git status
git add 5_Hackathon_Code/
git commit -m "Add hackathon contribution"
git push origin <branch-name>
```

Choose a short branch name that describes your work, for example `add-ocean-analysis-notebook`. Your changes are pushed to your fork, not to the main hackathon repository.

[GitHub Docs: Set up Git](https://docs.github.com/en/get-started/git-basics/set-up-git)

[GitHub Docs: Pushing commits to a remote repository](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository)

## Open a Pull Request

Open a pull request from your fork's branch into the main Ocean Hackathon repository:

https://github.com/ESA-EarthCODE/ocean_site/pulls

[GitHub Docs: Creating a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

After creating the pull request, check that it appears in the pull request list and follow up on any review comments.
