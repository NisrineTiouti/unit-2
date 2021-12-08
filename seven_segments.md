## Seven Segments:

![Copy of Seven segment](https://user-images.githubusercontent.com/89052189/144089422-695bb755-0ec2-4fa0-b965-96597020940c.png)

```.c
int portA = 2;
int portB = 3;
int portC = 7;
int portD = 6;
int portE = 5 ;
int portF = 4;
int portG = 8;

void setup()
{ 
  
  pinMode(portA, OUTPUT);
  pinMode(portB, OUTPUT);
  pinMode(portC, OUTPUT);
  pinMode(portD, OUTPUT);
  pinMode(portE, OUTPUT);
  pinMode(portF, OUTPUT);
  pinMode(portG, OUTPUT);
}

void loop()
{
 // Let's define our inputs for now like this  
  bool X = false;
  bool Y = false;
  bool Z = true; 
  bool W = false; 
    
  // From the slide A = notX W + YZ + YnotWnotZ + XnotWZ + WnotZnotY + notXnotYnotZ
  // not = !, and = &&, or = ||
  int A = (!X && W) || (Y && Z) ||(Y && !W && !Z) || (X && !W && Z) || (W && !Z && !Y) || (!X && !Y && !Z); 
  digitalWrite(portA, A);
  
  // B = notY notZ + notZ y  notX+ Z  notY notX + notW  Y  X+ W notY  X

  int B = (!Y && !Z) || (!Z && Y && !X) || (Z && !Y && !X) || (!W && Y && X) || (W && !Y && X);
  digitalWrite(portB, B);
  
  // C = NotY NotX NotW + X NotY NotW + W X NotY + W NotZ NotX + Y W NotZ + Y Z  Not W+ YX NotW
  int C = (!Y && !X && !W) || (X && !Y && !W) || (W && X && !Y) || (W && !Z && !X) || (Y && W && !Z) || (Y && Z && !W) || (Y && X && !W);  
  digitalWrite(portC, C);  
  
  // D = notW notZ notX  +  notY not X W + Y notX Z + Y X notZ + notY X Z
  int D = (!W && !Z && !X) || (!Y && !X && W) || (Y && !X && Z) || (!Y && X && Z);
  digitalWrite(portD, D);
  
  // E = notZnotYnotX+WnotY+WnotYnotX+WZntoX+notYX+XWnotZ+notWnotZnotY
  int E = (!Z && !Y && X) || ( W && !Y && !X) || (W && Z && !X) || (!Y && X) || ( X && W && !Z) || (!W && !Z && !Y);
  digitalWrite(portE, E);
  
  // F = YZ + ZnotWnotX + notXnotYnotZ + WnotZnotY + ZnotWnotY
  int F = (Y && Z) || (Z && !W && !X) || (!X && !Y && !Z) || (W && !Z && !Y) || (Z && !W && !Y);
  digitalWrite(portF, F);
  
  // G = WY + WnotZnotX + notWZnotX + WnotZX + ZnotYX + notWnotZY
  int G = (W && Y) || (W && !Z && !X) || (!W && Z && !X) || (W && !Z && X) || (Z && !Y && X) || (!W && !Z && Y);
  digitalWrite(portG, G);
  

  
  
  
}
