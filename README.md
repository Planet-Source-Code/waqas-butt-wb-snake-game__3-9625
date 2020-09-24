<div align="center">

## wb Snake Game


</div>

### Description

Just for enjoyement

a small size game
 
### More Info
 
only arrow keys to control the direction of snake

its my first submission, i have written this small program consisting of only 78 statements only in 3 hours. let me do more work on it , and i will submit its 2nd version in which you can edit levels, high score, more speed , bonus items and many more...

not any


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Waqas Butt](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/waqas-butt.md)
**Level**          |Beginner
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[Games](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/games__3-13.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/waqas-butt-wb-snake-game__3-9625/archive/master.zip)





### Source Code

```
#include<iostream.h>
#include<conio.h>
#include<dos.h>
#include<graphics.h>
#include<stdlib.h>
///// WAQAS BUTT
///// wbwaqas@yahoo.com
///// PAKISTAN, LAHORE
/////PLZ CHANGE THE VALUES OF mx AND my for u'r computer settings
/// mx = MAX x-cooridnates
/// my = MAX y-coordinates
void main()
{
textcolor(2);
char ch;
int i,x=15,y=15,tx[100],ty[100],t=(2)+10,d=1,mx=78,my=50,fx=35,fy=35;
for(i=0;i<t;i++)	    //initializing
{
tx[i]=15;
ty[i]=15;
}
clrscr();
///////////////////////////////////////// loop starts here
	while(ch!=27)
	{
textcolor(2);
gotoxy(1,1);
cout<<"Score : "<<t-12;
gotoxy(35,1);
cout<<"WAQAS BUTT";
for(i=0;i<t;i++)     //printing tail
{
gotoxy(tx[i],ty[i]);
cout<<"Û";
}
gotoxy(tx[t-1],ty[t-1]);	//removing trail
cout<<" ";
gotoxy(x,y);		// printing head
cout<<"*";
gotoxy(fx,fy);		//printing fruit;
cout<<"<w>";
//change vale of DELAY for game speed
delay(50);		//game speed factor
///////////////////////////////////////////////////////////
if(kbhit())		//if key is pressed than enter here
{
ch=getch();
	if(ch==72 && d!=2)	//changing direction of snake w.r.t. key
	d=4;
	if(ch==80 && d!=4)
	d=2;
	if(ch==77 && d!=3)
	d=1;
	if(ch==75 && d!=1)
	d=3;
}
////////////////////////////////////////////////////////////
	if(d==4)        //changing location
	y--;
	if(d==2)
	y++;
	if(d==1)
	x++;
	if(d==3)
	x--;
///////////////////
//78,50
if(x<1)       //  checking crossing of borders
x=mx;
if(x>mx)
x=1;
if(y<1)
y=my;
if(y>my)
y=1;
///////////////////
gotoxy(tx[t-1],ty[t-1]);	//removing trail
cout<<" ";
tx[0]=x;          //	calculating the postion of tail
ty[0]=y;
for(i=1;i<t;i++)
{
tx[t-i]=tx[t-1-i];
ty[t-i]=ty[t-1-i];
}
///////////////////
			// checking collition of snake with its tail
for(i=2;i<t;i++)
{
	if(x==tx[i] && y==ty[i])
		{
	   //	clrscr();
		gotoxy(my/2,mx/2-10);
		cout<<"END OF GAME >> SNAKE COLLIDES";
		delay(2000);
		exit(1);
		}
}
//////////////////
			//checking eating food
if((x==fx || x==fx+1 || x==fx+2) && y==fy)
{
t++;
fx=10+random(50);
fy=10+random(35);
clrscr();
}
////////////////// checking winning condition
if(t>100)
{
gotoxy(my/2,mx/2-10);
cout<<"<< CONGRATULATIONS >>  wait 4 next version";
delay(5000);
exit(1);
}
///////////////////////////////////////////////////////////////////////////////
	}//loop
}//main
```

