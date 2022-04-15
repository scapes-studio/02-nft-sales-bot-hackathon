# Hackathon #2: NFT Sales Bot

![hackathon2](https://user-images.githubusercontent.com/2725836/163633528-a3ccf108-3efd-434b-91cc-ff47d1f5ad3c.png)

**Topic:** Open Source Package for cross platform tracking of NFT Sales.

**Reward Pool: 1.5 ETH & 3 Scapes**
<small>
> The winning project will be paid 0.1 ETH. <br>
0.25 ETH goes to the submissions voted for 2nd and 3rd place. <br>
All three winning projects will get one scape.
</small>

**Deadline: Sunday, 24th of April; 24:00 ET**

## Intro

Our [first hackathon](https://github.com/punkscape/01-rarity-analyser-hackathon) was a great success, with five teams building open source rarity analyzer toolkits. We're pleased to finally re-start this initiative and kick off our second round.

Most NFT collections maintain a sales bot for Twitter and Discord. While there are a few open-source solutions out there already, all share one issue: They rely on the [OpenSea API](https://docs.opensea.io/reference/api-overview) to function and don't track sales from other platforms like [Looksrare](https://looksrare.org) or [X2Y2](https://x2y2.io/).
More Marketplaces are on the horizon.

Why not circumvent all of this and build a sales bot that watches `Transfer`-Events right on the collection contract? This is what this Hackathon is about...

## Let's get it!
- If you are a single developer or a team of buddies, then this is for you!
- The second PunkScapes Hackathon will be launched with the goal of developing general purpose sales trackers
  1. track sales right from the smart contract, without the need for third party APIs
  2. requires only the smart contract address to function
  3. integrates with the Twitter and Discord APIs to publish sales
  4. is configurable as to the notification messages sent out (e.g. text, image, ...)
  5. has easy instructions for others to add their collection metadata, install the app on a simple server or platform (like Heroku / DigitalOcean / ...)
- Deadline for the submission of completed projects is 25.04.2022 00:00 ET.
- The developed submissions are to be open sourced under the MIT license.
- All submissions will be voted on by the PunkScape core team jury as well as all other participating developers / teams..
- Please choose a common programming language/environment like NodeJS or Python.

## Requirements:

1. The app *has to* keep track of all sales (Transfers with value) on the collection smart contract.
2. The app *has to* integrate with Discord and post a notification message for each sale
3. The app *should* integrate with Twitter and post a notification tweet for each sale. The app *may* also integrate with other platforms like Telegram.
4. The app *has to* work with `ERC721` token contracts and *may* also be compatible with `ERC1155` token contracts.
5. The app *has to* extract ETH value behind transfers and correctly report it. It also *should* track WETH transfers and *may* track other arbitrary tokens transferred.
6. There *must* be easy to follow documentation for other developers on how to configure and deploy the bot to a server.
7. You have to hold a OneDayPunk to take part in the hackathon. They are currently available for ~30$ on [OpenSea](https://opensea.io/collection/onedaypunks). If you would like to take part but economically can't afford to right now, please reach out to jalil#1001 on [Discord](https://discord.gg/Se9V2B4VEZ) and we'll figure something out.

## Technical Details

- All modern NFTs implement either the `ERC721` or the `ERC1155` token standard. All token transfers are kept track of via a `Transfer` event emitted by the contract whenever an token changes hands.
- In the case of sales, the Transactions emitting these Events also contain a message `value`, which corresponds to the ETH transferred during the transaction – normally the price of the NFT. Of course there are edge cases when a single transaction contains transfers for multiple tokens or tokens aren't purchased with pure ETH but for example WETH.
- The bot should be able to take in a starting `block` (Ethereum Block), to report on historical sales data.
- You can use a library like [Ethers JS](https://docs.ethers.io/v5) to watch transfers. You will also need a JSON-RPC Provider – easiest is via an account with [Alchemy](https://www.alchemy.com/) or [Infura](https://infura.io/).

## Sponsors

50% of all Secondary Sales of the [PunkScape NFT](https://opensea.io/collection/punkscapes) are put into a community vault which funds these initiatives. So thank you to all the buyers of scapes!

We'll host these monthly, so watch out for the next one!
