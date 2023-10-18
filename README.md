# Demo roadmap

## `plebbit-js`

- [x] Publish comment over pubsub
  - [x] Captcha
  - [x] Signature
  - [x] Encryption
  - [x] HTTP gateway fallback if IPFS client undefined
  - [x] Pubsub provider fallback if IPFS client undefined
  - [x] Add signature to `PubsubMessage` and validate `PubsubMessage.signature`
  - [x] Encrypt `ChallengeMessage.challenges` and `ChallengeAnswerMessage.answers`
  - [x] Include Plebbit and plebbit-js version in every pubsub message
- [x] Get comment over IPFS/IPNS
  - [x] Verify author signature
  - [x] Verify subplebbit owner signature
  - [x] HTTP gateway fallback if IPFS client undefined
  - [x] Validate `comment.link` is valid with `new URL(comment.link).protocol === 'https:'` (all posts, comments and replies, and in pages)
- [x] Get subplebbit over IPNS
  - [x] Verify Subplebbit.signature (sub owner must sign subplebbit updates otherwise IPNS provider can lie)
  - [x] HTTP gateway fallback if IPFS client undefined
- [x] Get subplebbit pages over IPNS
  - [x] Verify author signature
  - [x] HTTP gateway fallback if IPFS client undefined
- [x] Tests
  - [x] Tests run under 1 minute
  - [x] Concurrent mocha tests
  - [x] Concurrent karma tests
  - [x] Add CI
  - [x] Add CI including plebbit-react-hooks CI
  - [x] Add way to run only 1 file in mocha tests with CLI
- [x] Bind `Plebbit`, `Comment`. `Subplebbit`, `Pages` classses public methods

## `plebbit-react`

- [x] Post page
- [x] Feed page
  - [x] Infinite scroll
  - [x] Loading skeleton
- [x] Submit post page
- [x] Publish vote and captcha modal
- [x] Publish comment and captcha modal
- [x] Auto login with default account
- [x] Deploy demo to demo.plebbit.eth
- [ ] Electron client
  - [x] Add windows icon
  - [x] Add mac icon
  - [ ] Add linux .desktop file info and icon
  - [ ] Set up Plebbit app to open Plebbit links. Any link that starts with demo.plebbit.eth
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
- [x] Subplebbits hooks
  - [x] useSubplebbit
  - [x] useSubplebbits
  - [x] Make Cloudflare not cache IPNS requests
- [x] Feeds hooks
  - [x] useFeed
  - [x] useBufferedFeeds
- [x] Tests
  - [x] Add CI
  - [x] Clean up tests to be smaller and give better errors
  - [x] Add CI integration tests with plebbit-js (after the plebbit-js test are optimized)
  - [x] Add way to run only 1 file in mocha tests with CLI

# MVP roadmap

## `plebbit-js`

- [ ] Publish comment over pubsub
  - [x] Encrypt challenges and challengeAnswers
  - [ ] Queue pubsub publishing when more than 5 keepalive connections in the browser
- [ ] Get comment over IPFS/IPNS
  - [x] Resolve `author.address` ENS name
  - [x] Subplebbit owner adds comment.thumbnailUrl (optionally because it can leak IP)
  - [ ] Electron and Android client can fetch comment.thumbnailUrl when not already available (optionally because it can leak IP)
- [x] Get subplebbit over IPNS
  - [x] Resolve `subplebbit.address` ENS name
- [ ] Get subplebbit pages over IPNS
  - [x] Resolve `author.address` ENS name
- [ ] Multisubs
  - [ ] Implement `Plebbit.createMultisub(createMultisubOptions): Multisub`
  - [ ] Implement `Plebbit.getMultisub(multisubAddress): Multisub`
- [ ] Subplebbits
  - [ ] Implement `Plebbit.createSubplebbitEdit(createSubplebbitEditOptions): SubplebbitEdit`
- [x] IPNS over pubsub
- [ ] Peers block spam IP addresses
- [ ] Challenges
  - [ ] Text captcha challenge
- [x] Implement `Plebbit.listSubplebbits(): address[]`
- [x] Change dataPath to dataPath/subplebbits and dataPath/cache
- [ ] Implement `Plebbit.getDefaults()`
- [ ] Add `Plebbit.createSubplebbitEdit(createSubplebbitEditOptions)` and `CreateSubplebbitEditOptions` documentation to readme
- [x] Round robin multiple pubsub providers and IPFS gateways, change provider/gateway configs to arrays
- [ ] Make BlockchainProvider.rpcUrls an array, either to round robin or double validate responses
- [x] Figure out how to block IPFS files larger than the max publication size

