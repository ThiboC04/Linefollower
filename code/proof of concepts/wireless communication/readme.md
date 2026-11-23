# Draadloze communicatie – Proof of Concept

## Doel

Aantonen dat er bidirectionele (duplex) communicatie mogelijk is tussen de Arduino UNO R4 WiFi en een laptop of smartphone via een draadloze WiFi-verbinding.

De communicatie maakt het mogelijk om gegevens van de microcontroller te ontvangen en tegelijkertijd commando's en instellingen naar de microcontroller te versturen.

## Configuratie

- **Microcontroller:** Arduino UNO R4 WiFi
- **Draadloze communicatie:** WiFi
- **Communicatiemethode:** WiFi Access Point en HTTP
- **SSID:** LineFollowerTC
- **Wachtwoord:** Robot1234
- **Communicatieprotocol:** HTTP
- **Poort:** 80
- **Bediening:** Webbrowser op laptop of smartphone
- **Programma:** Arduino IDE en een webbrowser

De Arduino maakt zelf een WiFi-netwerk aan waarop een laptop of smartphone kan aansluiten.

## Opmerkingen

De communicatie verloopt in twee richtingen:

**Microcontroller naar laptop/smartphone:**
- Live meetwaarden van de zes lijnsensoren versturen.
- Status van de robot doorgeven.
- Actuele PID-instellingen en motorsnelheid doorgeven.

**Laptop/smartphone naar microcontroller:**
- Start- en stopcommando's versturen.
- PID-parameters (Kp, Ki en Kd) aanpassen.
- Basissnelheid van de motoren aanpassen.
- Cyclustijd aanpassen.

De gegevens worden via HTTP-verzoeken uitgewisseld. De sensorwaarden worden in JSON-formaat doorgestuurd.

## Gebruiksaanwijzing

1. Verbind de Arduino UNO R4 WiFi met de computer via USB.
2. Upload de Arduino-code via Arduino IDE.
3. Open de Serial Monitor op 115200 baud.
4. Wacht tot het WiFi-netwerk is opgestart.
5. Verbind de laptop of smartphone met het WiFi-netwerk `LineFollowerTC`.
6. Gebruik het wachtwoord `Robot1234`.
7. Zoek het IP-adres dat in de Serial Monitor wordt weergegeven.
8. Open een webbrowser en voer het weergegeven IP-adres in.
9. Het Line Follower-dashboard wordt geopend.

Via het dashboard kunnen de sensorwaarden live worden bekeken en kunnen de robot en zijn parameters draadloos worden bediend.
