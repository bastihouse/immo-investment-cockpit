# Immo Investment Cockpit · Österreich · Modell 2

Kostenlose statische Webapp ohne Build, Server oder externe Abhängigkeiten.
Eingaben bleiben im Browser (`localStorage`); JSON-Import älterer Versionen bleibt möglich.

## Start und Tests

`index.html` über einen statischen Webserver öffnen. GitHub Pages veröffentlicht `main` / Repository-Stamm.

Modelltests: `node --test model.test.cjs` (Node.js 18 oder neuer).

## Funktionen

- Dashboard mit aufklappbaren Eingaben und sofortiger Neuberechnung nach Bestätigung einer Eingabe.
- SVG-Charts mit Tooltips per Maus, Touch und Tastaturfokus.
- Cashflow-Zerlegung, getrennte Steuerrechnung, Jahres-/Monatsdurchschnitt, echter monatlicher Kreditplan, sortierbare Tabellen, CSV.
- Basis-, vorsichtiges, günstiges und frei konfigurierbares Szenario; zusätzliche Instandhaltung als Liquiditätsschock.
- Sensitivitätsmatrix mit wählbaren Achsen und Kennzahlen; Cashflow-neutrale Miete und Zuschussbedarf.
- Letzter Tab „So wird gerechnet“ mit verständlicher Erklärung, aktuellen Berechnungsbeispielen und Primärquellen.

## Steuerlicher Umfang · geprüft 20.10.2026

Das Modell bildet einen **Neukauf und ganzjährig ab Januar beginnende private Wohnraumvermietung** ab. Es ist kein Steuerbescheid.

- Aktivierbare Erwerbsnebenkosten sind Bestandteil der Anschaffungskosten. Kreditgebühren sind nicht in dieser Position enthalten.
- Gebäude-AfA auf Gebäudeanteil inklusive anteiliger Erwerbsnebenkosten; Grundstück nicht abschreibbar. Kapitalisierte Herstellungskosten werden zur Gebäudebasis addiert.
- Lineare, beschleunigte und erweiterte beschleunigte AfA zur Auswahl. Voraussetzungen muss der Nutzer erfüllen; keine automatische rechtliche Einordnung. AfA ist auf die Basis begrenzt.
- Anfangsrenovierung: aktivierter Herstellungsaufwand / Instandsetzung über 15 Jahre / sofort abgesetzte Instandhaltung. Liquiditätsabfluss jeweils bei Kauf; keine Doppelzahlung.
- Einkommensteuer als Differenz der Tarifsteuer mit und ohne Vermietung. Tarifgrenzen 2026 bleiben nominal konstant; Spitzensatz 55 % nur bis 2029. Anderes steuerpflichtiges Einkommen bleibt konstant. Keine Absetzbeträge oder Veranlagungsfreibeträge.
- Verlustausgleich im gleichen Jahr wählbar, begrenzt durch Tarifsteuer auf anderes Einkommen. Kein Verlustvortrag für Vermietung.
- Tilgung und WEG-Einzahlungen nicht als Werbungskosten angesetzt. Tatsächliche spätere WEG-Aufwendungen und deren steuerliche Behandlung fehlen.
- Verkauf: Anschaffungskosten inklusive aktivierbarer Erwerbsnebenkosten, Herstellungsaufwand bzw. noch nicht abgesetzter Instandsetzung, abzüglich kumulierter Gebäude-AfA. Mitteilungs-/Selbstberechnungskosten gesondert abgezogen; übrige Verkaufskosten nur in der Liquidität. Standard-ImmoESt 30 % auf positiven Gewinn. Kein automatischer Verkaufverlustausgleich.
- Keine Hauptwohnsitz-/Herstellerbefreiung, Altvermögen, Umwidmung, Regelbesteuerungsoption, Umsatzsteuer/Vorsteuer oder Förderungen. Keine Halbjahres-AfA, da Januarbeginn.
- Kleine Vermietung ab 2024: 25-Jahres-Indikator ohne Verkaufsgewinn; keine vollständige Liebhabereiprognose oder steuerliche Anerkennung. Tatsächlicher Rahmen grundsätzlich 25 Jahre ab Vermietungsbeginn / höchstens 28 Jahre ab ersten Aufwendungen.
- ETF: **Näherung** für laufenden steuerpflichtigen Ertrag als frei wählbarer Prozentsatz des Depotwerts vor jährlicher Steuer. Dieser Wert ist keine gesetzliche Pauschale. Fortschreibung der Steuerbasis; Steuerzahlung aus Teilverkauf inklusive dessen Gewinnsteuer und proportionaler Basisreduktion; bei Endverkauf KESt auf verbleibenden positiven Gewinn. Keine konkreten OeKB-Meldedaten, Quellensteuer, Ausschüttungs-/Meldetermine oder Verlustverrechnung.

## Vergleichskonvention

Identisches Anfangskapital und identische externe Zuschüsse. Positive Immobilien-Cashflows werden unverzinst zurückgelegt und finanzieren spätere Fehlbeträge zuerst. Erst zusätzliche externe Einzahlungen werden im ETF gespiegelt. Negative Cashflows werden **nicht erneut** vom Immobilienvermögen abgezogen. Die WEG-Rücklage wird nicht separat beim Verkauf ausgezahlt. Einkommensteuer wird zur Liquiditätsplanung auf zwölf Monate geglättet; Sonderinstandhaltung wird im Januar des Szenariojahres bezahlt.

## Primärquellen

- [BMF · Tarif](https://www.bmf.gv.at/themen/steuern/arbeitnehmerveranlagung/steuertarif-steuerabsetzbetraege/steuertarif-steuerabsetzbetraege.html)
- [BMF · AfA](https://www.bmf.gv.at/themen/steuern/immobilien-grundstuecke/vermietung-verpachtung/absetzung-fuer-abnutzung-bei-vuv.html)
- [BMF · Verkauf / Anschaffungskosten](https://www.oesterreich.gv.at/de/themen/steuern_und_finanzen/immobilienertragsteuer/1/Seite.2420008)
- [RIS · EStG §§ 16, 28, 30, 30a](https://www.ris.bka.gv.at/GeltendeFassung.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10004570)
- [BMF · Verlustverwertung](https://www.bmf.gv.at/themen/steuern/fuer-unternehmen/einkommensteuer/verlustverwertung.html)
- [BMF · Instandsetzung](https://findok.bmf.gv.at/findok/volltext?segmentId=2a19c4fa-f445-4685-b352-3cb766c46d88)
- [BMF · Liebhaberei](https://findok.bmf.gv.at/findok/volltext?segmentId=122eaa17-0686-406b-a344-bbd9e6886f01)
- [BMF · Fonds / Steuerbasis](https://findok.bmf.gv.at/findok/volltext?segmentId=f6bebe28-8310-4cb0-a917-4e70e8d89541)
