# ember-awesome-macros
[![npm version](https://badge.fury.io/js/ember-awesome-macros.svg)](https://badge.fury.io/js/ember-awesome-macros)
[![Build Status](https://travis-ci.org/kellyselden/ember-awesome-macros.svg?branch=master)](https://travis-ci.org/kellyselden/ember-awesome-macros)
[![Dependency Status](https://david-dm.org/kellyselden/ember-awesome-macros.svg)](https://david-dm.org/kellyselden/ember-awesome-macros)
[![devDependency Status](https://david-dm.org/kellyselden/ember-awesome-macros/dev-status.svg)](https://david-dm.org/kellyselden/ember-awesome-macros#info=devDependencies)

#### Macro list
* `defaultTrue`
* `getBy`
* `promiseArray`

#### Details

##### `defaultTrue`
sugar for `ifNull('key', true)` from [ember-cpm](https://github.com/cibernox/ember-cpm)

##### `getBy`
get a variable property name from an object

```js
key: 'modelProperty',
model: {
  modelProperty: 'my value'
},
value: getBy('model', 'key')
```

##### `promiseArray`
wraps a promise in the equivalent of `DS.PromiseArray` (`ArrayProxy` and `PromiseProxyMixin`)

```js
products: promiseArray(function() {
  return this.store.findAll('product');
})
```

can also wrap an existing property

```js
productsPromise: computed(function() {
  return this.store.findAll('product');
}),
products: promiseArray('productsPromise')
```
