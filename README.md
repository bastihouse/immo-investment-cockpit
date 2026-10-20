# Immo Investment Cockpit (Österreich)

Kostenfreie, komplett clientseitige Demo-Webapp zur überschlägigen Analyse einer privat vermieteten, fremdfinanzierten österreichischen Wohnimmobilie und zum Vergleich mit einem ETF. Es werden keine Daten an einen Server geschickt. Einstellungen werden im `localStorage` gespeichert und können als JSON exportiert/importiert werden.

## Veröffentlichung mit GitHub Pages

1. Auf https://github.com/new ein öffentliches Repository mit Namen `immo-investment-cockpit` erstellen, am besten **ohne** README oder Vorlage.
2. Dateien `index.html`, `style.css`, `app.js`, `.nojekyll` und `README.md` aus diesem Paket im Repository-Stamm hochladen (Add file → Upload files).
3. Unter **Settings → Pages** die Quelle **Deploy from a branch**, Branch **main**, Folder **/(root)** auswählen und speichern.
4. Die Website befindet sich danach unter `https://BENUTZERNAME.github.io/immo-investment-cockpit/`.

## Rechenlogik & Grenzen

- **Ankauf:** Kaufpreis + pauschale Erwerbsnebenkosten + Renovierung; Darlehen = Gesamtbedarf − Eigenkapital; Annuität bei konstantem Zinssatz.
- **Monatsmodell:** 12 Monate je Jahr mit Zinsen, Tilgung, Nettomiete, Leerstand, nicht umlegbaren Betriebskosten, Rücklage und pauschaler jährlicher Instandhaltung.
- **Einkommensteuer:** vereinfachte Tarifdifferenz 2026 zwischen anderem steuerpflichtigen Einkommen und zusätzlichem Vermietungsergebnis (Einnahmen − abzugsfähige Kosten − Zinsen − Gebäude-AfA). Tarifstufen 2026: bis 13.539 EUR 0%, danach 20%, 30%, 40%, 48%, 50%, ab 1 Mio. EUR bis 2029 55%. Kein Ansatz von Absetzbeträgen, Sonderausgaben, Verlustausgleichsbeschränkungen oder individuellen Sondertatbeständen.
- **AfA:** Vereinfachte lineare Gebäude-AfA auf den gewählten Gebäudeanteil des Kaufpreises. Die Bemessungsgrundlage und die Halbjahres-/beschleunigte AfA können im Einzelfall anders ausfallen.
- **WEG-Rücklage:** Liquiditätsabfluss, nicht sofort als Werbungskosten berücksichtigt. Die spätere steuerliche Verwertung tatsächlicher rücklagenfinanzierter Aufwendungen ist nicht automatisch modelliert.
- **Verkauf:** Ertrag auf den Wertzuwachs nach pauschalen Verkaufskosten mit vom Nutzer bestimmtem ImmoESt-Satz. Dies ist ein **stark vereinfachtes Modell**, **keine** rechtlich exakte ImmoESt-Bemessungsgrundlage (insbesondere AfA-Korrekturen der Anschaffungskosten, Herstellung-/Instandsetzungskosten, Hauptwohnsitzbefreiung, Altvermögen und besondere Tatbestände fehlen).
- **ETF:** monatliche Rendite auf Bruttovermögen; vereinfachte KESt ausschließlich auf positiven Gesamtgewinn bei hypothetischer Liquidation. **Wichtig:** Österreichische Meldefonds werden u.a. laufend über ausschüttungsgleiche Erträge besteuert; das ist **nicht** abgebildet. ETF-Ergebnis deshalb illustrativ, nicht als exakte Netto-Steuerprognose verwenden.
- **Vergleichslogik:** gleiche anfängliche Eigenkapitalauszahlung; monatliche ETF-Einzahlung basiert derzeit auf dem *geglätteten* monatlichen Immobilien-Cashflow nach annualisierter Steuerwirkung. Positive Immobilien-Cashflows werden als nicht verzinste Liquidität kumuliert. Für exakte liquiditätsgleiche Simulation sind echte Steuerzahlungszeitpunkte, variable Rückflüsse und andere Sparratenkonventionen vorzusehen.
- **Achtung:** Durch Vereinfachungen kann die langfristige Rendite insbesondere bei Sanierungen, Mietrecht, Inflation, variablen Kreditzinsen, WEG-Abrechnungen und österreichischer ETF-Besteuerung deutlich abweichen.

## Quellen & Stand

- [BMF Steuertarif 2026](https://www.bmf.gv.at/themen/steuern/arbeitnehmerveranlagung/steuertarif-steuerabsetzbetraege/steuertarif-steuerabsetzbetraege.html-0)
- [BMF AfA bei Vermietung und Verpachtung](https://www.bmf.gv.at/themen/steuern/immobilien-grundstuecke/vermietung-verpachtung/absetzung-fuer-abnutzung-bei-vuv.html)

**Rechtsstand des vereinfachten Modells:** Oktober 2026. Keine Steuer-, Kredit- oder Anlageberatung.
