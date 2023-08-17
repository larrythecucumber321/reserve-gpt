Link: https://reserve.org/protocol/rtokens/#non-compatible-erc20-assets
Title: Non-compatible ERC20 assets

The following types of ERC20s are not supported to be used directly in an RToken system:

Rebasing Tokens that return yields by increasing the balances of users
Tokens that take a "fee" on transfer
Tokens that do not expose the decimals() in their interface. Decimals should always be between 1 and 18.
ERC777 tokens which could allow reentrancy attacks
Tokens with multiple entry points (multiple addresses)
Tokens that do not adhere to the ERC20 standard in general

These tokens should be be wrapped into a compatible ERC20 token to be used within the protocol. A concrete example is the use of Static ATokens for Aave V2.
