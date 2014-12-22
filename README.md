#include<glut.h>
#include<math.h>
#include <iostream>
using namespace std;
float WinWid=1000.0;
float WinHei=1000.0;
float Angle=0.0, u=0;
float zoska=0.0;
int koor;
int n;
int or;
int ok;
float bum=1;
float ruh=1;
float krok;
int Psense;
int i;
int k;
float borodatarubkayosuf=0;


void Drawrobot()
{
        glClear(GL_COLOR_BUFFER_BIT);
        glPushMatrix();
        glBegin(GL_POINTS);
					u=rand()%10-5;
					cout<<u;
					bum=(koor-(ruh*krok))/koor;
if ((koor-(ruh*krok))<=0){
	  bum =0;}
					glColor3f(1.0,0,0);
                glVertex3f((or)*bum,(ok)*bum,0); 
 glBegin(GL_POINTS);
   glColor3d(1,0,0);
   glVertex3d(0,0,0); 
   glEnd();
  
  
        glPopMatrix();
        glutSwapBuffers();
}
void Timer(int value)
{
        glColor3f(1.0, 1.0, 1.0);
        glutPostRedisplay();
        glutTimerFunc(50, Timer, 0);
}

void Keyboard(unsigned char key, int x, int y)
{
        switch(key)
        {
        case 'a': ruh++;
                break;
        case 'd':;
                break;
				


        }
}

/*void SKeyboard(int key, int x, int y)
{
        switch(key)
        {
        case GLUT_KEY_LEFT:if (u<0) Angle++;
                break;
        case GLUT_KEY_RIGHT:if (u<0) Angle--;
                break;
		case GLUT_KEY_UP: if (u<0)zoska++;
			break;
		case GLUT_KEY_DOWN:if (u<0) zoska--;
			break;
       
		}
}*/

void Initialize()
{
        glClearColor(0.0, 0.0, 0.0, 1.0);
        glMatrixMode(GL_PROJECTION);
        glLoadIdentity();
        glOrtho(-WinWid/2, WinWid/2, -WinHei/2, WinHei/2, -400.0, 400.0);
        glMatrixMode(GL_MODELVIEW);
}

int main(int argc, char** argv)
{
 system("color F0");
cout<<"Vvedit pohubky pru hodbi"<<endl;
cout<<"pohubka=";
cin>>Psense;
cout<<"vvedit koordunaty robota vid -400 do 400"<<endl<<"x=";
cin>>or;
cout<<"y=";
cin>>ok;
cout<<"vvedit krok ruhu"<<endl;
cin>>krok;
koor=((or^2)+(ok^2))^(1/2);

n=100000;
system("cls");
        glutInit(&argc, argv);
        glutInitDisplayMode(GLUT_DOUBLE|GLUT_RGB);
        glutInitWindowSize(WinWid, WinHei);
        glutInitWindowPosition(100, 200);
        glutCreateWindow("Borodata Rubka Yosuf Vitaye Vas");
        glutDisplayFunc(Drawrobot);
        glutTimerFunc(50, Timer, 0);
        glutKeyboardFunc(Keyboard);
       // glutSpecialFunc(SKeyboard);
        Initialize();
        glutMainLoop();
		mark1:
        return 0;
}
