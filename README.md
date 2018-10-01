# LL Freeplay Counter-Strike: Global Offensive Dedicated Server in Docker

## Linux Container

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
