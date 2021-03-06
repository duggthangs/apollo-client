# CHANGELOG

### 1.0.16

- Removed unnecessary whitespace from error message
  [Issue #3398](https://github.com/apollographql/apollo-client/issues/3398)
  [PR #3593](https://github.com/apollographql/apollo-client/pull/3593)

### 1.0.15

- No changes

### 1.0.14

- Store key names generated by `getStoreKeyName` now leverage a more
  deterministic approach to handling JSON based strings. This prevents store
  key names from differing when using `args` like
  `{ prop1: 'value1', prop2: 'value2' }` and
  `{ prop2: 'value2', prop1: 'value1' }`.
  [PR #2869](https://github.com/apollographql/apollo-client/pull/2869)
- Avoid needless `hasOwnProperty` check in `deepFreeze`.
  [PR #3545](https://github.com/apollographql/apollo-client/pull/3545)

### 1.0.13

- Make `maybeDeepFreeze` a little more defensive, by always using
  `Object.prototype.hasOwnProperty` (to avoid cases where the object being
  frozen doesn't have its own `hasOwnProperty`).
  [Issue #3426](https://github.com/apollographql/apollo-client/issues/3426)
  [PR #3418](https://github.com/apollographql/apollo-client/pull/3418)
- Remove certain small internal caches to prevent memory leaks when using SSR.
  [PR #3444](https://github.com/apollographql/apollo-client/pull/3444)

### 1.0.12

- Not documented

### 1.0.11

- `toIdValue` helper now takes an object with `id` and `typename` properties
  as the preferred interface
  [PR #3159](https://github.com/apollographql/apollo-client/pull/3159)
- Map coverage to original source
- Don't `deepFreeze` in development/test environments if ES6 symbols are
  polyfilled
  [PR #3082](https://github.com/apollographql/apollo-client/pull/3082)
- Added ability to include or ignore fragments in `getDirectivesFromDocument`
  [PR #3010](https://github.com/apollographql/apollo-client/pull/3010)

### 1.0.9

- Dependency updates
- Added getDirectivesFromDocument utility function
  [PR #2974](https://github.com/apollographql/apollo-client/pull/2974)

### 1.0.8

- Add client, rest, and export directives to list of known directives
  [PR #2949](https://github.com/apollographql/apollo-client/pull/2949)

### 1.0.7

- Fix typo in error message for invalid argument being passed to @skip or
  @include directives
  [PR #2867](https://github.com/apollographql/apollo-client/pull/2867)

### 1.0.6

- Update `getStoreKeyName` to support custom directives

### 1.0.5

- Package dependency updates

### 1.0.4

- Package dependency updates

### 1.0.3

- Package dependency updates

### 1.0.2

- Improved rollup builds

### 1.0.1

- Added config to remove selection set of directive matches test

### 1.0.0

- Added utilities from hermes cache
- Added removeDirectivesFromDocument to allow cleaning of client only
  directives
- Added hasDirectives to recurse the AST and return a boolean for an array of
  directive names
- Improved performance of common store actions by memoizing addTypename and
  removeConnectionDirective
