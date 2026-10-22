# Immo Investment Cockpit · Österreich · Modell 3

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


## Mietrecht · ergänzt 22.10.2026

Drei Schaltflächen: freier Mietzins (MRG-Teilanwendung oder ausdrücklich außerhalb MRG), Genossenschaftskauf nach § 15h WGG, sonstige MRG-Fälle mit manuell geprüfter unbefristeter Obergrenze.

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

„Geschätzte jährliche ETF-Steuerbasis (% vom Depot)“ ersetzt die missverständliche frühere Bezeichnung. 2 % sind eine Annahme zur Bemessungsgrundlage, kein Steuersatz und keine zusätzliche Rendite. Beispiel: 10.000 € Depotwert → 200 € angenommener laufender steuerpflichtiger Ertrag → 55 € KESt bei 27,5 %, vor möglicher Teilverkaufssteuer. Die tatsächlichen Fondsmeldedaten sind ausschlaggebend. An der bisherigen ETF-Rechenlogik ändert diese Erläuterung nichts.
