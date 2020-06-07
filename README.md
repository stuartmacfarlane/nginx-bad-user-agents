# NginX Bad User Agents

## What is this?
This is a list of bad user agents that I personally block on all my private clients servers.
It is updated from time to time and always tested in production before being added to this repo.

## How do I use it?
Copy the config file to /etc/nginx/badbots and then include the following code within your virtual host configuration either globally or per domain.

```
# includes the list of bad bots from a seperate file
include badbots/nginx-bad-user-agents.conf;

# returns HTTP 444 for each bad bot instead of HTTP 200
if ($bad_client) { return 444; }
```
