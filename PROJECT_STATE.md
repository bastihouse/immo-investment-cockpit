# Projektstand · 20.10.2026

Repository: bastihouse/immo-investment-cockpit. Hosting: GitHub Pages, main / root.
Statische HTML/CSS/JS-App. Modell ausgelagert nach model.js; UI in app.js.
Modell 2: Steuerbasis/AfA, Renovierungsarten, Verkauf mit AfA-Korrektur, laufende ETF-Steuer-Näherung, korrigierter kapitalgleicher Vergleich.
Fünf Tabs: Dashboard mit Eingabeschublade, Cashflows, ETF, Szenarien, Erklärung.
Validierung: Node-Modelltests, Syntaxchecks und Browserprüfung nach Deployment.
Nächste sinnvolle Erweiterungen: konkrete OeKB-Fondsmeldungen; unterjähriger Kauf/Beginn; Anschlussfinanzierung; WEG-Aufwendungen.


## Update 22.10.2026 · Modell 3

rental.js: eigenständige monatliche Mietzins-/Wertsicherungslogik, vierzehn bestehende Steuer-/Finanzierungstests plus sechzehn Mietrechtstests.
MRG/WGG-Auswahl im Dashboard, Pflichtangaben und Sperre ungeklärter 15h-Fälle, Landesrichtwerte 2026, Prognose künftiger Grenzen, Befristungsabschlag, Mindestbefristung, April-/Mai-Indexierung, 15-Jahres-Frist ab erstem Kaufvertrag.
Cashflows, Steuern, Szenarien, CSV und Erklärungstab verwenden den tatsächlich angesetzten monatlichen Hauptmietzins.
ETF-Steuerbasis verständlich erklärt und umbenannt. Grenzen/Quellen siehe README und Erklärungstab.

Browserprüfung: Auswahl, Sperre bei unvollständigen Angaben, Testfall NÖ 70 m² und Cent-Anzeige geprüft. Gesetzliche Obergrenzen werden nicht auf höhere Centbeträge aufgerundet.

## Update · Modell 4 · 22.10.2026
ETF-Proxy ersatzlos entfernt, Altwerte ignoriert; stattdessen Barausschüttungsquote mit Netto-Wiederanlage und Verkaufsteuer. Vereinfachung und fehlende ausschüttungsgleiche Erträge deutlich in Eingabe, Vergleich und Erklärung offengelegt. Info-Dialog mit 5-/10-/20-Jahres-Indexrenditen bis 30.06.2026 (USD, Quellen und Varianten erläutert). Miete/Ausgaben zusammengefasst; MRG-Schalter und bedingte Felder statt drei gleichrangiger Modusbuttons. JSON-Version 4.
