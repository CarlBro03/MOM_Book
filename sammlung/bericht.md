# Bericht: öffentliche Musterdateien für die Eingangserkennung

Stand: 30.09.2026 · Inventar: `inventar.csv` (23 gelesene Funde) · Kandidaten: `kandidaten.csv` (50 ungelesene URLs) · Geladen wurde nichts.

## Ampel

| Bereich | Ampel | Kurzgrund |
|---|---|---|
| Jahresabschluss-PDF mit Kontennachweis | ROT | 0 Funde gelesen. Alle Hersteller- und Kammerhosts waren gesperrt. |
| Summen- und Saldenliste (xlsx/csv/pdf) | ROT | 0 Funde gelesen. Es liegen nur Kandidaten-URLs vor. |
| BWA (pdf/xlsx) | ROT | Nur eine leere Zeilenstruktur als CSV (Nr. 19). Kein ausgefülltes Muster gelesen. |
| Kontenrahmen SKR03/SKR04 | GELB | 19 Funde, alle aus öffentlichen Repos. Keine Herstellerdatei. Lizenz und DATEV-Rechte sind unklar. |
| DATEV-Importformate (EXTF) | GELB | 3 kleine Beispieldateien aus einem MIT-Repo. Die offiziellen DATEV-Beispiele waren nicht lesbar. |
| Herstellereigene Musterdateien | ROT | 0 von 23 Funden. Alle 23 stammen aus GitHub. |

**Ursache für Rot:** Der Egress-Proxy dieser Sitzung hat `WebFetch` und `curl -sIL` für praktisch alle Zielhosts abgelehnt (EGRESS_BLOCKED bzw. HTTP 403). Erreichbar waren nur `github.com` und `raw.githubusercontent.com`, dazu die Trefferlisten von `WebSearch`. Gesperrt waren unter anderem datev.de, alle `*.apps.datev.de`, lexware.de, simba.de, addison.de, wolterskluwer.com, agenda-software.de, lbv-net.de, taxeagle.de und die Sparkassen-Seiten.

Das heißt nicht, dass es dort nichts gibt. Es heißt nur, dass ich es nicht gelesen habe. Für diese Ziele steht deshalb überall „nicht abrufbar", nicht „nicht vorhanden". Ich habe keine Archive, Spiegel oder Umwege benutzt. Ich habe auch die Sperre nicht umgangen.

Aus den Suchtreffern (Titel und URL) habe ich nichts als Fund übernommen. Aufbau, Kontenrahmen, Seitenzahl und Lizenz habe ich nur eingetragen, wenn ich die Datei selbst gelesen habe. `kandidaten.csv` enthält alles, was ich nur aus Titeln kenne.

## Funde je Hersteller/System und Dokumenttyp (aus `inventar.csv`)

| Herkunft (Repo) | JA | SuSa | BWA | Kontenrahmen | Import-Format | Summe |
|---|---|---|---|---|---|---|
| ledermann/datev | 0 | 0 | 0 | 0 | 3 | 3 |
| Odoo l10n_de | 0 | 0 | 0 | 2 (SKR03, SKR04) | 0 | 2 |
| ERPNext/frappe | 0 | 0 | 0 | 3 (SKR03 verified, SKR04 verified, SKR03 unverified) | 0 | 3 |
| alyf-de/SKR04 | 0 | 0 | 0 | 1 (SKR04 mit HGB-Gliederung) | 0 | 1 |
| baltpeter/skr-json | 0 | 0 | 0 | 3 (SKR03, SKR04, SKR49) | 0 | 3 |
| scka-de/german-accounting | 0 | 0 | 0 | 1 (SKR03 und SKR04) | 0 | 1 |
| spritelite/SKR03 | 0 | 0 | 0 | 1 | 0 | 1 |
| GnuCash de_DE | 0 | 0 | 0 | 3 (SKR03, SKR04, SKR49) | 0 | 3 |
| thinserver/PHPAdvokat | 0 | 0 | 0 | 1 (SKR03 und SKR04, Stand 2007) | 0 | 1 |
| SebastianAlmer/fibu_konverter_datev2csv | 0 | 0 | 1 (leere Struktur) | 0 | 0 | 1 |
| Kleinere Repos (4commerce, hanneshier, mwelters, Tryton) | 0 | 0 | 0 | 4 | 0 | 4 |
| **Summe** | **0** | **0** | **1** | **19** | **3** | **23** |

Hersteller nach Auftrag: DATEV, Addison, Simba, Lexware, Agenda, sevDesk, lexoffice, Collmex und Buchhaltungsbutler haben je 0 gelesene Funde.

