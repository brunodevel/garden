# Contributing Guidelines

## Summary

- [Message Format](#message-format)
- [Message Types](#message-types)
- [Message Scope](#message-scope)
- [Message Subject](#message-subject)
- [Message Body](#message-body)
- [Branches](#branches)
- [Fetching](#fetching)
- [Pull Request](#pull-request)
- [Merging](#mergin)

This is our commits messages standard. We use these standard to easily identify and differentiate which type of commit is. This pattern is to have a better and understandable messages.

## Message Format

Each commit message consists of a header, a body and a footer. The header has a special format that includes a type, a scope and a subject:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

> Obs: prefer to use git commit to make bigger commit message.

## Message Types

These are the types of commits we can use.

- `feat` New features
- `fix` Bug fixes
- `docs` Documentation Changes
- `lint` Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- `refactor` A code change that neither fixes a bug nor adds a feature
- `test` Adding missing tests
- `chore` Changes to the build process or auxiliary tools and libraries such as documentation generation
- `revert` revert previous commit (hope not use this)

> we also provide `wip` type, but commits with `wip` type, should be rewrited using rebase when open a pull request

## Message Scope

Scope is what you're pretending to change, ex:

```
git commit -m 'feat(form): add new radio button component
```

## Message Subject
The subject contains succinct description of the change:

- use the imperative, present tense: "change" not "changed" nor "changes"
- no dot (.) at the end

## Message Body

Just as in the subject, use the imperative, present tense: "change" not "changed" nor "changes". The body should include the motivation for the change and contrast this with previous behavior.

## Branches

Always work inside a feature branch. Branch name should be based on our types, ex:

```
git checkout -b feat/new-radio-component

git checkout -b fix/radio-component

git checkout -b test/radio-component

git checkout -b refactor/radio-component

```

## Fetching

Prefer to use `git pull --rebase` to update you local branch

## Pull Request

When submit a pull request, doesn't matter if it's a fix/feature/refactor. We usually add `lint`, `jshint`, `jslint`, `coverage`, `layout` (for visual things), `tests log` prints-screen to show that's everthing ok before add tag `should-review`.

## Merging

Using this approach to merge branch when pull request is approved.

```
git fetch origin

# from feature branch
# use -i (interactively) to review your commits, rewrite, edit then
git rebase -i origin/develop

# We need to use -f because we did a rebase
git push origin feat/new-radio-component -f

# move to develop
git checkout develop

# use --ff-only to remove automatic merge message
git merge --ff-only feat/new-radio-component

```
--

Commit Guidelines is based in:

> - [Angular commit pattern](https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#commit).
> - [Thoughtbot Git Guide](https://github.com/thoughtbot/guides/tree/master/protocol/git)
> - [5 Useful tips for a better commit message](https://robots.thoughtbot.com/5-useful-tips-for-a-better-commit-message)