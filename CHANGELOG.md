# Changelog

Every release of LumiROM Builder, newest first. The same notes are on each
[release](../../releases) page: this file is written by CI when the source repository is tagged.

Earlier versions, from before this repository existed, are not reproduced here.

<!-- releases -->

## 1.3.1

**The app now looks for a new version when it starts, and says so with a notification.** Once per
version, deliberately: if it came back on every launch until you updated, the notification would stop
being read. The Updates section on About is still there with its button, for checking whenever you
feel like it.

**The licence is no longer MIT.** It should not have been. This app is free to use for building ROMs
for your own devices, and it is not free to redistribute, to ship alongside your own builds, or to
re-upload somewhere else. The wording is in `LICENSE`, and About says the same thing.

If you are already on 1.3.0, this is the first release the app will offer you by itself.

## 1.3.0

**The app now updates itself.** About has an **Updates** section that knows when a newer build has
been published, and offers to install it. It runs the installer with its own wizard, so every step is
visible, and the app closes first and comes back when the installation finishes.

**Nothing is installed without being checked first.** The published manifest says how large the
download should be and what its hash is, and a download that does not match is deleted rather than
run. A portable copy is never handed an installer: it is told where to get the ZIP and to unzip it
over its own folder, which is what someone who chose the ZIP wants.

**An About page**, with the version, the exact build this is, and a link to the support channel.
Diagnostics moved to the bottom of Settings, where the tools live.

**Downloads now live in their own repository**, so the links in this release are not the ones you may
have seen before. The installer and the portable ZIP are published there, and the app knows where to
look for the next one.

There is a **Telegram** button on About, which is the fastest way to report something broken. When
something is wrong, Settings -> Run diagnostics writes a report of everything the app can see: copy it
into the message and it saves a round of guessing.

## 1.2.0

**The app now tells you when the build scripts have moved on.** If the repository has commits your
checkout has never seen, Home says so and offers **Update now**, which fetches them and pulls, in the
console, where you can watch it happen. There is also a **Check for new commits** button for whenever
you would rather not wait for the next check.

The update can only fast-forward. If you have written something locally, or the branches have
diverged, it stops and says so rather than merging or overwriting anything of yours.

**The check costs nothing to run.** It asks the remote for a single commit id and stops there,
without downloading anything. That matters here: this repository is hundreds of megabytes, and
fetching just to find out whether there is something to fetch would be a silly price for a question
asked on every launch.

**Quieter when there is nothing to say.** The banner only opens when there is actually something to
pull. A banner that is always there announcing that everything is fine is a banner nobody reads.

**An About page**, with the version, the exact build and a link to the support channel. Diagnostics
moved to the bottom of Settings, where the tools live.

**Fixed: released builds sent a stray carriage return to every command they ran.** It only ever
showed up in binaries built by CI and never in local ones, which is exactly why it went unnoticed for
so long. If you downloaded an earlier release and a build failed in a strange way, this was probably
why.
