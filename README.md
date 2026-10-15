# Sports Legends Simulator

A 3D Roblox-style simulator game that runs in the browser, built for Chromebooks. The whole game is one file, `index.html`, using [Three.js](https://threejs.org/) for the 3D. Sound effects are synthesized in the browser, so there are no audio files.

## How to play

| Key | Action |
| --- | --- |
| WASD or arrow keys | Move |
| Space | Jump |
| Click | Hit with your gear, or click a pile to send your pets at it |
| Drag | Look around |
| Scroll | Zoom |
| Enter or / | Chat (online) |
| Esc | Pause menu |

1. Break piles of balls. Every pile has fixed health shown in a bar over it, and pays cash the moment it breaks; the coins fly straight to you. **Auto** hits for you.
2. Hatch pets at the **EGGS** pad. Pets have **Power** and attack the pile you're hitting (or the one you click). Each world has its own egg with 5 pets, from Common to Legendary.
3. At the **GEAR SHOP**, buy **Gear** (more damage per hit) and **Pet Training** (more Power for every pet). Both are bought separately in each world.
4. Unlock zones at the gates. Each zone's piles are tougher but pay more.
5. At the end of each world, **rebirth** through the portal into the next sport. Every rebirth gives x2 cash for good and one more pet slot (3 to start, up to 8). You start the new world with $0 and fresh gear and training, and keep all your pets.
6. Manage pets in **Pets**: sort them by Power, rarity or world, and delete the ones you don't want.
7. Buy the Championship Trophy at the end of the Golf Course to become a Sports Legend.

Background music and sound effects are synthesized in the browser, and each has its own on/off switch in the pause menu.

The game opens on a title screen that plays a short trailer, filmed live in the game engine. Pick a name (or roll a random one with 🎲), then press **Play** or Enter to start. You can watch it again from the pause menu.

## Multiplayer

On the GitHub Pages link, everyone online sees each other run around, hit, and show off their pets, with name tags overhead, whatever world each of them is in. Each player wears their own world's kit and gear. Press Enter to chat with everyone online: messages show in the corner and as a speech bubble over your head. The pause menu can turn chat off. Press **Players** to see who's online and which world they're in, change your name, or ask someone to trade pets. In a trade, both players pick pets to swap and press **Ready**. If either offer changes, both have to press Ready again. A **Coin Flip** works the same way, except each player bets pets and the winner takes them all; each game commits to a secret before either reveals it, so neither side can rig the coin. The flip looks like RBXFlip's: both players sit on either side with their bets, a ring counts down from 3, then a poker chip (Heads for the player who asked, Tails for the other) flips end over end and lands on the winner's side. Both players see the same flip.

Multiplayer runs on a free [Firebase](https://firebase.google.com) Realtime Database with anonymous sign-in:

- `FIREBASE_CONFIG` in `index.html` points at the project.
- `database.rules.json` holds the security rules. Paste it into the Firebase console under **Realtime Database → Rules**. Players can only write their own position, their own invites and their own side of a trade. Chat messages are capped at 100 characters, one every 1.5 seconds per player, and can't be edited or deleted by players.

Where the Firebase library can't load (such as the claude.ai artifact), the game plays the same without other players, and the Players button says Offline.

## Saving

Progress saves automatically every few seconds and right after every purchase. When the game is opened as a claude.ai artifact, it saves to a private document tied to your Claude account, so it survives cleared browser data and follows you to other computers. Any other copy (GitHub Pages, a downloaded file) saves in the browser. The pause menu shows where your progress is saved and when it last saved, and has a Reset progress button.

## Worlds

| World | Gear | Zones |
| --- | --- | --- |
| Soccer Stadium | Cleats (kick) | Training Pitch, Penalty Box, Golden Goal |
| Basketball Arena | Wristbands (slam dunk) | Practice Court, Three-Point Line, Slam Dunk Zone |
| Football Field | Shoulder pads (tackle) | Practice Field, Midfield, Hail Mary Zone |
| Baseball Park | Bat (swing) | Bullpen, Infield, Home Run Derby |
| Hockey Rink | Hockey stick (slapshot) | Warm-Up Ice, Blue Line, Power Play |
| Tennis Court | Racket (forehand) | Baseline, Service Box, Match Point |
| Volleyball Beach | Kneepads (spike) | Shoreline, Sand Court, Sunset Spike |
| Bowling Alley | Bowling ball (bowl) | Gutter Lane, Spare Lane, Strike Zone |
| Cricket Ground | Cricket bat (drive) | Nets, Outfield, Boundary Line |
| Golf Course | Golf club (swing) | Driving Range, Fairway, Championship Green |

Unlock prices were worked out backward from target times with a simulated player. The first zone opens after about a minute and the first world takes about 5. A new world starts tough (piles take a few seconds each with your old pets) and gets easy as you upgrade. The longest wait for anything new is about 4 minutes, and a full run takes about 3.5 hours.

## Run it

Open `index.html` in Chrome. To share it, turn on GitHub Pages for this repository (Settings → Pages → deploy from the branch) and open the link it gives you.
