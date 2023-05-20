# Larson_Scanner

//Link to Circuit__ https://www.tinkercad.com/things/aicqwHyALNE-frantic-vihelmo/editel

//This is the program and circuit for Larson Scanner on Arduino UNO
//Code:
int led[] = {12,11,10,9,8,7,6,5};
int c = 0;
int T= 50;

void setup() {
  for (c = 0; c < 8; c++) {
    pinMode(led[c], OUTPUT);
  }
}
void loop() {
  for (c = 0; c < 8; c++) {
    digitalWrite(led[c], HIGH);
    delay(T);
    digitalWrite(led[c+1], HIGH);
    delay(T);
    digitalWrite(led[c], LOW);
    delay(analogRead(0) / 8);
  }
  for (c=8; c>0; c--) {
    digitalWrite(led[c], HIGH);
    delay(T);
    digitalWrite(led[c - 1], HIGH);
    delay(T);
    digitalWrite(led[c], LOW);
    delay(analogRead(0) / 8);
  }
}
