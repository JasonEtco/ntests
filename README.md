# Test Selector

A helper CLI tool to make it easier to run just the tests you want by asking you which tests you want to run.

`test-selector` will look through your `package.json` file's scripts object and pick out the ones following the `test:testName` scheme. It will then ask you which one of those tests you want to run! Or, if you already know, you can include the test name in the command.

## Requirements

`tst` assumes that your `package.json` file's scripts object is formatted like this:

```json
{
  "scripts": {
    "test": "test for things",
    "test:api": "test just the api",
    "test:compiler": "test just the compiler"
  }
}
```

### Basic usage

```bash
$ tst
```

![image](https://user-images.githubusercontent.com/10660468/30147090-4e238982-936a-11e7-8042-d96d5abbe6a5.png)

### Run a specific test

Already know which test you want to run? Cool! The following command is the same as `npm run test:api`.

```bash
$ tst api
```
Output:
```
[tst] Running the test suite: api
```

### Available options

| Option | Default | Description |
| ------ | ------- | ----------- |
| `-p`, `--prefix` | `'test'` | Separator character |
| `-s`, `--separator` | `':'` | String that all tests are prefixed with |
