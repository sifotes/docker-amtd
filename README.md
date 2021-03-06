# AMTD - Automated Movie Trailer Downloader 
[RandomNinjaAtk/amtd](https://github.com/RandomNinjaAtk/docker-amtd) is a Radarr Companion script to automatically download movie trailers for use in media applications

[![RandomNinjaAtk/amtd](https://raw.githubusercontent.com/RandomNinjaAtk/unraid-templates/master/randomninjaatk/img/amtd.png)](https://github.com/RandomNinjaAtk/docker-amtd)


## Features
* Downloading **Movie Trailers** using online sources for use in popular applications (Plex/Kodi/Emby/Jellyfin): 
  * Connects to Radarr to automatically download trailers for Movies in your existing library
  * Downloads trailers using youtube-dl automatically
  * Names trailers correctly to match Kodi/Plex naming convention
  * Embeds relevant metadata into each trailer


## Supported Architectures

The architectures supported by this image are:

| Architecture | Tag |
| :----: | --- |
| x86-64 | amd64-latest |

## Version Tags

| Tag | Description |
| :----: | --- |
| latest | Newest release code |


## Parameters

Container images are configured using parameters passed at runtime (such as those above). These parameters are separated by a colon and indicate `<external>:<internal>` respectively. For example, `-p 8080:80` would expose port `80` from inside the container to be accessible from the host's IP on port `8080` outside the container.

| Parameter | Function |
| --- | --- |
| `-e PUID=1000` | for UserID - see below for explanation |
| `-e PGID=1000` | for GroupID - see below for explanation |
| `-v /config` | Configuration files for AMTD. |
| `-v /change/me/to/match/radarr` | Configure this volume to match your Radarr Radarr's volume mappings associated with Radarr's Library Root Folder settings |
| `-e AUTOSTART="true"` | true = Enabled :: Runs script automatically on startup |
| `-e RadarrUrl="http://127.0.0.1:8686"` | Set domain or IP to your Radarr instance including port. If using reverse proxy, do not use a trailing slash. Ensure you specify http/s. |
| `-e RadarrAPIkey="08d108d108d108d108d108d108d108d1"` | Lidarr API key. |
| `-e CountryCode=us` | Set the country code for preferred Radarr matching, uses Musicbrainz Country Codes, lowercase only. |
| `-e videoformat="--format bestvideo[vcodec*=avc1]+bestaudio"` | For guidence, please see youtube-dl documentation |
| `-e subtitlelanguage="en"` | Desired Language Code :: For guidence, please see youtube-dl documentation. |
| `-e FilePermissions=666` | Based on chmod linux permissions |

# Script Information
* Script will automatically run when enabled, if disabled, you will need to manually execute with the following command:
  * From Host CLI: `docker exec -it amtd /bin/bash -c 'bash /config/scripts/download.bash'`
  * From Docker CLI: `bash /config/scripts/download.bash`
  
## Directories:
* <strong>/config/scripts</strong>
  * Contains the scripts that are run
* <strong>/config/logs</strong>
  * Contains the log output from the script
* <strong>/config/cache</strong>
  * Contains the artist data cache to speed up processes
* <strong>/config/coookies</strong>
  * Store your cookies.txt file in this location, may be required for youtube-dl to work properly
  
  
<br />
<br />
<br />
<br />
  
 
 ##### Attribution 
 Icons made by <a href="http://www.freepik.com/" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon"> www.flaticon.com</a>
