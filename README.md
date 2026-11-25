# Badge OS signed app channel

Signed SpaceInv 1.0.2, Asteroids, Video, Codex Board, Hackaday, Messages and Doom 1.0.1 packages for the managed App Manager firmware. See [NOTICES](NOTICES.md) and the corresponding source references for attribution and licenses.

Use the [fork trial source c12985fd](https://github.com/evrenucar/supercon26-badge-os/tree/c12985fd729754f7792b0dea1bef5e65d4bb28fe), available on `codex/app-channel-ready`. It contains PR #6, PR #8 and the public-channel include fix; the reviewed PR #8 head is unchanged. This branch holds channel assets. Run the following from that firmware checkout with ESP-IDF 6.0.2 active:

```sh
channel_dir="$PWD/build/fork-channel"
base_url="https://raw.githubusercontent.com/evrenucar/supercon26-badge-os/app-channel"
mkdir -p "$channel_dir"
curl --fail --location "$base_url/public-key.pem" --output "$channel_dir/public-key.pem"
printf '%s  %s\n' '6628816d577d2d3c992a9d95d87c1102e6de0b2e7e491d0089a6f881e02e1c97' "$channel_dir/public-key.pem" | shasum -a 256 -c -
python3 apps/app_manager/tools/configure_channel.py \
  --base-url "$base_url" --public-key "$channel_dir/public-key.pem" \
  --output "$channel_dir/app-channel.h"
idf.py -B build/fork-managed -DSDKCONFIG="$PWD/build/fork-managed/sdkconfig" \
  -DBADGE_APP_MANAGER=ON -DBADGE_APP_MANAGER_CHANNEL="$channel_dir/app-channel.h" build
```

The public-key checksum above pins the same APP verification key as the previously installed packages. `app-channel.h` in this branch is the ready-generated equivalent. It contains public configuration only. Omitting the CMake channel input leaves upstream's default trust unchanged.

Existing managed badges must keep their partition table, installed store and matching APP key. This build command does not flash anything. Never flash an empty appstore image over an existing store. Stock partition layouts need separately reviewed first provisioning; app-only OTA cannot create an app store.

Video's signed clip is included under `video/assets/`. Doom's matching IWAD is a separate prerequisite. This channel updates apps; it does not change the OS Online update route.

Doom1.0.1 removes build-machine names from diagnostic filename strings. Its exact corresponding source is https://github.com/evrenucar/supercon26-badge-os/tree/09fac423d2943334a09a2731310f530d284d0a3f/apps/app_manager/modules/doom . ExistingDoom1.0.0 receipts continue to verify with the unchanged key; the public channel offers the newer1.0.1.
