# Demo roadmap

## `plebbit-js`

- [ ] Publish comment over pubsub
  - [x] Captcha
  - [x] Signature
  - [x] Encryption
  - [x] HTTP gateway fallback if IPFS client undefined
  - [x] Pubsub provider fallback if IPFS client undefined
  - [ ] Add signature to `PubsubMessage` and validate `PubsubMessage.signature`
- [ ] Get comment over IPFS/IPNS
  - [x] Verify author signature
  - [ ] Verify subplebbit owner signature
  - [x] HTTP gateway fallback if IPFS client undefined
  - [ ] Validate `comment.link` is valid with `new URL(comment.link).protocol === 'https:'` (all posts, comments and replies, and in pages)
- [ ] Get subplebbit over IPNS
  - [x] Verify signature
  - [x] HTTP gateway fallback if IPFS client undefined
- [ ] Get subplebbit pages over IPNS
  - [x] Verify author signature
  - [ ] Verify subplebbit owner signature
  - [x] HTTP gateway fallback if IPFS client undefined
- [ ] Tests
  - [ ] Tests run under 1 minute
  - [ ] Concurrent mocha tests
  - [ ] Concurrent karma tests
  - [ ] Add CI
  - [ ] Add CI including plebbit-react-hooks CI
  - [ ] Add way to run only 1 file in mocha tests with CLI
- [ ] Bind `Plebbit`, `Comment`. `Subplebbit`, `Pages` classses public methods

## `plebbit-react`

- [ ] Post page
- [x] Feed page
  - [x] Infinite scroll
  - [x] Loading skeleton
- [x] Submit post page
- [ ] Publish vote and captcha modal
- [x] Publish comment and captcha modal
- [ ] Auto login with default account
- [x] Deploy demo to demo.plebbit.eth
- [ ] Electron client
  - [x] Builds and runs on Linux
  - [ ] Builds and runs on Windows
  - [x] Builds and runs on Mac

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
- [ ] Subplebbits hooks
  - [x] useSubplebbit
  - [x] useSubplebbits
  - [ ] Make Cloudflare not cache IPNS requests
- [x] Feeds hooks
  - [x] useFeed
  - [x] useBufferedFeeds
- [ ] Tests
  - [x] Add CI
  - [ ] Clean up tests to be smaller and give better errors
  - [ ] Add CI integration tests with plebbit-js (after the plebbit-js test are optimized)
  - [ ] Add way to run only 1 file in mocha tests with CLI

# MVP roadmap

## `plebbit-js`

- [ ] Publish comment over pubsub
  - [ ] Encrypt challenges and challengeAnswers
  - [ ] Queue pubsub publishing when more than 5 keepalive connections in the browser
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
- [ ] Multisubs
  - [ ] Implement `Plebbit.createMultisub(createMultisubOptions): Multisub`
  - [ ] Implement `Plebbit.getMultisub(multisubAddress): Multisub`
- [ ] Subplebbits
  - [ ] Implement `Plebbit.createSubplebbitEdit(createSubplebbitEditOptions): SubplebbitEdit`
- [ ] IPNS over pubsub
- [ ] Peers block spam IP addresses
- [ ] Challenges
  - [ ] Text captcha challenge
- [ ] Implement `Plebbit.listSubplebbits(): address[]`
- [ ] Change dataPath to dataPath/subplebbits and dataPath/cache
- [ ] Implement `Plebbit.getDefaults()`
- [ ] Add `Plebbit.createSubplebbitEdit(createSubplebbitEditOptions)` and `CreateSubplebbitEditOptions` documentation to readme

## `plebbit-react`

- [ ] Challenges
  - [ ] Text captcha challenge
  - [ ] Challenge success/fail notification
  - [ ] Information about the publication on the challenge modal
  - [ ] Multiple challenges with progress indicator (e.g. 1/4)
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
  - [ ] Safety & Privacy
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
- [ ] Comment page
  - [ ] Display markdown
  - [ ] Verify markdown <a> tags links don't allow remote execution in electron
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
- [ ] Pubsub HTTP client can open unlimited keepalive connections without timeout in electron
- [ ] Tests
  - [ ] Playright browser tests
  - [ ] Add CI playright browser tests
  - [ ] Add CI/CD on master merge using plebbit-js, plebbit-react-hooks and plebbit-react tests

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
- [ ] Remove all typescript any and @ts-ignore
- [ ] Security
  - [ ] Context isolated desktop only functions to use in the electron client

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

## Misc

- [ ] PLEB reward interface for best posts by plebbit team
- [ ] ERC20 reward interface for best posts by subplebbit owners
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
