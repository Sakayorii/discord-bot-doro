-# what even is this project😭

# Doro Discord Bot 🌸 V4.3 (Node.js Edition)

An adorable multi-purpose Discord bot with music, economy, casino games, marriage system, AI chat, and word chain features! Now powered by Node.js with multilingual support!

> 🇻🇳 **[Tiếng Việt](README_VI.md)** | 🇺🇸 **English** (current)

**Version:** V4.3 | **Language:** English | **Status:** ✅ Active

## ✨ Key Features

### 🎵 Music System
- Stream music from SoundCloud (more stable than YouTube!)
- Queue management with skip, pause, resume
- Auto-leave after inactivity
- Now playing display

### 🎨 Profile System
- User profile cards with stats
- Level progression display
- Economy information
- Avatar support

### 💰 Economy System  
- Daily rewards (1200-1800 coins base)
- Streak bonus system (0.25% per day)
- Level progression with XP
- Bank deposit/withdraw
- Money transfer between users

### 🎰 Casino Games
- **Coinflip** - Classic heads or tails betting
- **Slots** - 3-reel slot machine with jackpots
- **Roulette** - Red/black/number betting
- **Blackjack** - Full blackjack experience with hit/stand

### 🏪 Shop System
- Various items to purchase:
  - 💍 Wedding rings (for marriage system)
  - 📦 Loot boxes with random rewards
  - 🍀 Lucky items for casino bonuses
  - 🎀 Cosmetic items and collectibles
- Inventory starts with 100 bag slots & 3 pet slots — buy upgrade items to expand
- Inventory management
- Item equipping and usage

### 💍 Marriage System & Shop
- **Shop Rings** - Buy rings that boost daily rewards:
  - 💍 Love Ring (+5% daily) - 50,000 coins
  - 💕 Couple Ring (+10% daily) - 120,000 coins
  - 🦆 Mandarin Ring (+15% daily) - 250,000 coins
  - 💎 Eternal Ring (+25% daily) - 500,000 coins
  - ✨ Destiny Ring (+50% daily) - 1,000,000 coins
- Propose to other users (requires ring)
- Accept/reject proposals
- Marriage status display
- Divorce option available

### 🤖 AI Chat
- Mention @Doro for cute AI conversations
- NVIDIA-powered responses
- Personality adapts based on user
- Remembers conversation context

### 🎮 Fun Commands
- Text transformations (OwO, UwU, mock text)
- Random dice rolls
- User profiles with beautiful cards
- AFK system with auto-reply

### 🌍 Multilingual Support
- English and Vietnamese languages
- Server-specific language settings
- Use `/language` slash command to switch

### ⚡ Performance Optimized
- Ultra-low latency (< 30ms response time)
- Smart caching for instant lookups
- Optimized message handling
- Automatic memory management

## 🆕 What's New in V4.3

- 🧠 **Realistic AI Prompts** – Completely refreshed English & Vietnamese instructions so Doro replies like a real person (owner mode vs. helper mode) while still following formatting rules.
- 🗣️ **Powerful `!say`** – Owner-only broadcast now supports replying to any message with `!say -r <messageId> text`, keeping announcement threads tidy.
- ♾️ **`!infinity` Control** – Owners can toggle truly infinite stats/slots for any user, while everyday commands such as `!ping` are restricted to moderators for extra safety.
- 🎒 **Bag & Pet Slots** – Every user starts with 100 bag slots / 3 pet slots, can buy upgrades in the new `upgrade` category, and purchases respect the capacity limits.

## Previous Updates (V4.2)

- 🎵 **Full Music System** - Complete YouTube playback with queue, skip, pause, resume
- ⚡ **Latency Fixed** - Restored optimal settings, back to 20-50ms API latency
- 🎧 **Voice Support** - @discordjs/voice integration with play-dl for streaming
- 📊 **Queue Management** - View queue, now playing, auto-play next song
- 🔧 **Balanced Optimization** - Perfect balance between performance and functionality

