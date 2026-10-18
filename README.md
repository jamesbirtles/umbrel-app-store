# Umbrel apps

## Frigate

[Official Frigate package](https://github.com/getumbrel/umbrel-apps/tree/d8d48803f14cd8c536d1abc4b590670101345fa5/frigate)

Frigate starts with no cameras configured; add them through **Settings → Global configuration → Camera management**. Existing installs retain their own config, including any old sample camera; remove that camera in Frigate if it is still present.

The container has 2 GiB of shared memory, sized for approximately ten 1080p detection streams using [Frigate's calculator](https://docs.frigate.video/frigate/installation/#calculating-required-shm-size). This is a limit, not memory allocated up front. Recalculate and edit `shm_size` in `jamesbirtles-frigate/docker-compose.yml` if your camera count or detection resolution differs; Umbrel does not expose Docker shared-memory size as an app setting.

Media defaults to the app's `data/storage` directory. On umbrelOS 2.0, select a writable host folder, external drive, or network share in **Frigate → Settings → Media Storage**. This changes the `/media/frigate` bind mount, not `/config`. Stop Frigate and move existing media to the selected folder before switching; keep the destination drive mounted while Frigate runs. On older umbrelOS versions, media remains in the app data directory.
