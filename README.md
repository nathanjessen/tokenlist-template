# tokenlist

[![Schema](https://github.com/nathanjessen/tokenlist/workflows/Schema/badge.svg)](https://github.com/nathanjessen/tokenlist/actions?query=workflow%3ASchema)

Template for creating a tokenlist and validating against Uniswap token schema.

## Resources

* [Ethereum token lists](https://tokenlists.org/)
* [https://github.com/Uniswap/token-lists](https://github.com/Uniswap/token-lists)

## Semantic versioning

The `all.tokenlist.json` uses [Semantic versioning](https://github.com/Uniswap/token-lists/blob/master/README.md#semantic-versioning) as described by Uniswap.

## Validation

Validation must pass for the tokenlist to work on Uniswap and to prevent the tokenlist from being delisted.

### Local Testing

The `all.tokenlist.json` is validated against Uniswap's tokenlist schema.

To test locally,

```
# Install dependencies
npm install

# Run test script
npm start
```

If there is an error, the error will be output to the terminal.

### GitHub Workflow

A GitHub workflow has also been included that automatically tests for validation any time there is a push or pull request.

## Updating the Tokenlist

### New Token

- At the bottom of `all.tokenlist.json` increase the "minor" number by 1. Set the "patch" number to 0.
- Add your new token to the end of the "token" array.
- Add the token image to the img folder.

Each entry should follow the format below where the logoURI is the path to the raw image file on GitHub or the URL if you host the files with a different provider.

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
- Remove the token from the json file
- Remove the token image from the img folder

## Repository Settings

A best practice would be to create a new branch for any change and create a pull request to master. I recommend branch protection rules to prevent invalid changes from being merged into the repository.

Settings -> Branches

Branch protection rules -> Add rule

Branch name pattern: `master`

Check the boxes for

* Require status checks to pass before merging
* Require branches to be up to date before merging
* build
* Include administrators

Save changes

## Deploying your list

You can paste the link to your raw json file in Uniswap

`https://raw.githubusercontent.com/nathanjessen/tokenlist/master/all.tokenlist.json`

or
you can submit the list to [Ethereum token lists](https://tokenlists.org/).

More information can be found at [https://github.com/Uniswap/token-lists#deploying-your-list](https://github.com/Uniswap/token-lists#deploying-your-list)

After you've used the tokenlist on Uniswap, Uniswap will discover any change you make to the tokenlist as long as you follow the Semantic versioning instructions.
