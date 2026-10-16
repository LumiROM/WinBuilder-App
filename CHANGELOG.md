# Changelog

Every release of LumiROM Builder, newest first. The same notes are on each
[release](../../releases) page: this file is written by CI when the source repository is tagged.

Earlier versions, from before this repository existed, are not reproduced here.

<!-- releases -->

## 1.2.0

**The app now tells you when the build scripts have moved on.** If the repository has commits your
checkout has never seen, Home says so and offers **Update now**, which fetches them and pulls - in the
console, where you can watch it happen. There is also a **Check for new commits** button for whenever
you would rather not wait for the next check.

The update can only fast-forward. If you have written something locally, or the branches have
diverged, it stops and says so rather than merging or overwriting anything of yours. The check itself
downloads nothing: it asks the remote for one commit id and stops there, so asking whether there is
something to fetch does not fetch it.

**About** moved into the navigation, with the version, the exact build, and a link to the support
channel. Diagnostics moved to the bottom of Settings, where the tools live.

Also fixed: released builds sent a stray carriage return to every command they ran. It only showed in
binaries built by CI, never in local builds, which is exactly why it went unnoticed for so long.
