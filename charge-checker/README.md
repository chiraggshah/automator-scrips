As per https://www.apple.com/batteries/maximizing-performance/,
If you store a device when its battery is fully discharged,
the battery could fall into a deep discharge state,
which renders it incapable of holding a charge.
Conversely, if you store it fully charged for an extended period of time,
the battery may lose some capacity, leading to shorter battery life.

This App / Automator Workflow shows a notification:
- If the battery is charged to > 80%, reminding you to unplug
- If the battery goes below 20%, reminding you to plug it in.

1. Place the ChargeChecker.app in your applications directory
2. Move the info.plist file to `~/Library/LaunchAgents`. (This file is needed to make it run every 10 minutes)
3. Finally, to get the launchd daemon to load your configuration file, run the following in terminal

`launchctl load ~/Library/LaunchAgents/com.apple.automator.ChargeChecker.plist`

From then on, the app will run every 10 minutes.

If you want to stop it from running, then unload it:

`launchctl unload ~/Library/LaunchAgents/com.apple.automator.ChargeChecker.plist`
