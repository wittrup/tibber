# Tibber repository

![GitHub language count](https://img.shields.io/github/languages/count/wittrup/tibber)&nbsp;
![GitHub top language](https://img.shields.io/github/languages/top/wittrup/tibber)&nbsp;
![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/wittrup/tibber)&nbsp;
![GitHub repo size](https://img.shields.io/github/repo-size/wittrup/tibber)&nbsp;
![GitHub](https://img.shields.io/github/license/wittrup/tibber)&nbsp;
![GitHub forks](https://img.shields.io/github/forks/wittrup/tibber?style=social)&nbsp;
![GitHub watchers](https://img.shields.io/github/watchers/wittrup/tibber?style=social)&nbsp;
![GitHub last commit](https://img.shields.io/github/last-commit/wittrup/tibber)&nbsp;

` `

Scripts and example files for [Tibber](https://tibber.com/)

Find your API token at [Tibber Developer](https://developer.tibber.com/)

Place it in a file, as shown here: [demo-token-header](https://github.com/wittrup/tibber/blob/main/demo-token-header)

## Shell usage:
```console
$ ./curlfile -h demo-token-header example-queries/01-logged-in-user.gql | jq
{
  "data": {
    "viewer": {
      "name": "Arya Stark"
    }
  }
}

$ ./curlfile -h demo-token-header example-queries/02-homes.gql
{"data":{"viewer":{"homes":[{"address":{"address1":"Winterfell Castle 1",
"address2":null,"address3":null,"postalCode":null,"city":null,
"country":null,"latitude":null,"longitude":null}}]}}}

$ ./curlfile -h demo-token-header example-queries/03-current-energy-price.gql | head -c79
{"data":{"viewer":{"homes":[{"currentSubscription":{"priceInfo":{"current":{"to
```

` `

[graphqurl](https://github.com/hasura/graphqurl) not supported at the moment:
```console
$ gq https://api.tibber.com/v1-beta/gql -q '{ viewer { name } }' -H 'Authorization: Bearer 476c477d8a039529478ebd690d35ddd80e3308ffc49b59c65b142321aee963a4'
Executing query... error
Error:  { errors: [ { message: 'failed to fetch' } ] }

$ gq https://api.tibber.com/v1-beta/gql --queryFile example-queries/01-logged-in-user.gql -H demo-token-header
 ›   Error: cannot parse header 'demo-token-header' (multiple ':')
```
