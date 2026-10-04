# Firebase einrichten

Das Spiel meldet Spieler automatisch anonym an. Eine Registrierung ist nicht nötig.

1. In Firebase unter **Authentication → Sign-in method** den Anbieter **Anonymous** aktivieren.
2. Warten, bis die aktualisierte GitHub-Pages-Seite den neuen Spielcode verwendet. Neue Raumcodes haben acht Zeichen.
3. Den gesamten Inhalt von `database.rules.json` kopieren.
4. In Firebase unter **Realtime Database → Rules** den bisherigen Inhalt vollständig ersetzen und **Publish** auswählen.
5. Alle Spieler laden die Spielseite neu. Der Gastgeber erstellt einen neuen Raum und teilt den neuen Code.

Alte Spielräume verwenden Spielernamen als Identität und sind mit den neuen Regeln nicht kompatibel. Anonyme Identitäten werden im jeweiligen Browser gespeichert; ein anderer Browser oder gelöschte Browserdaten erzeugen eine neue Identität.

## Zugriff

Die gesamte Datenbank und die Liste aller Räume sind für Spielclients gesperrt. Wer einen Raumcode kennt und anonym angemeldet ist, kann vor Beginn der ersten Runde mitspielen. Der Raumcode ist daher eine Einladung und sollte nur an Mitspieler weitergegeben werden. Nach Beginn dürfen nur bereits eingetragene Spieler wieder beitreten.

Spieler können ihre eigenen Antworten einmalig nach STOP einreichen und ihre eigenen Reaktionen setzen. Nur der Gastgeber kann Rezensionen, Ergebnisse und Gesamtpunkte schreiben. Der ausgewählte Spieler darf den Buchstaben wählen; alle Raumteilnehmer dürfen STOP drücken. Der Gastgeber ist für die Wertung vertrauenswürdig und kann die Punkte des eigenen Raums verwalten.

Die Regeln verhindern den bisherigen uneingeschränkten Datenbankzugriff. Sie ersetzen keine Maßnahmen gegen massenhafte anonyme Anmeldungen oder Raum-Erstellung; für ein öffentliches Spiel mit größerer Nutzung sind zusätzlich App Check, Quotenüberwachung und gegebenenfalls serverseitige Begrenzungen sinnvoll.

Eine Änderung dieser Datei oder der Regeln auf GitHub allein veröffentlicht keine Regeln in Firebase.
