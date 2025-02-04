# Contributing to the Chainlink Documentation

PRs are welcome! We try to keep a clean commit history, so we'll follow a standard process:

- Create a PR
  - If your PR contains multiple commits, we'll ask you to squash them
  - If your PR has conflicts with `main`, we'll ask you to rebase it
- Someone will review your PR
- Your PR will be merged, amended, closed, or you'll be asked for changes

## Standards

- Commit messages
  - Start with a present tense verb
  - Keep your commit headline short but sufficient to understand the scope and focus of the change.
  - Changes are often formatted like `add doc X`, `fix page Y`, `improve docs for Z`.
  - Example: "`update contract addresses for BNB Chain`".
- If you touch any infrastructure, make sure it builds with `yarn build`
  - If you haven't already, `npm -g install astro`
- Trust the autoformatter (prettier)
- Make sure images are optimized and compressed
- Keep images < 20kb whenever possible to keep the site fast and the repo small (try [trimage](https://trimage.org/))

## How to rebase a PR

```shell
git fetch
git rebase origin/main
# resolve conflicts
git push -f
```

It's okay to force push over your own PR branch. In fact, that's what we want so that the commits are clean.

## How to squash a PR

To squash multiple commits, use the following steps:

### 1. Rebase multiple commits into one

When squashing commits, you should always rebase from the main branch of the repo: `git rebase -i origin/main`.

After rebasing, you can squash the commits by changing `pick` into `squash` for all of your commits except the recent one:

```shell
pick 686e386 add doc structure
squash ee2eed7 add main content
squash 3eccd39 fix typos

# Rebase 287bc79..3eccd39 onto 287bc79 (3 commands)
# …
```

### 2. Fix your commit message

Next, comment or remove all of your commit messages and leave the one that describes your PR.

### 3. Force push to your branch

Lastly, force push the changes to your branch to have a clean history:

```shell
git push -f
```

It's easier to use `git --amend` while working on your PR first. Avoiding multiple commits is much cleaner and easier than fixing them.

## Adding a new chain feed

Data Feeds information comes from a private GitHub repository that processed and updated automatically.

## Checking Links

To check the site for broken links, run `npm run linkcheck`.

## Adding or updating code samples

The main code samples are stored in the `/public/samples/` directory.

## Style Guide

- **Bold** key terms or any terms the user must absolutely know when reading a doc.
- _Italicize_ terms for emphasis but only when necessary.
- When referring to dropdown menus or a sequence of dropdown events, bold the relevant entities. Example: Go to **Menu Name** > **Option**. Do not use quotes.
- Use markdown over HTML wherever possible.
- When writing an additional note, start it with **Note:**.
- Use a consistent voice. When writing documentation, avoid first person plural "we" and opt for second person singular "you". Avoid passive voice.
