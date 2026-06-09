# Datenschutzerklärung für AssistenzTimer

Stand: 8. Juni 2026

## 1. Verantwortlicher

Andre Schmidt
Potsdamer Straße 3
59192 Bergkamen
E-Mail: andre.schmidt.be@icloud.com

## 2. Allgemeines

AssistenzTimer (im Folgenden „die App") ist eine iOS-Anwendung für Menschen, die ihre persönlichen Assistenzkräfte selbst beschäftigen (zum Beispiel im Rahmen eines Persönlichen Budgets). Mit der App werden Arbeitszeiten, Pausen und Tätigkeiten der Assistenzkräfte erfasst, daraus monatliche Tätigkeitsnachweise und Kostenabrechnungen als PDF erstellt und auf einem vom Nutzer selbst konfigurierten WebDAV-Server abgelegt.

Die App speichert keine personenbezogenen Daten auf Servern des Entwicklers. Alle Daten werden ausschließlich lokal auf dem Gerät des Nutzers und auf dem vom Nutzer konfigurierten WebDAV-Server abgelegt. Welcher Server das ist (beispielsweise eine eigene Synology- oder QNAP-NAS, eine Nextcloud-Instanz, ein Cloud-Anbieter mit WebDAV-Endpunkt wie Strato HiDrive, Magenta Cloud oder mailbox.org), entscheidet ausschließlich der Nutzer. Wahl und Betrieb dieses Servers liegen vollständig in seiner Verantwortung.

## 3. Verarbeitete Daten

### Lokal auf dem Gerät

- Die WebDAV-Serveradresse, der Benutzername und das Passwort. Das Passwort wird verschlüsselt im iOS-Schlüsselbund abgelegt (`kSecAttrAccessibleAfterFirstUnlockThisDeviceOnly`) und nicht in iCloud-Backups synchronisiert.
- Die Liste der angelegten Assistenzkräfte (Vornamen, Telefonnummern, E-Mail-Adressen, Stundenlohn-Angaben und Kontaktkarten-Details, soweit vom Nutzer eingetragen).
- Daten zum Arbeitgeber (Name und Adresse, die im Kopf der erstellten PDF-Dokumente erscheinen).
- Erfasste Schichten: Ankunfts- und Abreisezeiten, Pausen, freitextliche Tätigkeitsbeschreibungen.
- Konfigurationseinstellungen und Schalter-Zustände (z.B. ob Push-Mitteilungen aktiviert sind, ob Sprachausgaben erfolgen sollen).
- Eine Liste der bereits über die Hintergrundaktualisierung gesehenen Beanstandungen und unterschriebenen Tätigkeitsnachweise.

Diese Daten werden ausschließlich lokal auf dem Gerät gespeichert. Sie werden weder an den Entwickler noch an Dritte übermittelt.

### Auf dem WebDAV-Server des Nutzers

- Die erzeugten Tätigkeitsnachweise und Kostenabrechnungen als PDF — eingegliedert in eine Ordnerstruktur pro Assistenzkraft und Monat.
- Optionale JSON-Sicherungspakete, die die App regelmäßig nach Änderungen anlegt (Mitarbeiterliste, Zeit-Einträge, Mitarbeiter-Einstellungen, Kontaktkarten). Es werden bis zu 20 Sicherungen rotierend behalten.
- Kurze TXT-Notizen, mit denen Beanstandungen aus der Begleit-App „AT Postfach" als erledigt markiert werden.

Die App stellt keine Verbindung zu Servern des Entwicklers oder zu Drittanbietern her, sondern ausschließlich zu Apple-System-Diensten und zum vom Nutzer konfigurierten WebDAV-Server.

## 4. Verarbeitung durch Apple-Systeme

Die App nutzt einige in iOS eingebaute Systemdienste, die ihrerseits den Apple-Datenschutzbestimmungen unterliegen:

**Apple Foundation Models / Apple Intelligence:** Auf Geräten mit Apple Intelligence kann die App die eingegebene Tätigkeitsbeschreibung zu kompakten Stichworten zusammenfassen. Die Verarbeitung erfolgt vollständig auf dem Gerät. Es findet kein Aufruf an Apple-Server statt; der Text der Tätigkeitsbeschreibung verlässt das Gerät nicht.

**Sprachausgabe (AVSpeechSynthesizer):** Optionale Sprachansagen (Ankunft/Abreise, Beanstandungs-Hinweise) werden lokal vom iOS-System-Sprachsynthesizer erzeugt. Es erfolgt kein Aufruf an Apple- oder Drittserver.

**System-Diktat (Tastatur):** Wenn der Nutzer die Mikrofon-Taste der iOS-Tastatur verwendet, läuft die Spracherkennung — abhängig von Modell und iOS-Einstellungen — auf modernen iPhones lokal auf dem Gerät. Welcher Modus aktiv ist, regelt iOS in den System-Einstellungen.

## 5. Apple-Berechtigungen

Die App fordert nur Berechtigungen an, die für den jeweiligen Funktionsumfang notwendig sind:

**Hintergrundaktualisierung (Background App Refresh):** prüft periodisch, ob auf dem WebDAV-Server neue Beanstandungen oder neu unterschriebene Tätigkeitsnachweise eingetroffen sind, und löst gegebenenfalls eine lokale Benachrichtigung aus.

**Mitteilungen (Local Notifications):** informieren über neue Beanstandungen und neu eingetroffene unterschriebene Tätigkeitsnachweise. Push-Mitteilungen werden lokal auf dem Gerät erzeugt — es werden keine Push-Nachrichten über Apples Push-Notification-Server verschickt.

Es wird keine Telemetrie, keine Analyse-Software und kein Tracking eingesetzt.

## 6. TestFlight (während der Beta-Phase)

Wer die App über Apples TestFlight-Programm installiert, akzeptiert die Datenverarbeitung durch Apple im Rahmen von TestFlight. Dazu zählen unter anderem anonymisierte Absturzberichte und Nutzungsmetriken, die direkt an Apple gehen und dem Entwickler in App Store Connect angezeigt werden. Details regelt die Apple-Datenschutzerklärung.

## 7. Weitergabe an Dritte

Es findet keine Weitergabe personenbezogener Daten an Dritte statt — weder durch den Entwickler noch durch die App. Daten, die der Nutzer auf seinem eigenen WebDAV-Server ablegt, unterliegen ausschließlich seiner Verfügungsgewalt.

## 8. Rechte der Betroffenen

Da der Entwickler keine personenbezogenen Daten verarbeitet, sind Auskunfts-, Lösch- und Berichtigungsansprüche gegenüber dem Entwickler gegenstandslos. Für Daten auf dem eigenen WebDAV-Server ist der Nutzer selbst Verantwortlicher im Sinne der DSGVO.

## 9. Kontakt

Bei Fragen zur Datenschutzerklärung oder zur App selbst: andre.schmidt.be@icloud.com
