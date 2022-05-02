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
- [ ] Subplebbit feed page
- [ ] Multisub feed page (p/home, p/all, p/dao)
- [ ] Own profile page
- [ ] Settings page
- [ ] Submit post page
- [ ] Moderator/about pages

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

# Low priority

## `plebbit-react-hooks`

- [ ] Accounts actions
  - [ ] publishReport
  - [ ] saveComment
  - [ ] followComment
  - [ ] hideComment
  - [ ] followAuthor
  - [ ] limitAddress

## Misc

- [ ] Moderator log (a `Page` of CommentEdit publications available both on `Subplebbit.posts` and `Comment.replies`)
- [ ] Vote log (a `Page` of CommentEdit publications available both on `Subplebbit.posts` and `Comment.replies`)
- [ ] Event/Meetup post type (to compete with Facebook and Meetup.com events)
- [ ] Marketplace post type (to compete with Facebook marketplace, Shopify, Amazon)
- [ ] Fundraiser post type (to compete with Gofundme and Kickstarter)
- [ ] Sync accounts between multiple devices
- [ ] Encrypt private key PEM with password at rest (similar to MetaMask)
- [ ] Native Android client, APK only, no app store
