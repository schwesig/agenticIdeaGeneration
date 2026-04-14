# PoC: Scraper via Chrome DevTools mit sprite.dev

**Working Title:** DoKa-Scrape

Siehe Issue [#1](https://github.com/schwesig/agenticIdeaGeneration/issues/1).

## Ziel

Einen Web-Scraper mit Hilfe von [sprite.dev](https://sprite.dev) erzeugen,
der auf Chrome DevTools (Chrome DevTools Protocol / Puppeteer / Playwright)
als Laufzeit basiert.

## Idee des Ablaufs

1. **Aufzeichnen**: Eine interaktive Browser-Session wird aufgezeichnet
   (Klicks, Navigation, Netzwerk-Requests).
2. **Generieren**: sprite.dev erzeugt aus der Aufzeichnung Scraper-Code
   (Selektoren, Wartepunkte, Extraktionslogik).
3. **Ausfuehren**: Der generierte Code laeuft headless via Puppeteer
   oder Playwright und liefert strukturierte Daten (JSON).

## Architektur-Skizze

```
 +----------------+      +-----------+      +------------------+
 | Browser-Session|  ->  | sprite.dev|  ->  |  Scraper (JS/TS) |
 | (CDP Recording)|      | Generator |      |  Playwright/CDP  |
 +----------------+      +-----------+      +------------------+
                                                     |
                                                     v
                                              +--------------+
                                              | JSON Output  |
                                              +--------------+
```

## Offene Punkte

- [ ] sprite.dev API / CLI evaluieren
- [ ] Aufzeichnungsformat definieren (HAR? CDP Trace?)
- [ ] Umgang mit dynamischen Inhalten (SPA, Lazy Load)
- [ ] Rate Limiting, robots.txt, User-Agent
- [ ] Test mit einer realen Zielseite

## Naechste Schritte

1. sprite.dev Dokumentation sichten und Features zusammenfassen
2. Minimalen Prototyp bauen: eine statische Seite scrapen
3. Erweitern auf eine dynamische Zielseite
4. Ergebnisse in diesem Ordner dokumentieren
