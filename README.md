# symiapp.com

Statische Landingpage für Symi. Die Seite lädt keine externen Ressourcen nach:

- keine externen Fonts
- keine CDN-Skripte
- keine externen Bilder
- kein Tracking
- kein Backend

## Cloudflare Pages

Das Cloudflare Pages Projekt heißt `symiapp-com`. Die Pages-Konfiguration liegt in
[`wrangler.jsonc`](wrangler.jsonc), damit der statische Output eindeutig versioniert ist.

### Build Settings

```text
Framework preset: None
Build command: leer lassen
Build output directory: /
Root directory: /
Production branch: main
Preview deployments: All branches
```

Da die Website aus statischen HTML-, CSS- und Asset-Dateien im Repository-Root besteht, ist kein
Build-Schritt nötig. `pages_build_output_dir` zeigt deshalb auf `./`.

### Automatisches Deployment

Cloudflare Pages ist mit `mpwg/symiapp.com` verbunden. Pushes auf `main` erzeugen Production
Deployments, andere Branches erzeugen Preview Deployments.

Die Domain `symiapp.com` läuft über Cloudflare DNS und ist als Custom Domain für das Pages-Projekt
vorgesehen. Der DNS-Eintrag für die Apex-Domain muss auf das Pages-Subdomain-Ziel zeigen:

```text
Type: CNAME
Name: @
Target: symiapp-com.pages.dev
Proxy status: Proxied
```

HTTPS wird von Cloudflare Pages automatisch bereitgestellt, sobald die Domain validiert ist.

Vor Veröffentlichung müssen die Platzhalter in `impressum.html` und `support.html` ergänzt werden.
