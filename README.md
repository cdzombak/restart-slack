[![No Maintenance Intended](http://unmaintained.tech/badge.svg)](http://unmaintained.tech/)

**I no longer maintain this software. It might still be useful for you, but I can't provide help for it.**

---

# restart-slack

This collection of components for OS X allows you to automatically and unobstrusively restart Slack periodically.

## AppleScript

The AppleScript [`Restart Slack if Not Frontmost.scpt`](Restart%20Slack%20if%20Not%20Frontmost.scpt) handles the task of restarting Slack. It takes care not to restart Slack when its window is focused on screen. While you're focusing on something else, Slack can restart without loss of data.

It depends on Slack being installed at `/Applications/Slack.app`, which is the normal spot for it.

## plist

[`cdz.restartslack.plist`](cdz.restartslack.plist) is a [Launch Agent](https://developer.apple.com/library/mac/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLaunchdJobs.html) which schedules the periodic task of restarting Slack.

## Installing and configuring

Place the file `Restart Slack if Not Frontmost.scpt` in a directory like `~/Applications`.

Place the file `cdz.restartslack.plist` in `~/Library/LaunchAgents`. You’ll first want to edit it so that it points to the correct `Restart Slack if Not Frontmost.scpt` path.

Run the command `launchctl load cdz.restartslack.plist` to set up the task.

## Uninstalling

Run the command `launchctl unload cdz.restartslack.plist` to unload the task. Then remove `Restart Slack if Not Frontmost.scpt` from `~/Applications`, and `cdz.restartslack.plist` from `~/Library/LaunchAgents`.

## Additional Tools & Reference

- [A `launchd` Tutorial](http://launchd.info)
- [`launhctl(1)`](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/launchctl.1.html)
- [Lingon](https://itunes.apple.com/us/app/lingon-3/id450201424?mt=12) can be used to create, edit, and manage launch agent plists.

## License

The [Unlicense](http://unlicense.org); see [`LICENSE.txt`](LICENSE.txt).
