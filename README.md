# symiapp.com

Statische Landingpage für Symi. Die Seite lädt keine externen Ressourcen nach:

- keine externen Fonts
- keine CDN-Skripte
- keine externen Bilder
- kein Tracking
- kein Backend

## Cloudflare Pages

Das Cloudflare Pages Projekt heißt `symiapp-com` und verwendet die Konfiguration aus
[../wrangler.jsonc](/Users/mat/code/Symi/wrangler.jsonc).

Für Cloudflare Pages kann dieses Verzeichnis als statischer Output verwendet werden:

```text
semiapp.com
```

Build command leer lassen oder auf `None` setzen. Das Output-Verzeichnis ist `semiapp.com`, wenn aus dem Repository-Root deployed wird.

Die einmalige Einrichtung für GitHub-Integration, Preview Deployments und `symiapp.com` ist in
[docs/Cloudflare-Pages.md](/Users/mat/code/Symi/docs/Cloudflare-Pages.md) dokumentiert.

Vor Veröffentlichung müssen die Platzhalter in `impressum.html` und `support.html` ergänzt werden.
