# Taxi Jame3i Dash — Ultra Arcade

The active web experience is now an endless arcade runner inspired by the simple driving / flying / combo loop requested by the user. The former simulator modules remain in source; the deployed entry point is `src/main.jsx` and `ArcadeScene.jsx`.

## Run

`npm ci`, `npm run dev`, `npm test`, `npm run build`.

## Controls

- Left/right or A/D: switch lanes; in the air, barrel roll.
- Space / Up / W: jump; hold to fly; press again in the air to front flip.
- Down / S: slam down.
- Shift: air-powered boost.
- Q: Ultra when the meter reaches 100%.
- Z: use a collected rocket or magnet.
- P / Escape: pause. M: mute.
- Mobile: swipe left/right/down; tap and hold to jump/fly; dedicated direction, boost, fly, item and Ultra controls.

Air replenishes on the ground when not boosting, from blue cells and from landed tricks. Near misses, coins and trick combinations charge Ultra. Ultra provides seven seconds of higher speed and invincibility. A star grants eight seconds of invincibility. One unprotected collision ends the run.

## Visuals and sound

Warm sunrise sky, low sun, warm directional lighting and coastal haze. The rear window reads `ECH5ER YA TALYENA`.

Original Tunisian louage model with rounded bodywork, red/blue/gold liveries, destination signs, Tunisian plates and ten thrusters. Three.js/R3F render the road, Tunisian-inspired architecture, traffic, animated pickups, physical vehicle motion, flip/roll animations, jets and neon speed streaks. Ultra shifts sky/light color, increases field of view, strengthens neon trails and activates bloom through Three.js postprocessing. ULTRA/HIGH/LOW FX controls graphics quality independently of the in-game Ultra power.

Web Audio mixes synthesized engine, turbine, wind and transient effects with three uploaded MP3s. The first MP3 plays on launch and boost activation, the second on game over, and the third loops during a run. Music pauses/resumes with the game and rewinds on a new run. All effects lower the music bus with fast attack and smooth recovery; boost/fly/Ultra maintain ducking while active. Mute controls a shared master gain. Audio starts after a user gesture. The three user-uploaded MP3s are used for launch/boost, game over, and looping background music. No reference-site code is reused.

Records, coins, livery, graphics quality and mute settings are saved on this device under `taxi-jame3i-dash-v4`. The ranking is explicitly local. No simulated global leaderboard.

## Tests and limitations

`tests/arcade.test.mjs` covers automatic acceleration, resource-consuming boost, steering, jumping/flying/tricks/slam, combos, Ultra gating and duration, invincibility, pickups, near misses, pause, collisions, persistence and restart. Existing simulator and actual Rapier collision tests are retained.

The production build and automated tests pass. Managed browser preview is unavailable in this environment; visual layout, audible output, touch hit targets and GPU performance have not been verified in a live browser. The reference site was previously inspected for its controls; a fresh revisit was unavailable during this update.
