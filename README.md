# tokenlist

[![Schema](https://github.com/nathanjessen/tokenlist/workflows/Schema/badge.svg)](https://github.com/nathanjessen/tokenlist/actions?query=workflow%3ASchema)

Template for creating a tokenlist with Uniswap token schema validation.

## Contributing

### New Token

- At the bottom of `all.tokenlist.json` increase the "minor" number by 1. Set the "patch" number to 0.
- Add your new token to the end of the "token" array.
- Add the token image to the img folder.

Each entry should follow the format below 

```
{
    "chainId": 1,
    "address": "0x...",
    "symbol": "XYZ",
    "name": "XYZ Token",
    "decimals": 18,
    "logoURI": "https://raw.githubusercontent.com/nathanjessen/tokenlist/master/img/xyz_token_32.png"
}
```

### Updating an existing token

- At the bottom of `all.tokenlist.json` increase the "patch" number by 1.
- Go to your token in the file and update the information

### Removing an existing token

- At the bottom of `all.tokenlist.json` increase the "major" number by 1. Set "minor" to 0. Set "patch" to 0.
- Remove the token from the file
- Remove the token image from the img folder

## Resources

* [Ethereum token lists](https://tokenlists.org/)
* [https://github.com/Uniswap/token-lists](https://github.com/Uniswap/token-lists)
* [What are token lists?](https://github.com/Uniswap/token-lists/blob/master/README.md#what-are-token-lists)
* [Semantic versioning](https://github.com/Uniswap/token-lists/blob/master/README.md#semantic-versioning)
* [Deploying your list](https://github.com/Uniswap/token-lists/blob/master/README.md#deploying-your-list)