## `plebbit-react`

- [ ] Challenges
  - [ ] Text captcha challenge
  - [x] Challenge success/fail notification
  - [ ] Information about the publication on the challenge modal
  - [ ] Multiple challenges with progress indicator (e.g. 1/4)
- [ ] Moderator/about pages
  - [ ] Subplebbit settings
    - [ ] Instructions to export/backup subplebbit (backup the file `${plebbit.dataPath}/subplebbits/${subplebbit.address}`)
    - [ ] Instructions to import subplebbit (copy the database file in `${plebbit.dataPath}/subplebbits/${subplebbit.address}`) and refresh
  - [x] Subplebbit appearance
  - [x] Subplebbit rules
  - [x] Subplebbit moderators
- [ ] Settings pages
  - [ ] Account
    - [ ] Language
    - [ ] Location
    - [x] Export
    - [x] Import
  - [ ] Profile
    - [x] NFT avatar
    - [x] Display name
    - [ ] Crypto wallet addresses (to receive tips and awards)
  - [ ] Safety & Privacy
    - [ ] Blocked addresses
- [ ] Own profile page
  - [x] Edit NFT avatar
  - [x] Edit display name
  - [ ] Edit crypto wallet addresses (to receive tips and awards)
- [ ] Feed page
  - [x] Author address (ENS or 14 characters public key)
  - [x] Author avatar image
  - [x] Author flair
  - [x] Post flair
  - [x] Date
  - [x] Full embed images
  - [x] Small thumbnails
  - [x] Share button
  - [ ] Block button
  - [x] Sidebar links
  - [x] Sidebar popular communities
  - [x] Nicely display broken images and thumbnails
  - [x] Switch sort types
- [ ] Comment page
  - [x] Display markdown
  - [x] Verify markdown <a> tags links don't allow remote execution in electron
  - [ ] Cross posts
- [x] Top menu
  - [x] Create more than 1 account
  - [x] Switch account
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
- [x] Pubsub HTTP client can open unlimited keepalive connections without timeout in electron
- [ ] Tests
  - [ ] Playright browser tests
  - [ ] Add CI playright browser tests
  - [ ] Add CI/CD on master merge using plebbit-js, plebbit-react-hooks and plebbit-react tests
