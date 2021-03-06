![thumb-gamesvr-csgo-freeplay](https://raw.githubusercontent.com/LacledesLAN/gamesvr-csgo-freeplay/master/.misc/thumb-gamesvr-csgo-freeplay.png "thumb-gamesvr-csgo-freeplay")

This repository is maintained by [Laclede's LAN](https://lacledeslan.com). Its contents are heavily tailored and tweaked for use at our charity LAN-Parties. For third-parties we recommend using this repo only as a reference example and then building your own using [gamesvr-csgo](https://github.com/LacledesLAN/gamesvr-csgo) as the base image for your customized server.

## Linux Container

[![Build Status](https://dev.azure.com/LacledesLAN/Game%20Servers/_apis/build/status/gamesvr-csgo-freeplay)](https://dev.azure.com/LacledesLAN/Game%20Servers/_build/latest?definitionId=3)
[![](https://images.microbadger.com/badges/version/lacledeslan/gamesvr-csgo-freeplay.svg)](https://microbadger.com/images/lacledeslan/gamesvr-csgo-freeplay "Get your own version badge on microbadger.com")
[![](https://images.microbadger.com/badges/image/lacledeslan/gamesvr-csgo-freeplay.svg)](https://microbadger.com/images/lacledeslan/gamesvr-csgo-freeplay "Get your own image badge on microbadger.com")

### Download

```shell
docker pull lacledeslan/gamesvr-csgo-freeplay;
```

### Run Self-Tests

The image includes a test script that can be used to verify its contents. No changes or pull-requests will be accepted to this repository if any tests fail.

```shell
docker run --rm lacledeslan/gamesvr-csgo-freeplay ./ll-tests/gamesvr-csgo-freeplay.sh;
```

### Run Simple, Interactive Server

```shell
docker run --rm lacledeslan/gamesvr-csgo-freeplay  ./srcds_run -game csgo +game_type 1 +game_mode 0 -tickrate 128 +mapgroup ll_arms +map ar_baggage +sv_lan 1
```

## Game Mode Switch Snippets

Use to switch the game mode on an already running freeplay server.

### Arms Race

```shell
game_mode 0; game_type 1; mapgroup mg_armsrace; exec gamemode_armsrace; exec gamemode_armsrace_server; mapgroup mg_armsrace; map ar_shoots
```

### Classic Casual

```shell
game_mode 0; game_type 0; exec gamemode_casual; exec gamemode_casual_server; mapgroup ll_bomb; map de_cache
```

### Classic Competitive

```shell
game_mode 1; game_type 0; exec gamemode_competitive; exec gamemode_competitive_server; mapgroup ll_bomb; map de_dust2
```

### Deathmatch

```shell
game_mode 2; game_type 1; exec gamemode_deathmatch; exec gamemode_deathmatch_server; mapgroup mg_deathmatch; map de_bank
```

### Demolition

```shell
game_mode 1; game_type 1; exec gamemode_demolition; exec gamemode_demolition_server; mapgroup mg_demolition; map de_lake
```

## Getting Started with Game Servers in Docker

[Docker](https://docs.docker.com/) is an open-source project that bundles applications into lightweight, portable, self-sufficient containers. For a crash course on running Dockerized game servers check out [Using Docker for Game Servers](https://github.com/LacledesLAN/README.1ST/blob/master/GameServers/DockerAndGameServers.md). For tips, tricks, and recommended tools for working with Laclede's LAN Dockerized game server repos see the guide for [Working with our Game Server Repos](https://github.com/LacledesLAN/README.1ST/blob/master/GameServers/WorkingWithOurRepos.md). You can also browse all of our other Dockerized game servers: [Laclede's LAN Game Servers Directory](https://github.com/LacledesLAN/README.1ST/tree/master/GameServers).
