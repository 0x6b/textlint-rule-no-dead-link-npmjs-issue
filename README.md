Repository for enhancement request for [textlint-rule-no-dead-link](https://github.com/textlint-rule/textlint-rule-no-dead-link).

[npmjs.com](https://www.npmjs.com) seems to return 503 for HEAD request. Run test by `yarn install && yarn test` will produce:

```sh
yarn run v1.3.2
$ textlint --debug -c textlintrc.json test.md
  textlint:cli Running on files, stdin-filename: undefined +0ms
  textlint:module-loader config Config {
  textlint:module-loader   configFile: '/Users/.../textlint-rule-no-dead-link-npmjs-issue/textlintrc.json',
  textlint:module-loader   rulesBaseDirectory: undefined,
  textlint:module-loader   rules: [ 'no-dead-link' ],
  textlint:module-loader   disabledRules: [],
  textlint:module-loader   filterRules: [],
  textlint:module-loader   disabledFilterRules: [],
  textlint:module-loader   presets: [],
  textlint:module-loader   plugins: [],
  textlint:module-loader   pluginsConfig: {},
  textlint:module-loader   rulesConfig: { 'no-dead-link': {} },
  textlint:module-loader   filterRulesConfig: {},
  textlint:module-loader   extensions: [],
  textlint:module-loader   rulePaths: [],
  textlint:module-loader   formatterName: undefined,
  textlint:module-loader   quiet: false,
  textlint:module-loader   color: true,
  textlint:module-loader   cache: false,
  textlint:module-loader   cacheLocation: '/Users/.../textlint-rule-no-dead-link-npmjs-issue/.textlintcache' } +62ms
  textlint:module-loader Loading rules from /Users/.../textlint-rule-no-dead-link-npmjs-issue/node_modules/textlint-rule-no-dead-link/lib/no-dead-link.js +7ms
  textlint:engine-core Process files [ '/Users/.../textlint-rule-no-dead-link-npmjs-issue/test.md' ] +109ms
  textlint:engine-core Not Process files [] +0ms
  textlint:TextLintCoreTask rules [ { ruleId: 'no-dead-link',
    rule: { linter: [Function: reporter], fixer: [Function: reporter] },
    options: {} } ] +51ms
  textlint:TextLintCoreTask filterRules [] +2ms
  textlint:core-task no-dead-link pushReport {"index":23} +16s
  textlint:textfix-formatter try formatterName: stylish +2ms

/Users/.../textlint-rule-no-dead-link-npmjs-issue/test.md
  1:24  error  https://www.npmjs.com/search?q=textlint is dead. (503 first byte timeout)  no-dead-link

✖ 1 problem (1 error, 0 warnings)
```