- [x] Add config for progressive web app
- [x] Add config for react-native build to Android APK
- [x] Add Android APK to automatic releases
- [ ] Embeds
  - [ ] Twitter
  - [ ] Instagram
  - [ ] Twitch
  - [ ] Tiktok
  - [ ] Youtube
  - [ ] Odysee
  - [ ] Bitchute
  - [ ] Reddit
  - [ ] Streamable
  - [ ] Spotify
  - [ ] Imgur (not needed, they give direct links to .png)
  - [ ] Giphy (not needed, they give direct links to .gif)
  - [ ] Rumble (doesn't seem possible without API)
  - [ ] Soundcloud (doesn't seem possible without API)
  - [ ] Bandcamp (doesn't seem possible without API)
  - [ ] Google Drive (need to research, low priority)

## `plebbit-react-hooks`

- [ ] Accounts actions
  - [ ] publishSubplebbitEdit
  - [x] deleteAccount
  - [x] importAccount
  - [x] exportAccount
  - [ ] deleteComment
  - [x] blockAddress
- [x] Accounts hooks
  - [x] useAccountNotifications
- [ ] Feeds hooks
  - [ ] useRepliesFeed
- [x] Authors hooks
  - [x] useAuthorComments or useAuthorFeed
  - [x] hook to get total karma and other profile info (possibly just include it in useAuthorFeed)
- [ ] Multisubs hooks
  - [ ] useFeed should resolve multisubs
  - [ ] useMultisub
  - [ ] createMultisub
- [ ] Tipping
- [ ] Gold and Silver NFT awards
- [ ] Filter feed by language
- [ ] Filter feed by location
- [ ] Add account.warnings for ENS not resolving properly
- [ ] useResolvedSubplebbitAddress for debugging setting up ENS in a subplebbit
- [ ] Filter blocked addresses from accounts notifications
- [x] Migrate feeds React context to Zustand

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
- [x] Security
  - [x] Context isolated desktop only functions to use in the electron client
- [ ] Algo for most anonymous padding size for publication encryption
- [x] Make createSigner a native function with a `sign()` method to protect privateKey against XSS
- [ ] Sort by active
- [ ] Pass `acceptedChallengeTypes` in Plebbit constructor
- [x] Make `updateInterval` and `publishInterval` public APIs
- [ ] API for `postTitleMinLength`
- [ ] Comment.archived and subplebbit.settings.archiveTimestampOlderThan, archiveLastReplyTimestampOlderThan
- [ ] Spec for public gateway providers and public pubsub providers challenges
- [x] Retry infinity getComment, getSubplebbit, getPage with a global timeout in plebbitOptions
- [ ] Comment.linkRemoved to remove only the link, like on 4chan

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
- [x] Add markdown XSS examples in content mock
- [ ] Make list of warnings and display them randomly in feeds, e.g. warn that subplebbits can be hacked and display scams. Maybe have a removable sticky with a list of common scams
- [ ] Embed IPFS webui inside the electron app in the settings or profile page
- [x] Notification count in ( ) and post.title in meta title
- [ ] Web of trust recommendations from authors, i.e. look at the authors I upvote and find the subs they post in and recommend them
- [ ] Playlist with autoplay for video/audio

## `plebbit-react-hooks`

- [ ] Accounts actions
  - [ ] publishReport
  - [ ] saveComment
  - [ ] followComment
  - [x] hideComment
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
- [ ] Add statuses to all hooks, like success, error, ready, progress, etc
- [ ] Sort by active
- [ ] Indicator to what HTML tag to use by analyzing comment.link (e.g. `useCommentLinkTagName(commentLink?: string): 'a' | 'img' | 'video' | 'audio'`)
- [ ] Implement useThumbnailUrl() on desktop and android
- [ ] Hook for plebbit and IPFS stats
- [ ] Block communities / comments / authors based on keyword / tag / language / etc

## Misc

- [ ] PLEB reward interface for best posts by plebbit team
- [ ] ERC20 reward interface for best posts by subplebbit owners
- [ ] PLEB DAO vote for curated NFT collection
- [ ] PLEB DAO vote for curated multisubs
- [ ] Moderator log (a `Page` of CommentEdit publications available both on `Subplebbit.posts` and `Comment.replies`)
- [ ] Vote log (a `Page` of CommentEdit publications available both on `Subplebbit.posts` and `Comment.replies`)
- [ ] Event/Meetup post type (to compete with Facebook and Meetup.com events)
- [ ] Marketplace post type (to compete with Facebook marketplace, Shopify, Amazon)
- [ ] Fundraiser post type (to compete with Gofundme and Kickstarter)
- [ ] Sync accounts between multiple devices
- [ ] Encrypt private key with password at rest (similar to MetaMask)
- [ ] Publish Android APK on F-Droid
- [ ] Make pubsub-provider and ipfs gateway more spam resistant using provider catchas on top of subplebbit captchas (as part of the protocol)
- [ ] Share provider (a server that caches a plebbit page and hosts it on a random domain for 24h to easily share on other social medias)
- [x] 4chan interface
- [ ] Discourse interface
- [x] Validate IPFS CIDs and content gotten from public IPFS gateways (because they can lie)
- [ ] Update desktop version over IPFS
- [ ] CLI client
- [ ] JSON-RPC client
- [ ] Build open source plebbit archiver
- [ ] Integrate P2P DMs from another project
- [ ] Integrate P2P live threads (chat) from another project
- [ ] Integrate comment.link for livestreaming (with live thread)
- [ ] Develop a tool to scrape a subreddit and copy its posts to Plebbit
- [ ] Fallback to IPFS provider on desktop app when P2P not supported, like on cellular
- [ ] Subplebbit uptime monitor and alerter
- [ ] Video/audio player android/android tv client, similar to youtube, to play youtube, soundcloud, rumble, etc links directly, without ads and without visiting the original video site
- [ ] ENS over IPFS, create a trie of all ENS domains, and resolve the new trie daily using IPNS, to resolve ENS over IPFS, without needing an ETH provider
- [ ] Configurable search and recommendation RPC, several centralized providers could provide their API and the user can choose which API to use
- [ ] Substack / patreon / medium like interface, to publish long text and paywalled content
- [ ] Stackexchange like interface with LaTeX support
- [ ] Centralized service to index/search plebbit, like warosu.org
- [ ] Centralized service to run subs for others for free
- [ ] vBulletin v3 client