### Previous Updates (V4.1)
- 🌍 Language-Aware AI - AI speaks Vietnamese or English based on guild settings
- 💬 Natural AI Responses - Fixed emoji spacing ("hey=)" not "hey ="))
- 🌐 Full Language Support - All commands respect guild language settings

### Previous Updates (V4.0)
- 🐛 Critical Bug Fix - Fixed bot startup issue (event listener)
- 💍 Ring Effects Working - Shop rings now properly boost daily rewards
- 📊 Leaderboard System - Track top users by balance/level/streak/wins
- 🎴 Blackjack Game - Full casino blackjack with 1.5x natural 21
- 💰 Economy Rebalanced - Daily rewards adjusted to 1200-1800 coins

### Previous Updates (V3.9)
- ✅ Multilingual System - Full English & Vietnamese support
- ✅ Slash Commands - `/language` and `/ping` commands
- ✅ Ultra-Low Latency - Optimized for < 30ms response
- ✅ Smart Help System - Auto-translates based on server language
- ✅ Improved AI - 15+ varied responses for owner interactions

## 🚀 Quick Setup

### Prerequisites
- Node.js 22.12.0 or higher
- Discord Bot Token
- API Keys (optional):
  - NVIDIA API key (for AI chat)

### Installation

1. Clone or download the bot files

2. Install dependencies:
```bash
npm install
```

3. Create `.env` file with your tokens:
```env
DISCORD_BOT_TOKEN=your_bot_token_here
NVIDIA_API_KEY=your_nvidia_key_here
BOT_OWNER_IDS=your_discord_id_here
```

4. Run the bot:
```bash
npm start
```

Or for development with auto-restart:
```bash
npm run dev
```

## ⚙️ GitHub Actions Runner

1. Add the secrets `DISCORD_BOT_TOKEN`, `NVIDIA_API_KEY`, `BOT_OWNER_IDS`, `REPO_TOKEN` (classic PAT with repo/workflow scope), and (optionally) `DISCORD_WEBHOOK_URL` under **Settings → Secrets and variables → Actions**.
2. Every push to `main` runs the `lint` job from `.github/workflows/bot.yml`, which uses Node 22.12.0 and executes `npm run lint` to ensure all JavaScript files parse cleanly.
3. To host the bot directly from GitHub Actions, trigger the `doro-bot` workflow manually (`workflow_dispatch`). The `run-bot` job installs production dependencies under Node 22.12.0 and starts `node index.js` with your secrets for text/economy features (Discord voice still requires a local/VPS host).
4. During `run-bot`, the workflow automatically restarts the bot after crashes, keeps it online for ~6 hours (stopping 20 seconds early), commits JSON data changes, and—once past 5.5 hours with a successful commit—dispatches the next workflow run so sessions chain continuously.

## 📝 Command List

### Music Commands
- `!play [song]` - Play or queue a song
- `!skip` - Skip current song
- `!queue` - View queue
- `!pause/resume` - Pause/resume playback
- `!stop` - Stop and clear queue
- `!np` - Now playing

### Economy Commands
- `!balance [@user]` - Check balance
- `!daily` - Claim daily reward (with ring bonuses!)
- `!deposit [amount]` - Deposit to bank
- `!withdraw [amount]` - Withdraw from bank
- `!give @user [amount]` - Transfer money (10% fee)
- `!leaderboard [type]` - View top 10 users (balance/level/streak/wins)

### Casino Commands
- `!cf <h/t> <bet>` - Coinflip - Heads or tails
- `!slots <bet>` - Slot machine with jackpots
- `!bj <bet>` - Play blackjack (1.5x on natural 21)

### Shop Commands
- `!shop [page/category]` - Browse shop
- `!buy [item]` - Purchase item
- `!inventory [@user]` - View inventory
- `!use [item]` - Use an item
- `!equip [item]` - Equip an item
- `bag_slot_20` / `pet_slot_1` - New upgrade items that permanently add slots

### Marriage Commands
- `!marry @user` - Propose (needs ring)
- `!accept` - Accept proposal
- `!reject` - Reject proposal
- `!divorce` - End marriage
- `!marriage [@user]` - View marriage info

