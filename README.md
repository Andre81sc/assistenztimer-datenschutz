# Datenschutzerklärung für AssistenzTimer

Stand: November 2026

## 1. Verantwortlicher

Andre Schmidt
Potsdamer Straße 3
59192 Bergkamen
E-Mail: entwickler@sternenwald.eu

## 2. Allgemeines

AssistenzTimer (im Folgenden „die App") ist eine iOS-Anwendung für Menschen, die ihre persönlichen Assistenzkräfte selbst beschäftigen (zum Beispiel im Rahmen eines Persönlichen Budgets). Mit der App werden Arbeitszeiten, Pausen und Tätigkeiten der Assistenzkräfte erfasst, daraus monatliche Tätigkeitsnachweise und Kostenabrechnungen als PDF erstellt und wahlweise in der Dateien-App (Standard) oder auf einem vom Nutzer selbst konfigurierten WebDAV-Server abgelegt.

Die App speichert keine personenbezogenen Daten auf Servern des Entwicklers. Alle Daten werden ausschließlich lokal auf dem Gerät des Nutzers, in dem in der Dateien-App gewählten Ordner oder auf dem vom Nutzer konfigurierten WebDAV-Server abgelegt. Welcher Server das ist (beispielsweise eine eigene Synology- oder QNAP-NAS, eine Nextcloud-Instanz, ein Cloud-Anbieter mit WebDAV-Endpunkt wie Strato HiDrive, Magenta Cloud oder mailbox.org), entscheidet ausschließlich der Nutzer. Wahl und Betrieb dieses Servers liegen vollständig in seiner Verantwortung.

Der Entwickler erhält nur dann personenbezogene Daten, wenn ihm jemand von sich aus eine E-Mail schreibt. Was dabei geschieht, steht in Abschnitt 7.

## 3. Verarbeitete Daten

### Lokal auf dem Gerät

- Die WebDAV-Serveradresse, der Benutzername und das Passwort. Das Passwort wird verschlüsselt im iOS-Schlüsselbund abgelegt (`kSecAttrAccessibleAfterFirstUnlockThisDeviceOnly`) und nicht in iCloud-Backups synchronisiert.
- Optional je Assistenzkraft eine gespeicherte Unterschrift als Bild. Sie wird ausschließlich verschlüsselt im iOS-Schlüsselbund des Geräts abgelegt (`kSecAttrAccessibleAfterFirstUnlockThisDeviceOnly`), nicht über iCloud synchronisiert und nicht auf andere Geräte übertragen; auch in den JSON-Sicherungen auf dem WebDAV-Server ist sie nicht enthalten. Die Unterschrift kann in der Kontaktkarte jederzeit neu erfasst oder gelöscht werden; beim Löschen der Assistenzkraft wird sie automatisch mit entfernt.
- Die Liste der angelegten Assistenzkräfte mit ihren Kontaktkarten (Namen, Telefonnummern, E-Mail-Adressen, Anschriften und Stundenlohn-Angaben, soweit vom Nutzer eingetragen).
- Daten zum Arbeitgeber (Name und Adresse, die im Kopf der erstellten PDF-Dokumente erscheinen).
- Erfasste Schichten: Ankunfts- und Abreisezeiten, Pausen, freitextliche Tätigkeitsbeschreibungen.
- Konfigurationseinstellungen und Schalter-Zustände (z.B. ob Push-Mitteilungen aktiviert sind, ob Sprachausgaben erfolgen sollen).
- Eine Liste der bereits über die Hintergrundaktualisierung gesehenen Beanstandungen und unterschriebenen Tätigkeitsnachweise.

Diese Daten werden ausschließlich lokal auf dem Gerät gespeichert. Sie werden weder an den Entwickler noch an Dritte übermittelt.

### In der Dateien-App (Standard-Speicherort)

- Ohne weitere Einrichtung legt die App die erzeugten PDF-Dokumente im eigenen App-Ordner ab, der in der Dateien-App unter „Auf meinem iPhone“ → „AssistenzTimer“ sichtbar ist, sortiert nach Assistenzkraft, Art und Jahr.
- Alternativ kann der Nutzer in den Einstellungen einen eigenen Ordner in der Dateien-App wählen. Liegt dieser Ordner bei einem Cloud-Anbieter (zum Beispiel iCloud Drive), gelten für die dort abgelegten Dateien die Bestimmungen dieses Anbieters. Die App merkt sich nur die Zugriffsberechtigung auf den gewählten Ordner.
- Ist der gewählte Ordner vorübergehend nicht erreichbar, wird das PDF auf dem Gerät vorgemerkt und automatisch nachgeschickt, sobald der Ordner wieder verfügbar ist.

### Auf dem WebDAV-Server des Nutzers (optional)

- Die erzeugten Tätigkeitsnachweise und Kostenabrechnungen als PDF — eingegliedert in eine Ordnerstruktur pro Assistenzkraft und Monat. Liegt für eine Assistenzkraft eine gespeicherte Unterschrift vor oder wurde ein Nachweis direkt in der App unterschrieben, enthält das abgelegte PDF diese Unterschrift als Bild.
- Optionale JSON-Sicherungspakete, die die App regelmäßig nach Änderungen anlegt (Mitarbeiterliste, Zeit-Einträge, Mitarbeiter-Einstellungen, Kontaktkarten, App-Einstellungen einschließlich Name und Adresse des Arbeitgebers sowie die Vermerke, welche Schichten bereits abgerechnet sind). Es wird eine begrenzte Anzahl von Sicherungen rotierend behalten; ist die Grenze erreicht, wird die jeweils älteste automatisch gelöscht.
- Kurze TXT-Notizen, mit denen Beanstandungen aus der Begleit-App „AT Postfach" als erledigt markiert werden.

Die Verbindung zum WebDAV-Server erfolgt ausschließlich verschlüsselt über HTTPS; unverschlüsselte Adressen lehnt die App ab.

Die App stellt keine Verbindung zu Servern des Entwicklers oder zu Drittanbietern her, sondern ausschließlich zu Apple-System-Diensten und zum vom Nutzer konfigurierten WebDAV-Server. Der Link „Datenschutzerklärung“ in der App öffnet lediglich diese Seite im Browser. Die Seite liegt bei GitHub; beim Aufruf verarbeitet GitHub wie jeder Webserver technische Zugriffsdaten (zum Beispiel die IP-Adresse) nach seinen eigenen Datenschutzbestimmungen. Die App selbst überträgt dabei keine Daten.

## 4. Verarbeitung durch Apple-Systeme

Die App nutzt einige in iOS eingebaute Systemdienste, die ihrerseits den Apple-Datenschutzbestimmungen unterliegen:

**Apple Foundation Models / Apple Intelligence:** Auf Geräten mit Apple Intelligence kann die App die eingegebene Tätigkeitsbeschreibung zu kompakten Stichworten zusammenfassen. Die Verarbeitung erfolgt vollständig auf dem Gerät. Es findet kein Aufruf an Apple-Server statt; der Text der Tätigkeitsbeschreibung verlässt das Gerät nicht.

**Sprachausgabe (AVSpeechSynthesizer):** Optionale Sprachansagen (Ankunft/Abreise, Beanstandungs-Hinweise) werden lokal vom iOS-System-Sprachsynthesizer erzeugt. Es erfolgt kein Aufruf an Apple- oder Drittserver.

**Siri und Kurzbefehle (App Intents):** Die App bietet Kurzbefehle an, etwa „Ankunft speichern für … in AssistenzTimer“. Wer sie per Siri, Action Button oder Kurzbefehle-App nutzt, dessen Spracheingabe verarbeitet Apple nach den Siri-Bestimmungen. Die App erhält davon nur den erkannten Befehl (zum Beispiel, für welche Assistenzkraft eine Zeit gespeichert werden soll) und speichert ihn wie eine Eingabe in der App. An den Entwickler wird nichts übermittelt.

**System-Diktat (Tastatur):** Wenn der Nutzer die Mikrofon-Taste der iOS-Tastatur verwendet, läuft die Spracherkennung — abhängig von Modell und iOS-Einstellungen — auf modernen iPhones lokal auf dem Gerät. Welcher Modus aktiv ist, regelt iOS in den System-Einstellungen.

## 5. Apple-Berechtigungen

Die App fordert nur Berechtigungen an, die für den jeweiligen Funktionsumfang notwendig sind:

**Hintergrundaktualisierung (Background App Refresh):** prüft periodisch, ob auf dem WebDAV-Server neue Beanstandungen oder neu unterschriebene Tätigkeitsnachweise eingetroffen sind, und löst gegebenenfalls eine lokale Benachrichtigung aus.

**Mitteilungen (Local Notifications):** informieren über neue Beanstandungen und neu eingetroffene unterschriebene Tätigkeitsnachweise. Push-Mitteilungen werden lokal auf dem Gerät erzeugt — es werden keine Push-Nachrichten über Apples Push-Notification-Server verschickt.

Es wird keine Telemetrie, keine Analyse-Software und kein Tracking eingesetzt.

## 6. TestFlight (während der Beta-Phase)

Wer die App über Apples TestFlight-Programm installiert, akzeptiert die Datenverarbeitung durch Apple im Rahmen von TestFlight. Dazu zählen unter anderem anonymisierte Absturzberichte und Nutzungsmetriken, die direkt an Apple gehen und dem Entwickler in App Store Connect angezeigt werden. Details regelt die Apple-Datenschutzerklärung.

## 7. Kontakt per E-Mail

Die App selbst verschickt keine E-Mails. Wer dem Entwickler eine E-Mail schreibt, übermittelt seine E-Mail-Adresse, den Namen, soweit er im Mailprogramm eingestellt ist, und den Inhalt der Nachricht. Diese Angaben werden nur genutzt, um die Nachricht zu beantworten und die App zu verbessern. Sie werden nicht an andere weitergegeben und spätestens ein Jahr nach Eingang gelöscht. Rechtsgrundlage ist das berechtigte Interesse, Anfragen und Rückmeldungen zu beantworten und die App zu verbessern (Art. 6 Abs. 1 lit. f DSGVO).

Der Entwickler betreibt für entwickler@sternenwald.eu einen eigenen Mailserver. Für den Versand nutzt er den Dienst SMTP2GO, als Ersatz-Mailserver Strato. Diese Dienstleister verarbeiten die E-Mails nur in seinem Auftrag.

## 8. Weitergabe an Dritte

Die App gibt keine personenbezogenen Daten an Dritte weiter. Auch der Entwickler gibt keine personenbezogenen Daten an Dritte weiter. Die einzige Ausnahme sind die in Abschnitt 7 genannten Dienstleister, die beim Kontakt per E-Mail am Transport der Nachrichten beteiligt sind. Daten, die der Nutzer auf seinem eigenen WebDAV-Server ablegt, unterliegen ausschließlich seiner Verfügungsgewalt.

## 9. Rechte der Betroffenen

**Daten in der App:** Über die App erhält der Entwickler keine personenbezogenen Daten. Er kann deshalb zu Daten, die in der App, in der Dateien-App oder auf dem WebDAV-Server des Nutzers liegen, weder Auskunft geben noch sie berichtigen oder löschen. Für diese Daten ist der Nutzer selbst Verantwortlicher im Sinne der DSGVO. Assistenzkräfte, deren Daten in der App erfasst sind, wenden sich mit ihren Anliegen an ihren Arbeitgeber, der die App nutzt.

**Daten aus dem Kontakt per E-Mail:** Wer dem Entwickler eine E-Mail geschrieben hat, dessen Daten verarbeitet der Entwickler wie in Abschnitt 7 beschrieben. Diese Personen haben gegenüber dem Entwickler das Recht auf Auskunft, Berichtigung, Löschung, Einschränkung der Verarbeitung und Datenübertragbarkeit sowie das Recht, der Verarbeitung zu widersprechen (Art. 15 bis 21 DSGVO). Eine formlose E-Mail an entwickler@sternenwald.eu genügt.

Außerdem besteht das Recht, sich bei einer Datenschutz-Aufsichtsbehörde zu beschweren, zum Beispiel bei der Landesbeauftragten für Datenschutz und Informationsfreiheit Nordrhein-Westfalen.

## 10. Kontakt

Bei Fragen zur Datenschutzerklärung oder zur App selbst: entwickler@sternenwald.eu

Was mit einer solchen E-Mail geschieht, steht in Abschnitt 7.

## Support

Fragen, Probleme oder Anregungen zur App AssistenzTimer? Schreib einfach eine E-Mail an **entwickler@sternenwald.eu** — du bekommst so schnell wie möglich eine Antwort, in der Regel innerhalb weniger Tage.
