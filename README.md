# Immo Investment Cockpit · Österreich · Modell 4

Kostenlose statische Webapp ohne Build, Server oder externe Abhängigkeiten.
Eingaben bleiben im Browser (`localStorage`); JSON-Import älterer Versionen bleibt möglich.

## Start und Tests

`index.html` über einen statischen Webserver öffnen. GitHub Pages veröffentlicht `main` / Repository-Stamm.

Modelltests: `node --test model.test.cjs rental.test.cjs` (Node.js 18 oder neuer).

## Funktionen

- Dashboard mit aufklappbaren Eingaben und sofortiger Neuberechnung nach Bestätigung einer Eingabe.
- SVG-Charts mit Tooltips per Maus, Touch und Tastaturfokus.
- Cashflow-Zerlegung, getrennte Steuerrechnung, Jahres-/Monatsdurchschnitt, echter monatlicher Kreditplan, sortierbare Tabellen, CSV.
- Basis-, vorsichtiges, günstiges und frei konfigurierbares Szenario; zusätzliche Instandhaltung als Liquiditätsschock.
- Sensitivitätsmatrix mit wählbaren Achsen und Kennzahlen; Cashflow-neutrale Miete und Zuschussbedarf.
- Letzter Tab „So wird gerechnet“ mit verständlicher Erklärung, aktuellen Berechnungsbeispielen und Primärquellen.

## Steuerlicher Umfang · geprüft 20.10.2026

Das Modell bildet einen **Neukauf im Januar und private Wohnraumvermietung mit wählbarem Mietvertragsbeginn** ab. Es ist kein Steuerbescheid.

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
- ETF: **Vereinfachte Ausschüttungs-/Verkaufsrechnung**. Keine automatische 2-%-Steuerbasis. Editierbare Barausschüttungsquote (Standard 0), bereits in der Gesamtrendite enthalten. Monatliche KESt auf Ausschüttung, Netto-Wiederanlage erhöht Anschaffungskosten; Endverkauf besteuert positiven Restgewinn. Ausschüttungsgleiche Erträge und Quellensteueranrechnung fehlen ausdrücklich, daher kann die Thesaurierungsvariante zu günstig erscheinen. Alte etfTaxableYield-Werte werden ignoriert.

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


## Mietrecht · ergänzt 22.10.2026

Ein MRG-Schalter, darunter die rechtliche Einordnung: MRG-Teilanwendung mit freiem Mietzins, Genossenschaftskauf nach § 15h WGG oder andere geprüfte Obergrenze. Bei MRG aus: ausdrücklich außerhalb MRG.

- § 15h: geförderte Errichtung/Finanzierung, Übertragung an bisherigen Mieter bzw. Erwerbskette, maßgeblicher Antrag/Angebot ab 1.8.2019 (§ 39 Abs. 36), Datum des ersten Kaufvertrags, Wohnnutzfläche, Bundesland, Gebäude ab 9.5.1945 und geprüfte verbleibende Förderungs-/Vertragsbindungen erforderlich.
- Direkter Anlegerkauf, sofortige Eigentumsübertragung, ungeklärte oder alte Fälle werden nicht automatisch als 15h-Fall qualifiziert. Unvollständige Angaben sperren Ergebnisse und CSV statt eine rechtliche Einordnung zu erfinden.
- 15 Jahre ab erstem Kaufvertrag, kein Neustart durch Weiterverkauf. Hauptmietzinsgrenze = reiner Landesrichtwert × Fläche; befristet 25 % Abschlag. Kein Lagezuschlag. Niedrigere Wunschmiete wird nicht angehoben.
- Bekannte Landesrichtwerte vor/nach April 2026 gemäß Statistik Austria. Zukünftige Richtwerte werden mit einer gekennzeichneten VPI-Annahme projiziert: 2027 maximal +2 %, ab 2028 über 3 % nur halbe Überschreitung, gesetzliche Cent-Rundung.
- MieWeG bei MRG-Voll-/Teilanwendung: jährlicher April-Termin, bei Vollanwendung im Modell Mai unter Annahme rechtzeitiger Mitteilung (§ 16 Abs. 9 MRG). Erste Valorisierung zeitanteilig nach vollen Monaten nach Vertragsabschluss; keine automatische Anpassung im Abschlussjahr. Vertragsgrenze kann die Erhöhung weiter begrenzen; ohne gültige Klausel keine Erhöhung.
- Mindestbefristung ab 2026: fünf Jahre bei Unternehmern, drei Jahre bei Nichtunternehmern. Fortsetzung zu gleichen Konditionen angenommen. Kein Marktmietensprung bei Fristablauf.
- Mietvertragsdatum = Beginn der Einnahmen; anteilige Kalendermonate. AfA unterstellt weiterhin steuerliche Vermietungsbereitschaft ab Januar; abweichender Beginn ist nicht automatisch beurteilt.
- Zusätzliche Einnahmen müssen im MRG-Modus eigenständig rechtlich geprüft sein. Sie dürfen die Obergrenze nicht umgehen. Förderungsgrenzen können zusätzlich als konstante absolute Grenze eingegeben werden.
- Alte Mietverträge vor 2026, individuelle Indexklauseln, Förderungsrecht, allgemeine Altbau-/Kategorie-/Zuschlagsberechnung und Verkaufs-/Nachzahlungsansprüche nach §§ 15g/15i WGG sind keine automatische Rechtsprüfung. Sonstige MRG-Grenzen sind manuell einzutragen.

