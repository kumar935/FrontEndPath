## Snapshot Testing with Jest, Configuring and running it | Lec 32,33

> for mocha testing watch v1 of the course only the mocha testing part

- create `__tests__` folder in js folder.
- then inside, create `Search.spec.jsx`
- to tell the eslint, add `jest: true` in `env` in `.eslintrc.json`.

> Jest under the hood is Jasmin

__Running Jest and snapshot testing__

- Run Jest using `NODE_ENV=test ./node_modules/.bin/jest`
- It will create a directory `__snapshots__` inside the tests folder and test the output against it.
- To update the snapshot just add run `NODE_ENV=test ./node_modules/.bin/jest -u`



## Shallow Testing with Enzyme | Lec 34 - 37

- changed Showcard.jsx, but test error thrown for Search.jsx
- we want test for showcard.jsx to fail; enter enzyme
- Showcard was Search's child component in a way that's why it was failing, so enzyme would be limiting to the component itself and stub out the child stuff.

- put x in front of test name to have it skipped.
- fail a test to verify it works

## Test coverage with Istanbul | Lec 38

jest --coverage will create a coverage directory which will give a gui showing test coverage





