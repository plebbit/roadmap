# Demo roadmap

## `plebbit-js`

- [ ] Publish comment over pubsub
  - [x] Captcha
  - [x] Signature
  - [x] Encryption
  - [ ] HTTP gateway fallback if IPFS client undefined
  - [ ] Pubsub provider fallback if IPFS client undefined
- [ ] Get comment over IPFS/IPNS
  - [x] Verify author signature
  - [ ] Verify subplebbit owner signature
  - [ ] HTTP gateway fallback if IPFS client undefined
- [ ] Get subplebbit over IPNS
  - [x] Verify signature
  - [ ] HTTP gateway fallback if IPFS client undefined
- [ ] Get subplebbit pages over IPNS
  - [x] Verify author signature
  - [ ] Verify subplebbit owner signature
  - [ ] HTTP gateway fallback if IPFS client undefined

## `plebbit-react`

- [ ] Post page
- [x] Feed page
  - [x] Infinite scroll
  - [x] Loading skeleton
- [x] Submit post page
- [ ] Publish vote and captcha modal
- [x] Publish comment and captcha modal
- [ ] Auto login with default account

## `plebbit-react-hooks`

- [x] Accounts actions
  - [x] createAccount
  - [x] setAccount
  - [x] setActiveAccount
  - [x] setAccountsOrder
  - [x] publishComment
  - [x] publishCommentEdit
  - [x] publishVote
- [x] Accounts hooks 
  - [x] useAccount
  - [x] useAccountComments
  - [x] useAccountVotes
  - [x] useAccountVote
  - [x] useAccounts
  - [x] useAccountsActions
- [x] Comments hooks
  - [x] useComment
  - [x] useComments
- [x] Subplebbits hooks
  - [x] useSubplebbit
  - [x] useSubplebbits
- [x] Feeds hooks
  - [x] useFeed
  - [x] useBufferedFeeds

# MVP roadmap

## `plebbit-js`

- [ ] Publish comment over pubsub
  - [ ] Encrypt challenges and challengeAnswers
- [ ] Get comment over IPFS/IPNS
  - [ ] Resolve `author.address` ENS name
  - [ ] Verify NFT avatar signature
  - [ ] Add NFT URL to `comment.author.avatar.imageUrl`
- [ ] Get subplebbit over IPNS
  - [ ] Resolve `subplebbit.address` ENS name
- [ ] Get subplebbit pages over IPNS
  - [ ] Resolve `author.address` ENS name
  - [ ] Verify NFT avatar signature
  - [ ] Add NFT URL to `comment.author.avatar.imageUrl`
- [ ] IPNS over pubsub
- [ ] Peers block spam IP addresses
- [ ] Challenges
  - [ ] Text captcha challenge

## `plebbit-react`

- [ ] Challenges
  - [ ] Text captcha challenge
- [ ] Moderator/about pages
  - [ ] Subplebbit settings
  - [ ] Subplebbit appearance
  - [ ] Subplebbit rules
  - [ ] Subplebbit moderators
- [ ] Settings pages
  - [ ] Account
    - [ ] Language
    - [ ] Location
  - [ ] Profile
    - [ ] NFT avatar
    - [ ] Display name
    - [ ] Crypto wallet addresses (to receive tips and awards)
  - Safety & Privacy
    - [ ] Blocked addresses
- [ ] Own profile page
  - [ ] Edit NFT avatar
  - [ ] Edit display name
  - [ ] Edit crypto wallet addresses (to receive tips and awards)
- [ ] Feed page
  - [ ] Author address (ENS or 12 characters public key)
  - [ ] Author avatar image
  - [ ] Author flair
  - [ ] Post flair
  - [ ] Date
  - [ ] Full embed images
  - [ ] Small thumbnails
  - [ ] Share button
  - [ ] Block button
  - [ ] Sidebar links
  - [ ] Sidebar popular communities
  - [ ] Nicely display broken images and thumbnails
  - [ ] Switch sort types
- [ ] Translations
  - [ ] Arabic
  - [ ] Chinese
  - [ ] Hindi
  - [ ] Spanish
  - [ ] Russian
  - [ ] Japanese
  - [ ] Portuguese
  - [ ] German
  - [ ] Korean
  - [ ] French
  - [ ] Italian
  - [ ] Turkish
- [ ] Improve logo and 'plebbit' text light and dark mode
- [ ] Improve captcha modal design
- [ ] Search default subs

## `plebbit-react-hooks`

- [ ] Accounts actions
  - [ ] deleteAccount
  - [ ] importAccount
  - [ ] exportAccount
  - [ ] deleteComment
  - [ ] blockAddress
- [x] Accounts hooks
  - [x] useAccountNotifications
- [ ] Feeds hooks
  - [ ] useAuthorComments
- [ ] PLEB tipping on AVAX
- [ ] Gold and Silver NFT awards on AVAX
- [ ] Filter feed by language
- [ ] Filter feed by location

# Low priority

## `plebbit-js`

- [ ] Challenges
  - [ ] ERC20 staking challenge
  - [ ] ERC721 staking challenge
  - [ ] ERC20 tipping challenge
  - [ ] ERC20 balance challenge
  - [ ] ERC721 balance challenge
  - [ ] Video captcha challenge
  - [ ] Audio captcha challenge
  - [ ] More difficult image captcha challenge
- [ ] Migrate to typescript
- [ ] Mod subplebbit posts pages
  - [ ] Mod queue
  - [ ] Reports
  - [ ] Spam
  - [ ] Edited
  - [ ] Unmoderated
- [ ] Comment edit log
- [ ] Comment vote log
- [ ] CI/CD

## `plebbit-react`

- [ ] Moderator/about pages
  - [ ] Queues
    - [ ] Mod queue
    - [ ] Reports
    - [ ] Spam
    - [ ] Edited
    - [ ] Unmoderated
- [ ] Create multisub page
- [ ] Manage multisub page
- [ ] Migrate to typescript
- [ ] Comment edit log
- [ ] Comment vote log
- [ ] Integrated crypto wallet for desktop client
- [ ] Encrypt private key PEM with password at rest (similar to MetaMask)
- [ ] CI/CD

## `plebbit-react-hooks`

- [ ] Accounts actions
  - [ ] publishReport
  - [ ] saveComment
  - [ ] followComment
  - [ ] hideComment
  - [ ] followAuthor
  - [ ] limitAddress
- [ ] Round robin multiple pubsub providers and IPFS gateways
- [ ] Define all types
- [ ] Remove all typescript any and @ts-ignore
- [ ] CI/CD

## Misc

- [ ] PLEB DAO vote for curated NFT collection on AVAX
- [ ] PLEB DAO vote for curated multisubs on AVAX
- [ ] Moderator log (a `Page` of CommentEdit publications available both on `Subplebbit.posts` and `Comment.replies`)
- [ ] Vote log (a `Page` of CommentEdit publications available both on `Subplebbit.posts` and `Comment.replies`)
- [ ] Event/Meetup post type (to compete with Facebook and Meetup.com events)
- [ ] Marketplace post type (to compete with Facebook marketplace, Shopify, Amazon)
- [ ] Fundraiser post type (to compete with Gofundme and Kickstarter)
- [ ] Sync accounts between multiple devices
- [ ] Encrypt private key PEM with password at rest (similar to MetaMask)
- [ ] Native Android client, APK only, no app store
- [ ] Make `pubsub-provider` more spam resistant
- [ ] Share provider (a server that caches a plebbit page and hosts it on a random domain for 24h to easily share on other social medias)
