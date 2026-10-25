<p align="center">
  <img src="FORGORA-logo.png" alt="Forgora" width="96" />
</p>

<h1 align="center">Forgora</h1>

<p align="center"><strong>It remembers you while you hold.</strong></p>

<p align="center">
  <a href="https://forgora.chat">Website</a> ·
  <a href="https://app.forgora.chat">App</a> ·
  <a href="https://forgora.chat/docs">Docs</a> ·
  <a href="https://forgora.chat/receipt">Launch receipt</a> ·
  <a href="https://x.com/forgora_ai">X</a>
</p>

---

## About

Forgora is a private AI chat on Robinhood Chain whose memory of you is locked to your wallet.

Hold `$FORGORA` above your tier's line and the AI remembers every conversation: your projects, your people, your plans, the way you write. Drop below the line for 24 hours and the key to that memory is destroyed. The memory is gone for good, and the public Forgotten counter goes up by one.

Most AI chats keep a memory of you on their side for as long as they choose, and deleting it is a request you cannot verify. Most AI tokens sell credits that nobody needs a coin to use. Forgora addresses both: the memory is the product, and the coin is the key to it.

The name comes from *forgor*, the internet's way of saying *forgot*.

| | |
|---|---|
| Chain | Robinhood Chain (EVM L2, chainId 4663) |
| Token | `$FORGORA`, 1,000,000,000 fixed supply, no mint, no tax |
| Contract | `0x3f4b91f5467d160647b623c820f10acca8e728b0` |
| Launch | Pons launchpad, fair launch, no presale, no team allocation |
| Memory line | 50,000 `$FORGORA` (Spark tier) |
| Grace period | 24 hours below the line |

Only trust the contract address above and the one shown on [forgora.chat/receipt](https://forgora.chat/receipt). Any other address claiming to be `$FORGORA` is not official.

## Features

### Wallet-locked memory

- **Sign in with a signature.** No email, no password, no transaction, no gas.
- **Memory follows your balance.** Forgora reads your `$FORGORA` balance at the latest block on sign-in and every 30 minutes after.
- **Three memory states.** `REMBER` (at or above the line, memory grows), `GRACE` (24-hour clock after a sell, memory still readable), `FORGOR` (key destroyed, nothing to restore).
- **Guest mode.** Wallets without enough `$FORGORA` get 3 free messages a day with no memory kept.

### Forgetting you can rely on

- **One data key per wallet.** A random 256-bit key encrypts every memory, chat and chat title. The store holds ciphertext only.
- **Envelope encryption.** The data key is stored wrapped by the key service, which unwraps it only while the wallet is above its line.
- **Short-lived sessions.** An unwrapped key lives in memory for 30 minutes and is never written to disk.
- **Destroy the key, not a row.** Forgetting destroys the wrapped key, then deletes the ciphertext. No one can restore it, including the team.

### Grace clock

- A watcher on `$FORGORA` Transfer events starts a 24-hour clock within about a minute of a balance falling below the line.
- The app shows a countdown banner with three options: **Buy back**, **Download history**, **Let it go**.
- Buying back before zero stops the clock, keeps the memory and keeps the streak.
- After zero, buying back starts a new memory from zero. The old one cannot return.

### Full control over your memory

- Read every memory the AI keeps on you, on one page.
- Edit or delete any single memory.
- Download your full chat history at any time.
- **Forget now:** the same destruction as the grace clock, done on purpose.
- Link cold wallets by signature so their balance counts toward your tier without moving coins.

### Tiers

| Tier | Hold | Access |
|---|---|---|
| Guest | 0 | 3 free messages a day, guest credits after that, no memory |
| Spark | 50,000 | Memory on (30 days deep), 60 messages a day |
| Keeper | 500,000 | Full memory with no depth limit, 300 messages and 10 pictures a day, up to 3 linked cold wallets |
| Vault | 5,000,000 | 1,000 messages and 40 pictures a day, agents that work with your memory, early Memory API access |

Lines are set in tokens, not dollars, so they can be checked on chain at any block.

### Anti-gaming

- **Flash buys:** balance checked at the latest block plus a 30-minute session key, so a borrowed balance unlocks nothing.
- **Wallet hopping:** each wallet has its own memory. Moving coins does not move the memory.
- **What counts:** coins in wallets you sign in with or link by signature. LP positions, exchange balances and lent tokens do not count.
- **Streaks:** derived from the key's age on the server, not from anything a user submits.

### Public transparency

- **Launch receipt** (`/receipt`): the dev wallet, the creation transaction, the dev buy and its 90-day time-lock, every wallet that bought in the first 60 seconds, and a cluster check for wallets funded from one source.
- **Forgotten page** (`/forgotten`): memories forgotten, saved by a rebuy, and alive. Ages and times only, never a wallet or any content.
- **ForgetRegistry** (phase 2): an on-chain contract that emits `Forgotten` and `Saved` events with a hashed key id and the memory's age, so the counter becomes a count of public events.

### Memory system

- **REMBER streak:** days in a row above the line, shown on the memory page.
- **Depth levels 1 to 5:** counted from the number of kept memories, never from their content.
- **Share cards:** `REMBER`, `SAVED` and `FORGOR`, showing only numbers the owner chooses to share.

### Privacy

- No request logs at the inference endpoints.
- No analytics on chat pages and no ad pixels anywhere.
- Your words are never sold, shared or used for training.
- Rate limits per wallet and per IP on every endpoint.

## Trust model

In phase 1 the key service runs on Forgora's own servers. Memories are encrypted at rest, keys are destroyed on schedule and every destruction is logged, but you are trusting that key service.

Phase 3 moves the key service and inference into confidential-computing hardware with fixed, attested code, and the app shows the attestation for every session. From then on, nobody at Forgora can read or restore a memory, by design rather than by promise.

## Roadmap

| Phase | Timing | Scope |
|---|---|---|
| 1. MVP | Weeks 1 to 3 | Sign-in, chat, memory by tier, envelope encryption, grace clocks, shredder, memory page, guest credits, receipt page, launch |
| 2. Growth | Months 1 to 2 | Pictures, linked cold wallets, ForgetRegistry, share cards, quarterly holder vote on tier lines, mobile web app |
| 3. Sealed | Months 3 to 4 | Sealed key service and inference with attestation, independent review published in full |
| 4. Ecosystem | Months 6 to 12 | Memory API with signed, expiring grants, agents with memory, memory across partner apps |

## Disclaimer

Forgora is a community project and is not affiliated with Robinhood Markets, any brokerage, the launchpad or any model provider. `$FORGORA` gives access to memory and features inside the app, nothing more, and can lose all of its value. Nothing here is investment advice. Forgetting is permanent by design: download what you want to keep.