## Lücken (wofür nichts gelesen wurde)

- **Jahresabschluss mit Kontennachweis:** nichts gelesen, für alle Hersteller. Das gilt auch für die DATEV-Datei „Musterauswertungen Jahresabschluss auf Basis von Kontenzwecken" und die Kammer- und Verbandsmuster (LBV, Steuerberaterkammer Köln). Sie stehen in `kandidaten.csv`.
- **Summen- und Saldenliste:** keine Datei gelesen, weder als xlsx, csv noch als PDF. Auch in Repos gibt es keine SuSa mit Testdaten. Nur der Konverter `fibu_konverter_datev2csv` enthält Skripte, die SuSa aus DATEV-PDF lesen, aber kein Beispiel-PDF.
- **BWA:** kein ausgefülltes Muster gelesen. Die DATEV-BWA-Muster, die Vorlagen von Drittanbietern und die BMWK-Vorlage waren gesperrt. Ob die BMWK-Vorlage existiert, weiß ich nur aus einer Suchtreffer-Zusammenfassung.
- **Addison, Simba, Agenda, Lexware, sevDesk, lexoffice, Collmex, Buchhaltungsbutler:** keine Datei gelesen. Nur Hilfeseiten, Handbücher und Anleitungen sind als Kandidaten bekannt. Aus der Suche ergab sich für keines dieser Systeme ein herstellereigenes Muster-PDF. Das ist ein Suchergebnis, kein Beweis, dass es keins gibt.
- **Kontenrahmen SKR07, SKR51, IKR:** in Repos und Suchtreffern nichts gefunden. Die GnuCash-Vorlagen enthalten nur SKR03, SKR04 und SKR49.
- **Orgamax, easybill, FastBill, WISO, Sage, Haufe, Zoho, Candis:** nicht ausgewertet, weil der Proxy die Seiten sperrt. Es gab auch keine Suchtreffer mit Beispieldatei.
- **DATEV-Entwicklerportal (`developer.datev.de`):** nicht lesbar. Ob die offiziellen Beispieldateien dort ohne Login erreichbar sind, ist offen.
- **eBilanz-Taxonomie-Mapping SKR03/04:** nichts gelesen. Der Treffer im eBilanz-Online-Forum war gesperrt.

## Die fünf nützlichsten Funde

Vorab: Keiner der Funde ist ein Jahresabschluss, eine SuSa oder eine ausgefüllte BWA. Es ist Ergänzungsmaterial und kein Ersatz für die eigentlichen Muster.

1. **Nr. 9, alyf-de/SKR04 (`de_skr04_hgb.json`, SKR04):** Ordnet Konten der HGB-Gliederung von Bilanz und GuV zu (Umsatzkostenverfahren). Das ist eine fertige Vorlage für die Zuordnung Konto → Position, die das Werkzeug für die Bilanz auf Kontoebene braucht. Die Datei ist bisher nur als Kopf/README gelesen, der Innenaufbau ist ungeprüft. Das Repo ist seit 2021 archiviert, die Lizenz ist GPL-3.0-or-later.
2. **Nr. 4 und 5, Odoo `account.account-de_skr03/04.csv`:** Die größten Kontenlisten im Fund (etwa 1.275 und 1.193 Zeilen). Sie sind zweisprachig und tragen `tag_ids` als Verweis auf Bilanz- und GuV-Positionen. Anderer Aufbau als die JSON-Bäume: flache CSV mit Kontonummer, Kontentyp und Steuerzuordnung. Lizenz LGPL-3.
3. **Nr. 1 bis 3, ledermann/datev (EXTF Buchungsstapel, Kontenbeschriftungen, Stammdaten):** Die einzigen Beispiele für das DATEV-Importformat. Der Aufbau ist typisch: EXTF-Kopfzeile, dann Spaltenkopf, dann Daten, mit S/H-Kennung in eigener Spalte. Das Format ist neu gegenüber den PDF-Mustern. Die Dateien sind winzig (2 bis 4 Zeilen), also nur ein Formatbeleg. Lizenz MIT.
4. **Nr. 19, fibu_konverter_datev2csv (`DATEV_BWA_Struktur_Vorlage.csv`):** Die einzige BWA-Struktur im Fund. Sie ist leer, hat 49 Zeilen, 12 Monatsspalten und einen Jahreswert und zeigt die Gliederung der DATEV-Jahresentwicklungsübersicht. Das taugt zur Prüfung der Zeilenerkennung, aber nicht für Werte. Lizenz MIT.
5. **Nr. 13, scka-de/german-accounting (SKR03 ↔ SKR04 mit Querverweisen):** Nur eine Auswahl (289 und 254 Konten), aber mit Querverweis zwischen den beiden Kontenrahmen. Damit lässt sich die Erkennung „SKR03 oder SKR04?" prüfen. Datenherkunft unklar (siehe unten). Lizenz MIT.

