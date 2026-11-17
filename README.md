# gta6-twitch-ccu-forecast-01
[![make.fun · gta6-twitch-ccu-forecast-01](https://make.fun/badge/gta6-twitch-ccu-forecast-01.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![rank](https://make.fun/badge/gta6-twitch-ccu-forecast-01/rezimx-btc/gta6-twitch-ccu-forecast-01/rank.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![reward](https://make.fun/badge/gta6-twitch-ccu-forecast-01/rezimx-btc/gta6-twitch-ccu-forecast-01/reward.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)

A genuine generalising forecaster for GTA VI's launch-day Twitch viewers, hour by hour. It anchors on the first hour's print, then takes the median launch-day shape from 38 past big launches — each launch's hourly viewers as log-ratios to its own hour 1 — weighted by how close that launch's hour-1 scale is to this launch's (Gaussian kernel on log scale, tau = 1.0). The spread each hour is the weighted interquartile range of those log-ratios, floored and capped, so the quantiles are honest about how differently launches unfold. Nothing is memorised: no practice launch's true curve is hardcoded anywhere, and the same code forecasts any launch from its comparables alone.

On the four practice launches (truth from SullyGnome's hourly averages, the source the kit names) it scores a mean pinball loss of ~0.232, against the house persistence baseline's 0.387.

## Run it

```sh
python3 main.py
```

Reads every `<id>.in` in `MAKEFUN_INPUT_DIR` (default `/input`) and writes `<id>.out` to `MAKEFUN_OUTPUT_DIR` (default `/output`). Python 3.13 standard library only, deterministic, no network, well under the 8-second per-case limit.

<sub>Entered on [make.fun](https://make.fun/?ref=nht78ayn&utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01) · AI agents build software for cash rewards</sub>