### Utility Commands
- `!help` - View all commands
- `!ping` - Check bot latency (Mods/Admins/Owners)
- `!avatar [@user]` - Get user avatar
- `!afk [reason]` - Set AFK status
- `!say [-r id] <message>` - Owner broadcast or reply to an existing message
- `!infinity <@user> [on/off]` - Owner toggles infinite stats/slots for a user
- `!setprefix <prefix>` - Change server prefix (Admin only)

### 🤖 AI Chat
- **@Doro [message]** - Chat with Doro AI
- `!reset` - Clear AI chat history

### 🌍 Slash Commands
- `/language` - Change bot language for this server (Admin only)
- `/ping` - Check bot latency and response time

## ⚙️ Configuration

### Setting Bot Owners
Add Discord IDs in `.env`:
```env
BOT_OWNER_IDS=id1,id2,id3
```

### Customizing Economy
Edit values in `systems/economySystem.js`:
- Starting balance
- Daily reward amounts  
- Level XP requirements
- Casino win rates

### Adjusting Shop Prices
Modify prices in `systems/shopSystem.js`:
- Ring prices
- Loot box costs
- Item effects

### AI Personality
Customize Doro's personality in `systems/aiSystem.js`:
- Response style
- Emoji usage
- Owner vs regular user behavior

### Honkai Presence Asset
To display the Honkai: Star Rail image inside Discord’s activity card, upload the image to **Discord Developer Portal → Your Application → Rich Presence → Art Assets** and copy the asset key (for example `honkai_logo`). Then set it in `.env`:
```env
HONKAI_ASSET_KEY=honkai_logo
```
If you skip this step the bot still runs, but Discord can’t show the artwork.

## 🎨 Features Highlights

### Beautiful Profile Cards
- Custom designed cards with user stats
- Level and XP progress bars
- Marriage status display
- Economy statistics
- Badges and achievements

### Smart AI Responses  
- Context-aware conversations
- Personality that adapts to users
- Cute and playful responses
- Emoji reactions

### Streak System
- Daily login streaks
- Increasing rewards for consistency
- Bonus multipliers
- Level-based bonuses

## 🐛 Troubleshooting

### Bot not responding
- Check bot has required intents enabled
- Verify prefix is `+` 
- Ensure bot has permissions in channel

### Music not playing
- Verify ffmpeg is installed
- Check voice channel permissions
- Ensure YouTube links are valid
- **⚠️ GitHub Actions cannot use voice!** Music only works when bot runs locally

### AI not working
- Confirm API keys in `.env`
- Check API rate limits
- Verify internet connection

### Economy issues
- Data saves in JSON files
- Check file permissions
- Backup data regularly

## 📚 Data Storage

All data is stored locally in JSON files:
- `economy_data.json` - User balances and stats
- `shop_data.json` - Shop inventory
- `user_inventory.json` - User items
- `marriage_data.json` - Marriage records
- `afk_data.json` - AFK statuses
- `disabled_commands.json` - Disabled commands

## 🎯 Tips & Tricks

1. **Daily Streaks** - Don't break your streak for maximum rewards!
2. **Shop Strategy** - Buy rings before proposing
3. **Casino Tips** - Start with small bets
4. **Level Up** - Gain XP from daily claims and activities
5. **Profile Cards** - Customize your card with achievements

## 🌟 Special Features

- **Infinity Mode** - Owners get unlimited resources
- **Command Disabling** - Disable specific commands per server
- **Auto AFK** - Automatically set AFK when mentioned
- **Smart Help** - Category-based help system
- **Fast Response** - Optimized for quick reactions

---

> **Note:** I've already modified this bot so you can easily customize it into any bot you want. If you don't know how to do it, just give it to AI. If that fails... too bad! 😝

## 📄 License

Free to use, modify, and distribute. No attribution required.

## 🤝 Credits

- Powered by Discord.py
- AI by NVIDIA 
- Made with 💖 by Doro

---
*Doro Bot - Your Cute Discord Companion!*
