# Contributing to Arcana

We welcome additions and extensions to Arcana that help progress our goal of supporting student learning through frequent formative feedback and delayed summative assessment.

This guide provides high-level details on how to contribute to the Programming-Arcana repository.

# Table of contents
- [Contributing to Arcana](#contributing-to-arcana)
- [Table of contents](#table-of-contents)
- [How to run it.](#how-to-run-it)
  - [Preparation](#preparation)
  - [Running in your local environment](#running-in-your-local-environment)
  - [Running with docker compose](#running-with-docker-compose)
- [Branch Prefixes](#branch-prefixes)
- [Commit Message Format](#commit-message-format)
    - [Use the imperative mood in your commit subject line](#use-the-imperative-mood-in-your-commit-subject-line)
    - [But how can I write new lines if I'm using `git commit -m "Message"`?](#but-how-can-i-write-new-lines-if-im-using-git-commit--m-message)

# How to run it.

## Preparation

1. Fork this repository.
2. Clone your Programming-Arcana
    
    ```bash 
    git clone https://github.com/<Your user name>/programming-arcana
    ```
3. Add the remote url so you can pull update from. (For more information about forking workflow check [Here](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow))
    ```bash
     git remote add upstream https://github.com/splashkit/programming-arcana
     ```
4. Nodejs Version **14** installed.
5. Docker installed. [optional]

\* The other version of nodejs may not working for this project, especially version 17.x.x. Please make sure you nodeJs version is **14**. I recommend to use [n](https://github.com/tj/n) for manage your nodeJs version.

## Running in your local environment 
1. Install the dependencies
    ```bash
    npm install
    ```
2. Running the application
    ```bash
    npm run develop
    ```
3. The application will be running at ` http://localhost:8000 `

## Running with [docker compose](https://docs.docker.com/compose/)
1. Build and running the image.
    ```bash
    docker-compose -f "docker-compose.yml" up -d --build
    ```
2. The application will be running at ` http://localhost:8080 ` 

\* Please notice the docker compose has mount the container volume with your local files, so you can develop normally with docker container running.

# Branch Prefixes

When branching, try to prefix your branch with one of the following:

Prefix     | Description                                                               | Example
-----------|---------------------------------------------------------------------------|--------------------------------------------------------------------
`feature/` | New feature was added                                                     | `feature/add-learning-outcome-alignment`
`fix/`     | A bug was fixed                                                           | `fix/crash-when-code-submission-finished`
`enhance/` | Improvement to existing feature, but not visual enhancement (See `LOOKS`) | `enhance/allow-code-files-to-be-submitted`
`looks/`   | UI Refinement, but not functional change (See `ENHANCE`)                  | `looks/rebrand-ui-for-version-2-marketing`
`quality/` | Refactoring of existing code                                              | `quality/make-code-convention-consistent`
`doc/`     | Documentation-related changes                                             | `doc/add-new-api-documentation`
`config/`  | Project configuration changes                                             | `config/add-framework-x-to-project`
`speed/`   | Performance-related improvements                                          | `speed/new-algorithm-to-process-foo`
`test/`    | Test addition or enhancement                                              | `test/unit-tests-for-new-feature-x`

# Commit Message Format

We have precise rules over how our Git commit messages must be formatted. This format makes it easier to read the commit history.

Each commit message consists of a header, a body, and a footer.

```text
<header>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The `header` is mandatory and must conform to the Commit Message Header format.

The `body` is recommended for all commits. When the body is present, it must be at least 20 characters long and conform to the Commit Message Body format.

The `footer` is optional. The Commit Message Footer format describes the purpose and structure of the footer.

Any line of the commit message should be 100 characters or fewer.

```text
Commit Message Header
<type>(<scope>): <short summary>
  │       │             │
  │       │             └─⫸ Summary in present tense. Not capitalized. No period at the end.
  │       │
  │       └─⫸ Commit Scope (optional): animations|common|style|forms|http|router|service-worker|
  │                                     upgrade|changelog|dev-infra|docs-infra|migrations|
  │
  └─⫸ Commit Type: build|ci|docs|feat|fix|perf|refactor|test
```

The `<type>` and `<summary>` fields are mandatory, the `(<scope>)` field is optional.

The `<type>` must be one of the following:

- **build**: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
- **ci**: Changes to our CI configuration files and scripts (example scopes: Circle, BrowserStack, SauceLabs)
- **docs**: Documentation only changes
- **feat**: A new feature
- **fix**: A bug fix
- **perf**: A code change that improves performance
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **test**: Adding missing tests or correcting existing tests

We recommend reading Chris Beam's post on [How to Write Good Commit Messages](http://chris.beams.io/posts/git-commit/).

### Use the imperative mood in your commit subject line

Write your commits in the imperative mood and not the indicative mood

- "Fix a bug" and **not** "Fix*ed* a bug"
- "Change the behaviour of Y" and **not** "*Changed* the behaviour of Y"
- "Add new API methods" and **not** "Sweet new API methods"

Keep the subject line (top line) concise; keep it **within 50 characters**.

Use the body (lines after the top line) to explain why and what and *not* how; keep it **within 72 characters**.

### But how can I write new lines if I'm using `git commit -m "Message"`?

Don't use the `-m` switch. Use a text editor to write your commit message instead.

If you are using the command line to write your commits, it is useful to set your git editor to make writing a commit body easier. You can use the following command to set your editor to Visual Studio Code, `nano`, `emacs`, `vim`, `atom`.

```bash
git config --global core.editor "code --wait"
git config --global core.editor nano
git config --global core.editor emacs
git config --global core.editor vim
git config --global core.editor "atom --wait"
```