Die ursprüngliche Aussage „Mietrecht nicht modelliert“ gilt damit nur noch für diese ausdrücklich genannten Sonderfälle.

### Zusätzliche Primärquellen

- https://www.ris.bka.gv.at/eli/bgbl/1979/139/A1P15h/NOR40244830
- https://ris.bka.gv.at/GeltendeFassung.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10011509
- https://www.statistik.at/fileadmin/pages/2114/VOe_Richtwerte_Kategoriemieten_20260401.pdf
- https://ris.bka.gv.at/eli/bgbl/i/2025/114/P1/NOR40274266
- https://www.oesterreich.gv.at/de/themen/bauen_und_wohnen/wohnen/3/Seite.210215

## ETF-Eingabe verständlicher benannt

Die frühere 2-%-Steuerbasis wurde entfernt. Sie wird auch aus alten Browserdaten/JSON-Dateien nicht übernommen. Die neue Ausschüttungsquote startet bei 0. Das Modell ist ausdrücklich keine vollständige österreichische Fondssteuerrechnung: auch ohne Auszahlung/Verkauf können ausschüttungsgleiche Erträge anfallen.

## Update · Eingaben und Indexinfo (22.10.2026)

Miete, Leerstand und laufende Ausgaben bilden einen gemeinsamen Bereich. Ein MRG-Schalter aktiviert Voll-/Teilanwendung; darunter werden Genossenschaftskauf, Teilanwendung oder andere geprüfte Grenze ausgewählt. Bei MRG aus wird tatsächlich außerhalb MRG gerechnet. Bestehende v3-MRG-Eingaben bleiben erhalten.

Info-Dialog direkt bei ETF-Rendite: annualisierte USD-Renditen bis 30.06.2026, Start 30.06.2021/2016/2006. MSCI World Net Return: 11,5 / 13,1 / 8,7 % (veröffentlichte Rundung auf eine Dezimalstelle). S&P 500 Total Return: 13,41 / 15,51 / 11,39 %. Wiederangelegte Dividenden; MSCI nach standardisierter Quellensteuer, S&P vor Quellensteuer. Keine österreichische KESt/ETF-Gebühren; EUR-Rendite weicht ab. Keine automatische Übernahme in Prognose.
Quellen: https://www.walterscott.com/strategies/global-equity/global-equity-usd/ (MSCI-Benchmark per 30.06.2026) und https://www.spglobal.com/spdji/en/documents/spiva/spiva-us-mid-year-2026.pdf (Report 3, S. 21). Die Quelle von Walter Scott wird als Index-Benchmark verwendet, nicht die Rendite des aktiven Fonds.

## Update · Modell 5 · 26.10.2026
- Eigenkapital: zwei einmalige Auto-Buttons 10/20 % des reinen Kaufpreises, Cent-Rundung. Nebenkosten/Renovierung werden nicht in die Prozentbasis einbezogen. Danach frei editierbar.
- Kompakte Info-Symbole mit einfacher Bedeutung und Auswirkung; Hover, Tastaturfokus und Klick/Touch. Alte längere Hilfstexte in Tooltips übernommen.
- Immobilien-Wertentwicklung/Verkauf und ETF-Rendite/Steuern in getrennten Eingabegruppen.
- Dynamischer Hinweis zu AfA und tatsächlicher ESt-Entlastung im ersten Jahr; keine zusätzliche Erstattung addiert. Bestehende Steuerlogik unverändert.
- Indexinfo: beide EUR Net Return ungesichert bis 30.06.2026, ausdrücklich gerundete Orientierungswerte. MSCI World 12,4/12,8/9,3 %, S&P 500 13,9/14,6/ca.11,3 % für 5/10/20 Jahre.

Nachvollziehbare Umrechnung: MSCI USD-Net-Kumulativrenditen 5J 72,12 %, 10J 243,63 % (State-Street-Benchmarktabellen per 30.06.2026), 20J CAGR 8,7 % (Walter Scott/MSCI). S&P USD-Net-CAGR 5J 12,92 %, 10J 14,93 % (State Street). EZB USD je EUR an den Startdaten 2021/2016/2006: 1,1884/1,1102/1,2713; Ende 2026: 1,1394. Formel EUR-CAGR = (1+USD-CAGR)*(FXStart/FXEnd)^(1/n)-1. Ergebnisse vor Anzeige-Rundung MSCI 12,41481577/12,84481477/9,29697336; S&P 13,87493841/14,63200998. S&P 20J ca.11,3 % EUR Net Return ist eine als solche gekennzeichnete gerundete Sekundärquellenangabe von Signal Alpha (https://signal-alpha.fr/rendement-bourse/), keine eigene exakte Indexreihenrechnung. Kein Mischen von Brutto-/Netto-Dividenden. Die Daten wurden nicht als angeblich exakte offizielle EUR-Factsheet-Zahlen ausgegeben. Curvo-Reihen geprüft, aber für S&P verworfen, weil sie eine andere Ertragsvariante abbilden. Quellen im App-Dialog.

AfA/Verlustausgleich geprüft: https://www.bmf.gv.at/themen/steuern/immobilien-grundstuecke/vermietung-verpachtung/absetzung-fuer-abnutzung-bei-vuv.html und https://www.bmf.gv.at/themen/steuern/fuer-unternehmen/einkommensteuer/verlustverwertung.html. Keine automatische jährliche Erstattung allein aus dem Kaufpreis; Grund und Boden nicht abschreibbar, Verlustausgleich nur bei zulässigem und anerkanntem Verlust.
