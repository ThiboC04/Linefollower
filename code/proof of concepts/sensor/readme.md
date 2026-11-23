<img width="1408" height="1117" alt="image" src="https://github.com/user-attachments/assets/9edd12d1-9bf9-48ae-ae35-3c677603832c" /># Sensoren proof of concept

minimale hard- en software die aantoont dat minimaal 6 sensoren onafhankelijk van elkaar kunnen uitgelezen worden (geen calibratie, normalisatie of interpolatie). Hierbij moet een zo groot mogelijk bereik van de AD converter benut worden (indien van toepassing)

<img width="1780" height="1260" alt="image" src="https://github.com/user-attachments/assets/e4da8e66-869e-4f87-8789-34fbfde0dd72" />

<img width="2160" height="2880" alt="IMG_6648" src="https://github.com/user-attachments/assets/5edb2de9-4f37-442e-80c6-38d98d23b0ec" />

<img width="1408" height="1117" alt="b71ac98e-0c16-4adb-84e9-1cde5b0177b4" src="https://github.com/user-attachments/assets/19ee2b89-6048-4e12-88dd-a2740958eba5" />



code :

/*
  Sensor Proof of Concept - QTR-8A
  Arduino UNO R4 WiFi
*/

const int sensorPins[6] = {
  A0, A1, A2, A3, A4, A5
};

int sensorValues[6];

void setup() {
  Serial.begin(115200);
  delay(1000);

  // Maximale 14-bit ADC-resolutie
  analogReadResolution(14);

  for (int i = 0; i < 6; i++) {
    pinMode(sensorPins[i], INPUT);
  }

  Serial.println("QTR-8A SENSOR TEST");
  Serial.println("S1\tS2\tS3\tS4\tS5\tS6");
}

void loop() {
  // Sensoren afzonderlijk uitlezen
  for (int i = 0; i < 6; i++) {
    sensorValues[i] = analogRead(sensorPins[i]);
  }

  // Meetwaarden weergeven
  for (int i = 0; i < 6; i++) {
    Serial.print(sensorValues[i]);

    if (i < 5) {
      Serial.print('\t');
    }
  }

  Serial.println();

  delay(250);
}
