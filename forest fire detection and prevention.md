#include <DHT.h>
#include <Servo.h>

// Define pins
#define FLAME_SENSOR_PIN A0
#define RELAY_PIN 8
#define DHT_PIN 2
#define DHT_TYPE DHT11
#define SERVO_PIN 9

// Initialize the DHT sensor
DHT dht(DHT_PIN, DHT_TYPE);

// Initialize the Servo
Servo myServo;

// Define temperature threshold for fire detection
const float TEMPERATURE_THRESHOLD = 50.0; // Adjust based on your requirement

void setup() {
  // Start serial communication for debugging purposes
  Serial.begin(9600);

  // Initialize the DHT sensor
  dht.begin();

  // Initialize the Servo
  myServo.attach(SERVO_PIN);
  myServo.write(0); // Set initial position

  // Set relay pin as output
  pinMode(RELAY_PIN, OUTPUT);

  // Set flame sensor pin as input
  pinMode(FLAME_SENSOR_PIN, INPUT);

  // Initialize relay to off
  digitalWrite(RELAY_PIN, LOW);
}

void loop() {
  // Read temperature and humidity from DHT11
  float temperature = dht.readTemperature();
  float humidity = dht.readHumidity();

  // Check if any reads failed and exit early (to try again).
  if (isnan(temperature) || isnan(humidity)) {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

  // Print sensor values to the serial monitor
  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" *C");
  Serial.print("Humidity: ");
  Serial.print(humidity);
  Serial.println(" %");

  // Check if temperature exceeds the threshold
  if (temperature > TEMPERATURE_THRESHOLD) {
    Serial.println("Temperature threshold exceeded! Checking flame sensor...");

    // Read flame sensor value
    int flameValue = analogRead(FLAME_SENSOR_PIN);
    Serial.print("Flame sensor value: ");
    Serial.println(flameValue);

    // Check for fire detection by flame sensor
    if (flameValue < 500) {
      // Fire detected, activate relay (which turns on the water pump) and servo motor
      digitalWrite(RELAY_PIN, HIGH);
      myServo.write(90); // Adjust the servo position as needed
      Serial.println("Fire detected! Activating water pump and servo motor...");
    } else {
      // No fire detected by flame sensor, deactivate relay and reset servo
      digitalWrite(RELAY_PIN, LOW);
      myServo.write(0);
      Serial.println("No fire detected by flame sensor.");
    }
  } else {
    // Temperature threshold not exceeded, deactivate relay and reset servo
    digitalWrite(RELAY_PIN, LOW);
    myServo.write(0);
    Serial.println("Temperature threshold not exceeded.");
  }

  // Wait for a second before repeating the loop
  delay(1000);
}

