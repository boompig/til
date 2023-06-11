# Jest

Jest is (currently) the most popular javascript unit-testing framework.

- `-t` allows you to select which test suites will run by name
- `--bail` allows you to bail after one failed test

## resolving weird problems

For example I had a version of [this issue](https://stackoverflow.com/questions/71223711/jest-cannot-find-module-node-modules-babel-preset-react-app-node-modules).
The posted solution worked for me, namely clearing the jest cache:

```
npx jest --clearCache
```

