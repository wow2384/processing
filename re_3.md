```
PFont f;
void setup() {
  size(640, 360);
  rectMode(CENTER);
  background(102);
  textSize(72);
  f= createFont("굴림", 30);
  textFont(f);
}
int a;
float ro;
void draw() {
  fill(255);
  text("0을 누르면 원 1을 누르면 사각형이 나옵니다\n3을 누르면 지워집니다.",10,180);
  if(a=='0'){
    fill(random(0,255),random(0,255),random(0,255));
    variableEllipse(mouseX, mouseY, pmouseX, pmouseY);
  }
  if(a=='1'){

    fill(random(0,255),random(0,255),random(0,255));
    variableRect(mouseX,mouseY,pmouseX,pmouseY);
  }
  if(a=='3'){
    background(102);
    text("지워졌습니다",250,180);
  }
 }

void keyPressed(){
  a = key;
}

void variableRect(int x, int y, int px, int py){
  float speed = abs(x-px) + abs(y-py);
  stroke(speed);
  rect(x,y,speed,speed);
}

void variableEllipse(int x, int y, int px, int py) {
  float speed = abs(x-px) + abs(y-py);
  stroke(speed);
  ellipse(x, y, speed, speed);
}
```