## Funde mit unklarer Lizenz

- **Alle Kontenrahmen-Funde (Nr. 4 bis 18, 20 bis 23):** Die Repo-Lizenz sagt nichts über die Rechte an den DATEV-Kontenrahmen selbst. Kein Repo belegt, dass DATEV die Weitergabe erlaubt. Ein Suchtreffer (Issue #320 im Repo opengewerk) nennt genau diese Frage („Lizenz vor dem Bau prüfen"). Ein anderer Treffer (UltraCanvas PR #513) beschreibt Kontenlisten, die „aus offiziellen DATEV-Kontenrahmen-PDFs" extrahiert wurden. Das ist urheberrechtlich heikel, ich habe es nicht als Fund aufgenommen.
- **Nr. 14 spritelite/SKR03:** Keine Lizenz angegeben (keine LICENSE-Datei, raw liefert 404). Nicht zum Laden vorgeschlagen.
- **Nr. 21 hanneshier/dolibarr-kontenplan (SKR49):** Keine Lizenz angegeben. Nicht zum Laden vorgeschlagen.
- **Nr. 10 bis 12 baltpeter/skr-json:** Das Repo behauptet, die GnuCash-Vorlagen seien nach einem Urteil des Kammergerichts Berlin von 1987 gemeinfrei. Das habe ich nicht rechtlich geprüft. Das LICENSE-Zitat stammt aus einer Zusammenfassung des Lesewerkzeugs, aber zwei Agenten geben es übereinstimmend wieder.
- **Nr. 6 bis 9, 15 bis 18, 22, 23 (GPL/AGPL-Repos):** GPL-Lizenzen schließen die interne Nutzung nicht aus. Sie sind aber Copyleft-Lizenzen, das ist für ein Testarchiv wohl unproblematisch, aber bei einer Weitergabe relevant.
- **Nr. 8 ERPNext „unverified":** Die Lizenz der Einzeldatei ist nicht geprüft. Die Repo-Lizenz ist vermutlich GPL-3.0, aber der Inhalt von `license.txt` wurde nicht gelesen.
- **Nr. 13 scka-de/german-accounting:** Die README erklärt MIT für „code and data", nennt aber als Datenquelle nur „DATEV docs, Steuerberater guidance, SKR documentation". Die Herkunft der Kontenbezeichnungen ist nicht belegt.
- **Nr. 1 bis 3 ledermann/datev:** MIT für das Repo. Ob die Beispieldateien ausdrücklich davon erfasst sind, ist nicht angegeben.
- **Alle 50 Kandidaten in `kandidaten.csv`:** Nutzungsbedingungen nicht gelesen. Drittkopien von DATEV-Mustern auf Steuerberaterseiten haben unklare Rechte.

## Abweichungen zwischen den Recherche-Agenten

- Bei Odoo hat ein Agent die Branches master/18.0/17.0 per Header verglichen (Größe 257.372 / 252.746 / 248.899 Byte für SKR03), ein anderer hat 17.0 inhaltlich gelesen. Das Inventar beschreibt 17.0. Master/18.0 können anders aufgebaut sein.
- Bei ERPNext gibt es zwei verschiedene SKR03-Dateien (`verified/de_kontenplan_SKR03.json` mit 15.181 Byte und `unverified/de_l10n_de_chart_template.json` mit 93.609 Byte). Beide stehen im Inventar (Nr. 6 und 8).
- Die Kodierung der EXTF-Beispiele wurde einmal als Windows-1252 angegeben, einmal als „nicht ermittelt". Das ist ungeprüft.
- Die Kontenzahl von skr03.json (baltpeter) ist grob geschätzt (100 bis 200+). Sie stammt aus einer Zusammenfassung des Lesewerkzeugs.
- Die Aufbau-Angaben zu Nr. 9, 13 und 18 stammen aus Kurzzusammenfassungen (README oder Repo-Seite), nicht aus dem Öffnen der Datei.

## Downloads

Es wurde nichts geladen, das Feld `sha256` in `inventar.csv` steht überall auf „nicht geladen". Ein Vorschlag zum Laden steht in der Antwort im Chat und wartet auf ein Ja.
