# TTC Departures: VM test

Desktop verification for the [TTC Departures](https://github.com/MehrshadFb/omarchy-ttc-departures) Omarchy plugin, kept in its own repository so the plugin itself contains nothing but the plugin.

The `vm-test` workflow runs on a free GitHub runner with KVM. It fetches the official [omarchy-iso](https://github.com/omacom/omarchy-iso) harness at a pinned commit, installs Omarchy from the released ISO into a QEMU guest by driving the real installer, boots the desktop, installs the plugin from GitHub inside it, and walks it through the bar label, the panel board, the stop picker, the trip planner, error states, a route filter, and a vertical bar, taking a screenshot of each. Screenshots and logs are uploaded as an artifact.

Trigger it from the Actions tab. It takes about an hour.

- `ci/run-vm-test.sh` runs inside an Arch container on the runner and drives the harness.
- `ci/guest/test/acceptance` runs inside the installed Omarchy desktop over SSH.

MIT, like the plugin.
