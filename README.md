# Raycast Monitor

Monitors the RAM usage of raycast and kills it if it is over a defined threshold.

## Configure

Create oder edit the file `~/.config/fx/raycast-monitor/.env` and provide the following Environment Variables:

```bash
RAYCAST_MONITOR___APP_NAME="<appName>"              # Default: "Raycast"
RAYCAST_MONITOR___MAX_RAM_USAGE_MB="<maxRamInMb>"   # Default: "500"
````


## Scheduling the raycast monitor
To schedule the raycast monitor copy the plist file to `~/Library/LaunchAgents/de.frixxx.raycastmonitor.plist`.

Then get the raycast-monitor path by running:
```sh
which raycast-monitor
```
Edit the plist file and set the `ProgramArguments` key to the path you got from the previous command.

Then load the plist with:
```sh
launchctl load ~/Library/LaunchAgents/de.frixxx.raycastmonitor.plist
```
Um den Dienst zu stoppen, verwenden Sie:
```sh
launchctl unload ~/Library/LaunchAgents/de.frixxx.raycastmonitor.plist
```
