# Automatic CI/CD pipeline:

1. I push to GitHub from Obsidian with an extension.
2. Github sends a webhook to https://krissssz.ddns.net/hooks/netconfigs-pull
3. NGINX proxies the request to localhost:9000
4. The `webhook` service handles the request according to ~/hooks/netconfigs-pull.json
5. The hook json (netconfigs-pull.json) runs the `~/scripts/netconfig-pull.sh` script
6. The obsidian vault is pulled to `/var/www/html/quartz/content`
7. quartzwiki.service notices the change automatically, and rebuilds the site.
8. Site is down for around a few seconds to a  minute (depending on the change that happened to the site), then it's up again with the new content. 

Site works like this:

1. User searches https://krissssz.ddns.net/wiki
2. NGINX serves static files with `/var/www/html/quartz/public`. It also handles TLS with certbot.


# Quartz v4

> “[One] who works with the door open gets all kinds of interruptions, but [they] also occasionally gets clues as to what the world is and what might be important.” — Richard Hamming

Quartz is a set of tools that helps you publish your [digital garden](https://jzhao.xyz/posts/networked-thought) and notes as a website for free.
Quartz v4 features a from-the-ground rewrite focusing on end-user extensibility and ease-of-use.

🔗 Read the documentation and get started: https://quartz.jzhao.xyz/

[Join the Discord Community](https://discord.gg/cRFFHYye7t)

## Sponsors

<p align="center">
  <a href="https://github.com/sponsors/jackyzha0">
    <img src="https://cdn.jsdelivr.net/gh/jackyzha0/jackyzha0/sponsorkit/sponsors.svg" />
  </a>
</p>
