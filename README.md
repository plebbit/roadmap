# Demo roadmap

## `plebbit-js`

- [ ] Publish comment over pubsub
  - [x] Captcha
  - [x] Signature
  - [x] Encryption
  - [x] HTTP gateway fallback if IPFS client undefined
  - [x] Pubsub provider fallback if IPFS client undefined
  - [ ] Add signature to `PubsubMessage` and validate `PubsubMessage.signature`
  - [ ] Encrypt `ChallengeMessage.challenges` and `ChallengeAnswerMessage.answers`
  - [ ] Include Plebbit and plebbit-js version in every pubsub message
- [ ] Get comment over IPFS/IPNS
  - [x] Verify author signature
  - [ ] Verify subplebbit owner signature
  - [x] HTTP gateway fallback if IPFS client undefined
  - [ ] Validate `comment.link` is valid with `new URL(comment.link).protocol === 'https:'` (all posts, comments and replies, and in pages)
- [ ] Get subplebbit over IPNS
  - [ ] Verify Subplebbit.signature (sub owner must sign subplebbit updates otherwise IPNS provider can lie)
  - [x] HTTP gateway fallback if IPFS client undefined
- [x] Get subplebbit pages over IPNS
  - [x] Verify author signature
  - [x] HTTP gateway fallback if IPFS client undefined
- [ ] Tests
  - [ ] Tests run under 1 minute
  - [ ] Concurrent mocha tests
  - [ ] Concurrent karma tests
  - [ ] Add CI
  - [ ] Add CI including plebbit-react-hooks CI
  - [ ] Add way to run only 1 file in mocha tests with CLI
- [x] Bind `Plebbit`, `Comment`. `Subplebbit`, `Pages` classses public methods

## `plebbit-react`

- [ ] Post page
- [x] Feed page
  - [x] Infinite scroll
  - [x] Loading skeleton
- [x] Submit post page
- [x] Publish vote and captcha modal
- [x] Publish comment and captcha modal
- [x] Auto login with default account
- [x] Deploy demo to demo.plebbit.eth
- [ ] Electron client
  - [ ] Add windows icon
  - [ ] Add mac icon
  - [ ] Add linux .desktop file info and icon
  - [x] Builds and runs on Linux
  - [x] Builds and runs on Windows
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
  - [ ] Subplebbit owner adds comment.thumbnailUrl (optionally because it can leak IP)
  - [ ] Electron and Android client can fetch comment.thumbnailUrl when not already available (optionally because it can leak IP)
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
- [ ] Round robin multiple pubsub providers and IPFS gateways, change provider/gateway configs to arrays
- [ ] Figure out how to block IPFS files larger than the max publication size

## `plebbit-react`

- [ ] Challenges
  - [ ] Text captcha challenge
  - [ ] Challenge success/fail notification
  - [ ] Information about the publication on the challenge modal
  - [ ] Multiple challenges with progress indicator (e.g. 1/4)
- [ ] Moderator/about pages
  - [ ] Subplebbit settings
    - [ ] Instructions to export/backup subplebbit (backup the file `${plebbit.dataPath}/subplebbits/${subplebbit.address}`)
    - [ ] Instructions to import subplebbit (copy the database file in `${plebbit.dataPath}/subplebbits/${subplebbit.address}`) and refresh
  - [ ] Subplebbit appearance
  - [ ] Subplebbit rules
  - [ ] Subplebbit moderators
- [ ] Settings pages
  - [ ] Account
    - [ ] Language
    - [ ] Location
    - [ ] Export
    - [ ] Import
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
  - [ ] Author address (ENS or 14 characters public key)
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
- [ ] Top menu
  - [ ] Create more than 1 account
  - [ ] Switch account
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
- [ ] Add config for progressive web app
- [ ] Add config for react-native build to Android APK
- [ ] Add Android APK to automatic releases

## `plebbit-react-hooks`

- [ ] Accounts actions
  - [ ] publishSubplebbitEdit
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
- [ ] Add account.warnings for ENS not resolving properly

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
  - [ ] Settings for less or no captcha for users with karma in the sub
  - [ ] Settings for less or no captcha for users with karma in other subs
- [x] Migrate to typescript
- [ ] Mod subplebbit posts pages
  - [ ] Mod queue
  - [ ] Reports
  - [ ] Spam
  - [ ] Edited
  - [ ] Unmoderated
- [ ] Report publication type (possibly just use CommentEdit, need to think of design)
- [ ] Comment edit log
- [ ] Comment vote log
- [ ] Remove all typescript any and @ts-ignore
- [ ] Security
  - [ ] Context isolated desktop only functions to use in the electron client
- [ ] Algo for most anonymous padding size for publication encryption

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
- [ ] Interface to choose and sign NFT avatars so users don't have to go to Etherscan
- [ ] Securely embed Twitter/Youtube/etc. (if possible to do securely)
- [ ] Lazy resolve author addresses

## `plebbit-react-hooks`

- [ ] Accounts actions
  - [ ] publishReport
  - [ ] saveComment
  - [ ] followComment
  - [ ] hideComment
  - [ ] followAuthor
  - [ ] limitAddress
- [ ] Multisubs
  - [ ] `usePlebbitDefaults()`
  - [ ] `useMultisub`
  - [ ] `useMultisubs`
  - [ ] incorporate multisubs with useFeed()
  - [ ] `createMultisub()`
- [ ] Define all types
- [ ] Remove all typescript any and @ts-ignore
- [ ] Progressive scrolling of replies in a post for posts with 100+ replies
- [ ] Include accountComments and accountVotes when importing/exporting
- [ ] Don't subscribe to all accountComments at once, queue new ones with higher priority, and old ones with lower priority

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
- [ ] Make `pubsub-provider` more spam resistant using provider catchas on top of subplebbit captchas (as part of the protocol)
- [ ] Make fast IPNS provider
- [ ] Share provider (a server that caches a plebbit page and hosts it on a random domain for 24h to easily share on other social medias)
- [ ] 4chan interface
- [ ] Discourse interface
- [ ] Validate IPFS CIDs and content gotten from public IPFS gateways (because they can lie)
- [ ] Update desktop version over IPFS
- [ ] CLI client
- [ ] JSON-RPC client
- [ ] Build open source plebbit archiver
