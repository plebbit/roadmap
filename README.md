# Plebbit roadmap

## Demo roadmap

### `plebbit-js`

- [ ] Publish comment over pubsub
  - [x] Captcha
  - [x] Signature
  - [x] Encryption
  - [ ] HTTP gateway fallback if IPFS client undefined
  - [ ] Pubsub provider fallback if IPFS client undefined
- [ ] Get comment over IPFS/IPNS
  - [x] Verify author signature
  - [ ] Resolve `author.address` ENS name
  - [ ] Verify subplebbit owner signature
  - [ ] Verify NFT avatar signature
  - [ ] Add NFT URL to `comment.author.avatar.imageUrl`
  - [ ] HTTP gateway fallback if IPFS client undefined
- [ ] Get subplebbit over IPNS
  - [x] Verify signature
  - [ ] Resolve `subplebbit.address` ENS name
- [ ] Get subplebbit pages over IPNS
  - [x] Verify author signature
  - [ ] Resolve `author.address` ENS name
  - [ ] Verify subplebbit owner signature
  - [ ] Verify NFT avatar signature
  - [ ] Add NFT URL to `comment.author.avatar.imageUrl`
  - [ ] HTTP gateway fallback if IPFS client undefined

### `plebbit-react`

- [ ] Post page
- [ ] Subplebbit feed page
- [ ] Multisub feed page (p/home, p/all, p/dao)
- [ ] Own profile page
- [ ] Settings page
- [ ] Submit post page
- [ ] Moderator/about pages

### `plebbit-react-hooks`

## MVP roadmap

## Low priority

- [ ] Sync accounts between multiple devices
- [ ] Encrypt private key PEM with password at rest (similar to MetaMask)
- [ ] Event/Meetup post type (to compete with Facebook and Meetup.com events)
- [ ] Marketplace post type (to compete with Facebook marketplace, Shopify, Amazon)
- [ ] Fundraiser post type (to compete with Gofundme and Kickstarter)
- [ ] Native Android client, APK only, no app store
