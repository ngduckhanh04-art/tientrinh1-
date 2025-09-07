

const int led1 = 8;  // LED đầu tiên gắn chân số 8
const int led2 = 9;  // LED thứ hai gắn chân số 9

void setup() {
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
}

void loop() {
  digitalWrite(led1, HIGH);
  digitalWrite(led2, HIGH);
  delay(1000);  // Delay 1 giây

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  delay(1000);  // Delay 1 giây
}
