# LensProtocolLifeHacks

This repo is here to save life hacks.

## Get list of followers for a specific user
*We will asume you know the user address and you want to track his default Lens profile*
1. [Get user's Lens profile id](#get-default-lens-profile-id-of-a-specific-address)
2. [Get user's Follow contract](#get-users-follow-contract)
3. [Get user's total number of followers](#get-users-total-number-of-followers)
4. [Get all user's followers](#get-all-users-followers)

### Smart contracts:
- LensHub Proxy: 0xDb46d1Dc155634FbC732f92E853b10B288AD5a1d ([doc](https://docs.lens.xyz/docs/deployed-contract-addresses))


## Get default Lens profile id of a specific address:

*Call [LensHub Proxy](#smart-contracts) **DefaultProfile** function*

DefaultProdile(walletAddress)

**return** LensProfileId

## Get user's follow contract:

*Call [LensHub Proxy](#smart-contracts) **getFollowNFT** function*

getFollowNFT(LensProfileId)

**return** FollorNFTAddress

## Get user's total number of followers
*Call [FollowNFTAddress](#get-users-follow-contract) as FollowNFT proxy ([doc](https://docs.lens.xyz/docs/deployed-contract-addresses)) **totalSupply** function*

totalSupply()

**return** totalSupply (type unit256)

## Get all user's followers
*Loop Call [FollowNFTAddress](#get-users-follow-contract) as FollowNFT proxy ([doc](https://docs.lens.xyz/docs/deployed-contract-addresses)) **tokenId** function*

ownerOf(tokenId)

**return** followerAddress


