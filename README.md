# Sports Legends Simulator

A 3D Roblox-style simulator game that runs in the browser, built for Chromebooks. The whole game is one file, `index.html`, using [Three.js](https://threejs.org/) for the 3D. Sound effects are synthesized in the browser, so there are no audio files.

## How to play

| Key | Action |
| --- | --- |
| WASD or arrow keys | Move |
| Space | Jump |
| Click | Hit with your gear |
| Drag | Look around |
| Scroll | Zoom |
| Esc | Pause menu |

1. Hit piles of balls to fill your bag. **Auto** hits for you.
2. Stand on a green **CASH** pad to sell your bag for dollars.
3. Buy better gear (more balls per hit) and bigger bags at the **GEAR SHOP**. Your gear level carries across worlds, and each world turns it into that sport's gear.
4. Hatch pets at the **EGGS** pad. Each world has its own egg with 5 pets, from Common to Legendary. Your best 4 pets follow you and boost your cash.
5. Unlock zones at the gates. Each zone's balls are worth 3x more.
6. At the end of each world, a portal unlocks the next one. Later worlds also need rebirths.
7. **Rebirth** to reset your cash, gear and bag for a permanent cash boost. You keep your worlds, zones and pets.
8. Buy the Championship Trophy at the end of the Golf Course to become a Sports Legend.

Background music and sound effects are synthesized in the browser, and each has its own on/off switch in the pause menu.

The game opens on a title screen that plays a short trailer, filmed live in the game engine. Press **Play** or Enter to start. You can watch it again from the pause menu.

## Multiplayer

On the GitHub Pages link, everyone playing in the same world sees each other run around, hit, and show off their pets, with name tags overhead. Press **Players** to see who's in your world, change your name, or ask someone to trade pets. In a trade, both players pick pets to swap and press **Ready**. If either offer changes, both have to press Ready again.

Multiplayer runs on a free [Firebase](https://firebase.google.com) Realtime Database with anonymous sign-in:

- `FIREBASE_CONFIG` in `index.html` points at the project.
- `database.rules.json` holds the security rules. Paste it into the Firebase console under **Realtime Database → Rules**. Players can only write their own position, their own invites and their own side of a trade.

Where the Firebase library can't load (such as the claude.ai artifact), the game plays the same without other players, and the Players button says Offline.

## Saving

Progress saves automatically every few seconds and right after every purchase. When the game is opened as a claude.ai artifact, it saves to a private document tied to your Claude account, so it survives cleared browser data and follows you to other computers. Any other copy (GitHub Pages, a downloaded file) saves in the browser. The pause menu shows where your progress is saved and when it last saved, and has a Reset progress button.

## Worlds

| World | Gear | Zones | Needs |
| --- | --- | --- | --- |
| Soccer Stadium | Cleats (kick) | Training Pitch, Penalty Box, Golden Goal | |
| Basketball Arena | Wristbands (slam dunk) | Practice Court, Three-Point Line, Slam Dunk Zone | 1 rebirth |
| Football Field | Shoulder pads (tackle) | Practice Field, Midfield, Hail Mary Zone | 3 rebirths |
| Baseball Park | Bat (swing) | Bullpen, Infield, Home Run Derby | 5 rebirths |
| Hockey Rink | Hockey stick (slapshot) | Warm-Up Ice, Blue Line, Power Play | 7 rebirths |
| Tennis Court | Racket (forehand) | Baseline, Service Box, Match Point | 9 rebirths |
| Volleyball Beach | Kneepads (spike) | Shoreline, Sand Court, Sunset Spike | 11 rebirths |
| Bowling Alley | Bowling ball (bowl) | Gutter Lane, Spare Lane, Strike Zone | 13 rebirths |
| Cricket Ground | Cricket bat (drive) | Nets, Outfield, Boundary Line | 15 rebirths |
| Golf Course | Golf club (swing) | Driving Range, Fairway, Championship Green | 17 rebirths |

Zone and rebirth prices were worked out backward from target times with a simulated player. The first zone opens after about 2 minutes, the first world takes about 11, and a full run takes about 5 hours.

## Run it

Open `index.html` in Chrome. To share it, turn on GitHub Pages for this repository (Settings → Pages → deploy from the branch) and open the link it gives you.
