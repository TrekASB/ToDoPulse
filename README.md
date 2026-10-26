# ToDoPulse

Norconsult dashboard-extension for Trimble Connect, basert på designkonseptet i [BCFT](https://github.com/TrekASB/BCFT).

## Leveransestatus

Prototype med fungerende dashboard, filtre, diagrammer og Trimble Connect Workspace-autentisering. **Live Issues API er ikke ferdig konfigurert eller verifisert.** Ingen fiktive saker vises. Appen er lesebasert og endrer ikke saker.

## Oppsett

1. Opprett et **public** repository med navnet `ToDoPulse` under `TrekASB`.
2. Last opp `index.html`, `manifest.json` og `README.md` på `main`.
3. Aktiver GitHub Pages under Settings → Pages → Deploy from a branch → `main` / root.
4. Åpne `https://trekasb.github.io/ToDoPulse/index.html` etter publisering.
5. Registrer extensionens manifest/URL i Trimble Connect med `https://trekasb.github.io/ToDoPulse/manifest.json`.
6. Under *API-oppsett og diagnostikk* oppgi det **verifiserte** Issues-listeendepunktet fra Trimble API og eventuelt JSON-sti til saksliste.

## Teknisk

- Bruker Trimble Connect Workspace API for aktiv prosjekt-ID og brukergodkjent tilgangstoken.
- Begrenser utgående bearer-token til HTTPS-endepunkter på `*.connect.trimble.com` og `*.api.trimble.com`.
- Tar imot en JSON-liste direkte eller under `items`, `data.items`, `results`, `data` eller `issues`.
- Normaliserer typiske navnevarianter for status, prioritet, ansvarlig, tidsfrist og opprettetdato. Sjekk feltnavn mot faktisk Issues API-respons.
- Tar foreløpig ikke hensyn til API-paginering, og tidsserien baserer seg på opprettelsesdato per måned.
- Gjenbruker Norconsult-logo fra eksisterende BCFT-publicering. Kilden må være offentlig tilgjengelig.

## Dokumentasjon

https://developer.trimble.com/docs/connect/tools/api/issues/

> Viktig: Ikke ta appen i produksjon før API-endepunkt, tilgang, paginering og datamapping er testet i prosjekt.
