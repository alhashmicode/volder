# volder
[![Codecov Coverage](https://img.shields.io/codecov/c/github/devSupporters/volder/master>.svg?style=flat-square)](https://codecov.io/gh/devSupporters/volder/)
[![CI](https://github.com/devSupporters/volder/actions/workflows/main.yml/badge.svg)](https://github.com/devSupporters/volder/actions/workflows/main.yml)
[![Package Size](https://img.shields.io/bundlephobia/minzip/volder?label=package%20size)](https://www.npmjs.com/package/volder)
[![Downloads](https://img.shields.io/npm/dm/volder)](https://www.npmjs.com/package/volder)
[![Version](https://img.shields.io/npm/v/volder)](https://www.npmjs.com/package/volder)
[![License](https://img.shields.io/npm/l/volder)](https://github.com/devSupporters/volder/blob/main/LICENSE)

volder is a powerful JavaScript schema builder for value parsing and validation. Define a schema and validate values, volder schema are extremely simple to use, it has custom error messages, custom types, nested schemas.

## Contents

- [Installation](#Installation)
- [Usage](#Usage)
- [Custom error messages](#Custom-error-messages)
- [Custom type validator](#Custom-type-validator)
- [Nested schema](#Nested-schema)
- [Option table](#Option-table)

## Installation
`npm install --save volder`

## Usage
You define and create volder schema objects

```js
import Volder from 'volder';

const person = new Volder({
  name: {
    type: String,
    min: 4,
    trim:true,
    required: true
  },
  age: {
    type: Number,
    max: 100
  }
});
const [isValidPerson, errors] = person.validate({name:"lion", age:23})
```
 - return isValidPerson true if an object are valid otherwise false
 - if there are error or something wrong return errors object with his option name otherwise return empty object {} 
 - throw an error if validate function paramatere other than object
