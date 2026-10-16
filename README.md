# Underblock

A neon-grime co-op dungeon crawler. One static page; multiplayer is peer-to-peer
(PeerJS), so there is no server to run.

## Put it on Vercel (no coding)

1. Make a free GitHub account at github.com if you don't have one.
2. On GitHub, click **New repository**, name it `underblock`, keep it Public, click **Create repository**.
3. On the empty repo page, click **uploading an existing file**, drag in `index.html`, `vercel.json` and this `README.md`, then click **Commit changes**.
4. Go to vercel.com, sign up with your GitHub account (the free Hobby plan is fine).
5. Click **Add New → Project**, pick the `underblock` repo, click **Import**.
6. Leave every setting as it is (Framework Preset: Other) and click **Deploy**.
7. In about a minute you get a link like `https://underblock-yourname.vercel.app`. Send that to your friends.

To update the game later: upload the new `index.html` to the GitHub repo
(Add file → Upload files). Vercel redeploys on its own.

Or, if you have Node installed: open a terminal in this folder and run `npx vercel`.

## Playing together

1. Everyone opens the Vercel link.
2. One person goes to **Multiplayer → Host** and reads out the 5-character room code.
3. Everyone else goes to **Multiplayer → Join**, types the code, and joins.
4. Everyone picks a runner and enters the Block. The host starts runs from the shaft
   and rides the lifts; everyone else comes along.
5. Up to 4 players. Enemies get tougher for each extra player.
6. If you drop out or end up in town while your squad is still down there, walk to the
   shaft and pick **Rejoin the run**.

Your runner, gear and money are saved in your own browser.

## If someone can't connect (the relay)

Connections go straight between players' browsers. Most home internet works, but
some routers, phone hotspots and work/school networks block that, which is usually
why a 3rd or 4th player can't get in. A relay fixes it:

1. Make a free account at metered.ca (the Open Relay / TURN server, free plan).
2. In its dashboard, copy your **app name** (the part before `.metered.live`) and your **API key**.
3. Open `index.html` in GitHub (click it, then the pencil icon to edit). Near the top find:
   `window.UB_CONFIG={meteredApp:'',meteredKey:'',maxPlayers:4};`
4. Paste them between the quotes, e.g. `meteredApp:'underblock',meteredKey:'abc123...'`
5. Click **Commit changes**. Vercel redeploys in about a minute. The Multiplayer
   screen then shows **RELAY ON**.
