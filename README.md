# creative_quiz
20230944 김민성 창의공학 퀴즈시험<br/>
1번<br/>
void setup(){
  pinMode(3, OUTPUT);
}

void loop(){
  digitalWrite(3, HIGH);
  delay(250);<br/>
  digitalWrite(3, LOW);
  delay(250);
}

2번=====================================================<br/>
void setup(){
  pinMode(13, OUTPUT);
  pinMode(7, INPUT_PULLUP);
}

void loop(){<br/>
  int sw=digitalRead(7);  

  if(sw==HIGH){<br/>           
    digitalWrite(13, LOW);   
  }
  else      
  {
    digitalWrite(13, HIGH);
  }
}

3번=========================================================<br/>
아두이노=====================================<br/>
void setup(){
  Serial.begin(9600);
  pinMode(13, OUTPUT);
  pinMode(7, INPUT_PULLUP);
}

void loop(){
  int sw=digitalRead(7);
  Serial.println(sw);
  delay(500);    
}

프로세싱=====================================<br/>
import processing.serial.*;
Serial p;

void setup(){
  size(400,400);
  p = new Serial(this,"COM4", 9600);
}

void draw(){
  if(p.available()>0){
    String m = p.readStringUntil('\n');
    
    if(m != null){
    
       print(m);
       
       if(m.indexOf('1')==0) background(0,0,255);
       
       if(m.indexOf('0')==0) background(255,0,0);
    }
  }
}

4번==================================================================================<br/>
아두이노================================<br/>
void setup() {
  Serial.begin(9600);
}

void loop(){
  char m = Serial.read();
    Serial.println(m);

  if(m == '5') tone(4,523,500);
}

프로세싱===========================<br/>
import processing.serial.*;
Serial p;

void setup(){
  p = new Serial(this, "COM4", 9600);
}

void draw(){}

void keyPressed(){
  background(0);
  textSize(64);
  text(key, 10, 64);
  p.write(key);
}
