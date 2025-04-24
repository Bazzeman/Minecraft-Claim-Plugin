# Minecraft-Claim-Plugin
In this repository I am going to develop my own plugin for Minecraft Java 1.20.2 servers. This plugin should give players the option to claim and so that it is protected against griefers. This plugin could be used for players to protect their important builds and farms, or for server administrators to protect land which should not be destroyed or griefed.

## Current state
The plugin is in th middle of development at the moment. A stable connection with the user their database can be established and data from the plugin can be read and saved. Also some commands are ready to be used by tge plugin, such as `/claim`, `/unclaim` and `/trust`. Furthermore a solid and well built system has been programmed, which should increase development speed for writing and modifying new commands. The next step is to set flags for claims which disallow players to interact with a claim.

## Links
- [Technical design document]([https://github.com/Bazzeman/Minecraft-Claim-Plugin/edit/main/README.md](https://github.com/Bazzeman/Minecraft-Claim-Plugin/blob/main/TechnicalDesignDocument.md)

## User stories
As a **building player**:
- I want to be able to claim my builds **so that** other players can't interact with anything in my base.
- I want to be able to claim multiple of my builds **so that** they are all protected against other players.
- I want to be able to change the settings of my claims **so that** I could allow certain player interactions.
- I want to be able to allow specific players to interact with my claim **so that** these players can interact with my builds.
- I want to be able to no longer allow specific players to interact with my claim **so that** these players can no longer interact with my build.
- I want to be able to remove my claim **so that** my claimed land can be used by other players without having to allow every player to interact with my claim.

As an **exploring player**:
- I want to be able to see which player is the owner of a claim **so that** I can ask this player to allow me to interact with their claim.
- I want to get notified when I enter a claim **so that** I am aware that I may not interact with this claim.
- I want to get notified when I interact with a claim where I am not allowed to **so that** I am aware why my interactions are being reverted.

As a **server administrator**:
- I want to be able to remove any claim **so that** I can remove claims of inactive or banned players.
- I want to be able to create a claim where the owner is the server **so that** other players are aware this claim does not belong to anyone.

As a **developer**:
- I only want to allow players to remove claims if they are the owner of the claim **so that** claims are properly protected.
- I only want to allow players with the right permissions to create server claims or to remove any claim **so that** claims are properly protected.
- I want users to use their own databse **so that** I don't have to wurry about which users are using my plugin.
- I want to give each player a limited amount of claims **so that** users their databases do not overflow.

As an **user**:
- I want to change settings in the `config.yml` file of the plugin **so that** I can apply server wide rules for claims.

## Technical Approach
- **Commands** which players can run to claim, unclaim, trust players and get information about a claim.
- **Action bar** which displays the the claim owner for a short period of time whenever the player is entering a claim.
- **Player chat messages** which notify players that they can not interact with the claim they try to interact with.
- **Permissions** which make sure only players with the right permissions are allowed to create server claims or remove any claim.
