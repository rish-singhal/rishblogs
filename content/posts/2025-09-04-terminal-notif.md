---
title: "Notifications for Terminal Commands"
date: "2025-09-04"
tags: [Productivity]
---

## Introduction
Sometimes, it’s the little things that make a big impact. In my day-to-day workflow, I often run lengthy processes in the terminal—deployments, builds, tests—you name it. Instead of staring at an idle screen, I’ve found that setting up desktop notifications can free my mind to focus on other tasks.

## Why Notifications Matter
When you’re juggling multiple projects, context-switching is inevitable. Automatically receiving a “done” alert when your command completes saves cognitive load. It means you can safely work on something else or take a quick break without fear of missing that crucial finish time.

## Quick Setup on macOS
You can set up instant notifications whenever a process completes. There are two easy approaches:

1. **AppleScript**  
   If you want to rely on built-in macOS utilities, chain an AppleScript command:
   ```bash
   my_long_process && osascript -e 'display notification "Process completed!" with title "Terminal Alert"'
   ```

2. **terminal-notifier**  
   For more flexibility:
   ```bash
   brew install terminal-notifier
   my_long_process && terminal-notifier -title "Done" -message "Build finished!"
   ```

## Customizing Alerts
For a custom message, a shell function is handy:
```bash
function notify_done() {
  local msg="${1:-All done!}"
  terminal-notifier -title "Terminal Alert" -message "$msg"
}
```
Then you can run:
```bash
my_long_process && notify_done "Deployment complete!"
```

## Next Steps
- Combine notifications with Slack or other messaging services if you need cross-device alerts.
- Keep an eye out for other small wins in your workflow. Incremental gains, when added up, lead to big results.

## Conclusion
Don’t wait around for that build to finish. Automate notifications, reclaim your focus, and iterate on your habits.
