# Husky-Jira Demo

> Configuring githooks using husky and linting git commit message to have jira id reference with commitlint

## Steps

1. Install `npm i --save-dev husky @commitlint/cli commitlint-config-jira commitlint-plugin-jira-rules` 
2. Create a file named `commitlint.config.js`

```js
// commitlint.config.js
module.exports = {
  plugins: ['commitlint-plugin-jira-rules'],
  extends: ['jira'],
}
```

3. Update package.json to configure `husky`

```json
{
"husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }
  }
}
```

4. Now each git commit message should contain a jira id reference else the commit will fail. Pattern to follow for successful git commit is `JIRA-<ID>: <Commit Message description>`
