# Sports Legends Simulator

A 3D Roblox-style simulator game that runs in the browser, built for Chromebooks. The whole game is one file, `index.html`, using [Three.js](https://threejs.org/) for the 3D. Sound effects are synthesized in the browser, so there are no audio files.

## How to play

| Key | Action |
| --- | --- |
| WASD or arrow keys | Move |
| Space | Jump |
| Click | Swing your gear |
| Drag | Look around |
| Scroll | Zoom |
| Esc | Pause menu |

1. Swing at piles of balls to fill your bag. **Auto Swing** swings for you.
2. Stand on a green **CASH** pad to sell your bag for dollars.
3. Buy better gear (more balls per hit) and bigger bags at the **GEAR SHOP**.
4. Hatch pets at the **EGGS** pad. Each world has its own egg with 5 pets, from Common to Legendary. Your best 4 pets follow you and boost your cash.
5. Unlock zones at the gates. Each zone's balls are worth 3x more.
6. At the end of each world, a portal unlocks the next one. Later worlds also need rebirths.
7. **Rebirth** to reset your cash, gear and bag for a permanent cash boost. You keep your worlds, zones and pets.
8. Buy the Championship Trophy at the end of the Hockey Rink to become a Sports Legend.

## Saving

Progress saves automatically every few seconds and right after every purchase. When the game is opened as a claude.ai artifact, it saves to a private document tied to your Claude account, so it survives cleared browser data and follows you to other computers. Any other copy (GitHub Pages, a downloaded file) saves in the browser. The pause menu shows where your progress is saved and when it last saved, and has a Reset progress button.

## Worlds

| World | Zones | Needs |
| --- | --- | --- |
| Soccer Stadium | Training Pitch, Penalty Box, Golden Goal | |
| Basketball Arena | Practice Court, Three-Point Line, Slam Dunk Zone | 1 rebirth |
| Football Field | Practice Field, Midfield, Hail Mary Zone | 3 rebirths |
| Baseball Park | Bullpen, Infield, Home Run Derby | 6 rebirths |
| Hockey Rink | Warm-Up Ice, Blue Line, Championship Ice | 10 rebirths |

The economy is tuned so a full run takes roughly 3 to 4 hours.

## Run it

Open `index.html` in Chrome. To share it, turn on GitHub Pages for this repository (Settings → Pages → deploy from the branch) and open the link it gives you.
