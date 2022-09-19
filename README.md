[![npm version](https://img.shields.io/npm/v/checksslcertificate.svg?style=flat)](https://npmjs.org/package/checksslcertificate "View this project on npm")
# checkSslCertificate

A module which allows you to check the certificate of a given hostname is valid.

- Typescript support

This module returns a Promise which will always resolve.

In case of an error the returned object will contain have an error property.

## Installation
To install this package run:
```bash
$ npm install @dmitryusenko/checksslcertificate --save 
# Or
$ yarn add @dmitryusenko/checksslcertificate
```

## Usage
```js
import checkSslCertificate from '@dmitryusenko/checksslcertificate'
// or 
// const checkSslCertificate = require('@dmitryusenko/checksslcertificate').default

checkSslCertificate({hostname: 'github.com'}).then(res => {
   console.log(res)
})
```

## Options
### UrlObject

| Properties | Type   | Required | Default | Example       |
|----------- | ------ | -------- | ------- | ------------- |
| hostname   | string | true     | -       | 'example.com' |
| method     | string | false    | 'HEAD'  | 'GET'         |
| path       | string | false    | -       | '/foo'        |
| port       | number | false    | 443     | 444           |

## Return Value
### SslCheckResponse

| Properties     | Type      | Optional | Example                    |
|--------------- | --------- | -------- | -------------------------- |
| error          | string    | true     |                            |
| originalObject | UrlObject | false    | {hostname: 'example.com'}  |
| valid          | boolean   | false    | true                       |
| validFrom      | string    | true     | 'May  8 00:00:00 2018 GMT' |
| validUntil     | string    | true     | 'Jun  3 12:00:00 2020 GMT' |
