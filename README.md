## restart-slack

This collection of components allows you to automatically and unobstrusively
restart Slack periodically. It is written for OS X and uses Automator and
plists, and is credited to Chris Dzombak.

### Automator script

"Restart Slack if Not Frontmost.scpt" handles the task of restarting Slack. 
It takes care not to restart it when the window is frontmost on the screen.
When you have something else that you're focusing on, Slack can restart without loss of data.

### plist

"cdz.restartslack.plist" handles the task of scheduling the task of restarting Slack.

## Installing and configuring

Place the file "Restart Slack if Not Frontmost.scpt" in a directory like ~/Applications.
It depends on Slack being installed in /Applications/Slack.app which is the normal spot for it.

Place the file "cdz.restartslack.plist" in ~/Library/LaunchAgents . You'll first want to edit it so that it
points to the correct "Restart Slack if Not Frontmost.scpt" path.

Run the command `launchctl load cdz.restartslack.plist` to set up the task.

## Uninstalling

Run the commadn `launchctl unload cdz.restartslack.plist` to unload the task.
