#include <LiquidCrystal.h>

LiquidCrystal lcd(3,4,5,6,7,8);

// Ultrasonic Sensor Pins
const int trigPin = A0;
const int echoPin = A1;

long duration;
float distance;

void setup() {
  lcd.begin(16, 2);

  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);

  lcd.setCursor(0, 0);
  lcd.print("Ultrasonic");
  lcd.setCursor(0, 1);
  lcd.print("Distance Meter");
  delay(2000);

  lcd.clear();
}

void loop() {
  // Send ultrasonic pulse
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);

  digitalWrite(trigPin, LOW);

  // Read echo
  duration = pulseIn(echoPin, HIGH);

  // Calculate distance in cm
  distance = duration * 0.0343 / 2;

  // Display on LCD
  lcd.clear();
  lcd.setCursor(0, 0);
  lcd.print("Distance:");

  lcd.setCursor(0, 1);
  lcd.print(distance);
  lcd.print(" cm");

  delay(500);
}
