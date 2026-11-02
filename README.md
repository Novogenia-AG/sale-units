# Sale Units

Werkzeug, um aus den Artikeln und Stücklisten aus Business Central kaufbare
Einheiten zusammenzustellen: links der Katalog, in der Mitte die Konfiguration,
rechts die Karte so, wie der Endkunde sie sieht.

Der Katalog in `index.html` liegt **verschlüsselt** in der Seite
(AES-256-GCM, Schlüssel per PBKDF2-SHA256 mit 8 Mio Iterationen). Ohne Passwort
ist kein einziger Produktcode lesbar, auch nicht im Quelltext.

Live: https://novogenia-ag.github.io/sale-units/

Gebaut wird die Datei mit `bau_krypto.py` (Passwort über stdin); die
Gegenprobe im Skript bricht ab, sobald Klartext aus dem Katalog in der Datei
landet — diese Prüfung nie entfernen.
