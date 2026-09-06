// Adapted for ESP32 Dev Module
// Original logic: YouTube | Tech at Home

byte ldr_sensor = 34;   // digital output pin from LDR comparator module
byte buzzer = 15;       // avoid strapping pins (0, 2, 12, 15 need care - 15 is fine if not pulled low at boot)
byte x = 0;

void setup()
{
  pinMode(ldr_sensor, INPUT);
  pinMode(buzzer, OUTPUT);
  Serial.begin(115200);   // helpful for debugging
}

void loop()
{
  int sensor_data = digitalRead(ldr_sensor);
  Serial.println(sensor_data);   // watch this in Serial Monitor to confirm HIGH/LOW toggling correctly

  if (sensor_data == LOW && x == 0)
  {
    digitalWrite(buzzer, LOW);
  }
  else
  {
    analogWrite(buzzer, 200);
    delay(110);
    analogWrite(buzzer, 100);
    delay(110);
    x = 1;
  }
}
