# COT-Tokens-DAO3L

1) Owner can mint limit tokens

2) Owner can mint 5% tokens from totalSupply() per year

3) 10B to Team vested (time is seting in the migration)

4) 20B will go to owner wallet for sales manually

(optional)
5) pool address can mint, this function commented out (optional)

[Correct mint limit (no more no less) (video)](https://vk.com/videos223443924?z=video223443924_456239565%2Fpl_223443924_-2)

[Correct mint input limit (video)](https://vk.com/videos223443924?z=video223443924_456239559%2Fpl_223443924_-2)

[Correct mint 5% per year (in our case 5 minutes) (video)](https://vk.com/videos223443924?z=video223443924_456239561%2Fpl_223443924_-2)

[Vesting (video)](https://vk.com/videos223443924?z=video223443924_456239556%2Fpl_223443924_-2)

(OPTIONAL)
[Allow mint for pool address (if pool balance > total / 2) (comment) (video)](https://vk.com/videos223443924?z=video223443924_456239555%2Fpl_223443924_-2)


# HOW MintNewTokens WORKS

1) Token pass owner to MintNewTokens contract.

2) Only MintNewTokens can call function mint in Token contract.

3) Owner MintNewTokens contract can call function mint through MintNewTokens contract.

Such a scheme is safe, and we limit the ability of the owner to create new tokens.

# So if we want create mint function based on vote we have five options

1) Override function transferOwnership, that in the future to be able to transfer the owner to a contract with a voting function. (problem - the administrator of transferOwnership function can at any time designate himself as the owner, and start mint new tokens)

2) Write vote function immediately! 

3) Leave the pool address function as a basis for voting. (it works reliably and safely)

4) To make MintNewTokens as Upgradable Smart Contract and add 51% vote in future.

5) Do not assign owner a contract, but this means that the owner can create new tokens in any quantity
