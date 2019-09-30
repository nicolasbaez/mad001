#: : m a d 0 0 1

![mad005](https://github.com/nicolasbaez/mad005/blob/master/mad005.gif)

```processing
float x;
float y;
float r; //radius
float w; //width
float dAngle; //angle
float j=0; //start
void setup() {
  size(512, 256);
  background(255);
  noStroke();
  fill(0);
}
void draw() {
  background(255);
  translate(width/2, height/2);
  dAngle=map(sin(radians(j)), -1, 1, 32, 4);
  w=map(cos(radians(j)), -1, 1, 2, 8);
  r=map(sin(radians(j))+cos(radians(j)), -1, 1, height*0.125, height*0.4);
  for (float i=j; i<=j+360; i+=dAngle) {
    x=r*cos(radians(i));
    y=r*sin(radians(i));
    rect(x-w/2, y-w/2, w, w);
  }
  j++;
  if (j<=360) {
    saveFrame("gif/mad005-######.png");
  }
}
```
