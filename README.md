# Aduino
* 조도센서의 밝기(조도)가 130을 넘을 경우 하늘색을 띄며 130을 안넘을 경우에는 노란색을 띄도록 했습니다. 
아두이노에 대해서 조금씩 알아가고 있는것이 너무 행복하며 아까 수업시간에 제가 할것을 다하고 휴대폰을 만지는 행위는 잘못되었던거 같습니다. 다음부터 주위를 둘러보며 못따라오는 학우가 있다면 따라오게 도와주도록 열심히 하겠습니다. 아두이노를 배워 행복한거 같습니다.
* 아두이노 코드 
void setup() {
  Serial.begin(9600);
}
int a;
void loop() {
  a = analogRead(A0);
  Serial.println(++a);
  delay(500);
}

* 프로세싱 코드
import processing.serial.*;
Serial p;
void setup(){
  size(300,300);
  p=new Serial(this, "COM4",9600);
}
void draw(){
  if(p.available()>0){
    String m=p.readString();
    int a = int(m.trim());
    println(a);
    if(a>130) fill(0,255,255);
    else      fill(255,255,0);
    ellipse(150,150, 150, 150);
  }
}
