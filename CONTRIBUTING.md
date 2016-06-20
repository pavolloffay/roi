# Contributing to roi

## Issue contributions

### Did you find a bug ?

Open a [new issue](https://github.com/bucharest-gold/roi/issues/new)
and be sure to include a title and clear description, as much relevant information
as possible, and a code sample or a test case demonstrating the expected behavior
that is not occurring.

Discussions can be done via github issues or IRC channel #brass-monkey.

## Code contributions

### Fork

Fork the project [on GitHub](https://github.com/bucharest-gold/roi)
and check out your copy locally.

```shell
$ git clone git@github.com:username/roi.git
$ cd roi
$ git remote add upstream https://github.com/bucharest-gold/roi.git
```

### Branch

Create a feature branch and start hacking:

```shell
$ git checkout -b my-contrib-branch
```

### Commit messages

Writing good commit logs is important. A commit log should describe what
changed and why. Follow these guidelines when writing one:

1. The first line should be 50 characters or less and contain a short
   description of the change.
2. Keep the second line blank.
3. Wrap all other lines at 72 columns.

Example of commit message:

```
fix a bug with download url.

The download url was not using https.
Body of commit message is a few lines of text, explaining things
in more detail, possibly giving some background about the issue
being fixed, etc. etc.

The body of the commit message can be several paragraphs, and
please do proper word-wrap and keep columns shorter than about
72 characters or so. That way `git log` will show things
nicely even when it is indented.
```

### Rebase to keep updated.

Use `git rebase` to sync your work from time to time.

```shell
$ git fetch upstream
$ git rebase upstream/master
```

### Start server | Code - Test - Code - Test... | Stop server

Bug fixes and features should come with tests. Add your tests in the
`test/roi-test.js` file.

To write the tests you will need to install json-server and start in one terminal:

```shell
$ npm install -g json-server
```

Then

```shell
$ json-server --watch test/fixtures/db.json
```

This will use json file as 'endpoints' like a fake-server.

Then you can start coding and watching the results of the tests with this command:

```shell
$ make test
```

Make sure the jshint and semistandard are happy and that all tests pass. Please, do not submit
patches that fail either check.

### Step 6: Push

```shell
$ git push origin my-contrib-branch
```

Go to https://github.com/yourusername/roi and select your feature branch.
Click the 'Pull Request' button and fill out the form.