We're really glad you're reading this, because we need volunteer developers to help this project come to fruition. 👏

## Instructions

These steps will guide you through contributing to this project:

- Fork the repo
- Clone it and install dependencies

		git clone https://github.com/eastbanctech/ts-optional
		npm install


Make and commit your changes. Make sure the command `npm ci && npm run test:prod && npm run build` is working.

Finally, send a [GitHub Pull Request](https://github.com/eastbanctech/ts-optional/compare?expand=1) 
with a clear list of what you've done (read more [about pull requests](https://help.github.com/articles/about-pull-requests/)). 
Make sure all of your commits are atomic (one feature per commit).

### Pull requests name format

A pull request name should look like '_[#issue_number] What was done_'

### Commit message format

Similar to PR names: '_[#issue_number] What was done_'

### Travis CI
Build descriptor for the project is '.travis.yml' file.
 
To integrate with the CI: 
- github [personal access tokens](https://github.com/settings/tokens) should be generated. 
    - Generated value should be defined in Travis as _GH_TOKEN_ 
[environment variable](https://docs.travis-ci.com/user/environment-variables/#defining-variables-in-repository-settings) for _master_ branch.
- npm account email should be defined as _NPM_EMAIL_ environment variable for all branches.
- npm [access tokens](https://docs.npmjs.com/creating-and-viewing-authentication-tokens) should be defined as _NPM_TOKEN_ environment variable for all branches.

### How to release (deploy npm package)
Travis will deploy all tags: 'Tagged commit' == 'new release'.

Generally [npm version](https://docs.npmjs.com/cli/version) command should be applied.

To make a release:
1. Checkout _master_ branch.
2. Run command `npm version patch`
3. Push changes: ` git push origin HEAD:master --tags`

Will be created a commit with new version number as a message. For example: _'v0.1.0'_.
Travis will deploy the new version.
