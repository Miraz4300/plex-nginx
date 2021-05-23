# Plex Nginx Reverse Proxy

Configuration to serve Plex & Tautulli via Nginx.

## Minimal Requirements:

1. Nginx
2. Plex
3. Tautulli (optional - tautulli server block can be removed)

* Remote Access - Disable.
* Network - Custom server access URLs = `https://<your-domain>:443,http://<your-domain>:80`
* Network - Secure connections = Preferred.

Note: `you can force SSL by setting required and not adding the HTTP URL, however some players which do not support HTTPS (e.g: Roku, Playstations, some SmartTVs) will no longer function.`

## Optional Requirements:

UFW (Linux) or other firewall:

* Disable or Deny port 32400 on public IP. (Plex still pings over 32400, some clients may use 32400 by mistake despite 443 and 80 being set).
* Disable port forwarding on router/switch for port 32400.

Note: `adding allowLocalhostOnly="1" to your Preferences.xml, will make Plex only listen on the localhost, achieving the same thing as using a firewall.`

## Tautulli:

* make sure HTTP Proxy is checked under Settings > Show Advanced button > Web Interface
* for custom url: Settings > Show Advanced button > Web Interface > HTTP Root. change the base URL to nginx configuration's Tautulli location block name.
