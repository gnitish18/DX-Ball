#include<fstream.h>
#include<conio.h>
#include<dos.h>
#include<stdlib.h>
#include<string.h>
#include<stdio.h>

class Scores
{
 char Name[15];
 int Score;
 public:
 void Putdata(char a[],int b);
 void Retrieve();
 void Display(int &i);
 int getscr();

}ex,s;

void Scores::Retrieve()
{int i=7;
 ifstream fi("DXBALL.DAT",ios::binary);
 clrscr();
 gotoxy(35,5);
 textcolor(6);
 cprintf("High Scores:\n");delay(1000);
 while(fi.read((char*)&s,sizeof(s)))
  {s.Display(i);
   delay(100);
  }
 getch();
}

void Scores::Display(int &i)
{gotoxy(1,i);
 textcolor(4);
 cprintf("%s",Name);
 textcolor(1);
 cprintf("%d",Score);
 ++i;
}

void Scores::Putdata(char a[],int b)
{strcpy(Name,a);
 strcat(Name,"               ");
 Score=b;
}

int Scores::getscr()
{return Score;}

void Destroy()
{ofstream fo("NEW.DAT",ios::binary);
 s.Putdata("NONAME",0);
 for(int i=0;i<10;i++)
   fo.write((char*)&s,sizeof(s));
 fo.close();
 remove("DXBALL.DAT");
 rename("NEW.DAT","DXBALL.DAT");
 gotoxy(25,18);
 textcolor(6);
 cprintf(" All Clear! ");delay(1000);
}

void Save()
{
ifstream fi("DXBALL.DAT",ios::binary);
ofstream fo("NEW.DAT",ios::binary);
char last='y';
while(fi.read((char*)&ex,sizeof(ex)))
 {if(ex.getscr()<=s.getscr())
   {fo.write((char*)&s,sizeof(s));
    fo.write((char*)&ex,sizeof(ex));
    last='n';
    break;
   }
  else
   fo.write((char*)&ex,sizeof(ex));
 }
if(last=='y')
 fo.write((char*)&s,sizeof(s));
else if(!fi.eof())
{while(!fi.eof())
 {fi.read((char*)&ex,sizeof(ex));
  fo.write((char*)&ex,sizeof(ex));
 }
}
fi.close();
fo.close();
remove("DXBALL.DAT");
rename("NEW.DAT","DXBALL.DAT");
}

void Remove()
{
ifstream fi("DXBALL.DAT",ios::binary);
ofstream fo("NEW.DAT",ios::binary);
while(fi.read((char*)&s,sizeof(s)))
 {fo.write((char*)&s,sizeof(s));
  if(fi.tellg()==10*sizeof(s))
    break;
 }
fi.close();
fo.close();
remove("DXBALL.DAT");
rename("NEW.DAT","DXBALL.DAT");
}

class DXBALL

{
 int h,dir,chnc,scr,batc,c,r,d;
 char ch;

 public:

 DXBALL()
 {c=62;
  r=22;
  dir=1;
  d=55;
  batc=58;
  chnc=4;
  scr=0;
  h=74;
  ch=' ';
 }
 void Welcome();
 void Menu();
 void Instructions();
 void Ball();
 void Pad();
 void Lines();
 void Play();

}dx;

void main()

{

 textbackground(15);

 clrscr();

 textbackground(15);

 dx.Welcome();

 dx.Menu();

 }

 void DXBALL::Welcome()

  { gotoxy(33,10);
    textcolor(4);
    cprintf("A Program by:");delay(1000);
    gotoxy(24,12);
    textcolor(1);
    cprintf(" Gudapati Nitish & Ajay Kumar G K ");delay(1000);
    getch();
  }

 void DXBALL::Menu()
  {char ch;
   X:
   clrscr();
   gotoxy(33,9);
   textcolor(4);
   cprintf("Menu");delay(100);
   gotoxy(24,11);
   textcolor(1);
   cprintf(" A. New Game ");
   gotoxy(24,12);
   textcolor(1);
   cprintf(" B. High Scores ");
   gotoxy(24,13);
   textcolor(1);
   cprintf(" C. Help ");
   gotoxy(24,14);
   textcolor(1);
   cprintf(" D. Clear High Scores ");
   gotoxy(24,15);
   textcolor(1);
   cprintf(" E. Exit ");
   gotoxy(24,16);
   textcolor(6);
   cprintf(" Enter choice:  ");cin>>ch;
   switch(ch)
   {case 'A':clrscr();
	     dx.Lines();
	     dx.Play();
	     break;
    case 'B':s.Retrieve();
	     goto X;
    case 'C':dx.Instructions();
	     goto X;
    case 'D':Destroy();
	     goto X;
    case 'E':exit(0);
    case 'a':clrscr();
	     dx.Lines();
	     dx.Play();
	     break;
    case 'b':s.Retrieve();
	     goto X;
    case 'c':dx.Instructions();
	     goto X;
    case 'd':Destroy();
	     goto X;
    case 'e':exit(0);

    default:clrscr();
	    gotoxy(33,9);
	    textcolor(4);
	    cprintf("\n Enter a valid choice");getch();
	    goto X;
    }
   getch();

  }

 void DXBALL::Instructions()

  {// INSTRUCTIONS
   clrscr();
   gotoxy(35,5);
   textcolor(6);
   cprintf("Instructions:\n");delay(1000);
   gotoxy(1,7);
   textcolor(1);
   cprintf(" \n  1.");
   textcolor(4);
   cprintf(" Use key 'a' to move the pad to the left. ");delay(100);
   gotoxy(1,8);
   textcolor(1);
   cprintf(" \n  2.");
   textcolor(4);
   cprintf(" Use key 'd' to move the pad to the right. ");delay(100);
   gotoxy(1,9);
   textcolor(1);
   cprintf("\n   3.");
   textcolor(4);
   cprintf(" Hit the ball with the pad and do not allow it to fall. ");delay(100);
   gotoxy(1,10);
   textcolor(1);
   cprintf(" \n  4.");
   textcolor(4);
   cprintf(" If the ball falls you lose a chance. ");delay(100);
   gotoxy(1,11);
   textcolor(1);
   cprintf(" \n  5.");
   textcolor(4);
   cprintf(" You have 5 turns. ");delay(100);
   gotoxy(1,12);
   textcolor(1);
   textcolor(0+128);
   cprintf(" \n  \" Press any key to return to menu. \" ");
   getch();
  }

 void DXBALL::Ball()

  {textcolor(6);textbackground(15);cprintf("*");
  }

 void DXBALL::Pad()

  {textcolor(1);textbackground(15);cprintf("<========>");
  }

 void DXBALL::Lines()

  {int i;
   // LOOP FOR HORIZONTAL LINES
   for(i=1;i<=80;i++)
   { gotoxy(i,1);
     textbackground(8);cprintf(" ");
     gotoxy(i,24);
     textbackground(8);cprintf(" ");
     textbackground(BROWN);textcolor(WHITE);
   }
   // LOOP FOR VERTICLE LINES
   for(i=1;i<=24;i++)
   { gotoxy(1,i);
     textbackground(8);cprintf(" ");
     gotoxy(80,i);
     textbackground(8);cprintf(" ");
   }
  }

 void DXBALL::Play()

 {
  c=62;
  r=22;
  dir=1;
  d=55;
  batc=58;
  chnc=4;
  scr=0;
  h=74;
  ch=' ';

  char nm[25];

  gotoxy(60,1);
  cout<<"            ";

  // DISPLAY JUST NIL SCORE IN THE START OF THE GAME

  gotoxy(59,1);
  cout<<"                 ";
  gotoxy(60,1);
  textcolor(4);textbackground(7);cprintf(" SCORE :");
  gotoxy(68,1);
  textcolor(9);textbackground(7);cprintf("0      ");

  // CHANCES LEFT

  gotoxy(5,1);
  cout<<"                 ";
  gotoxy(6,1);
  textcolor(4);textbackground(7);cprintf("CHANCES LEFT :");
  textcolor(9);textbackground(7);cprintf("%d",chnc);

  // DISPLAY JUST BAT AND BALL IN STARTING OF THE GAME

  gotoxy(c,r);
  dx.Ball();
  gotoxy(batc,23);
  dx.Pad();
  ch=getch();

  if(ch=='a')
    dir=2;

  if(ch=='d')
    dir=1;

  // COLUMN OF SCORE

  h=74;

  while((ch!='q')&&(ch!='Q'))
  { while((c<=79)&&(c>=2)&&(r<=22)&&(r>=2))
   // MAKE BALL
     { gotoxy(c,r);
       dx.Ball();
       // SCORE
       gotoxy(h-6,1);
       cout<<scr;
       scr++;
       // MAKE BAT
       gotoxy(batc,23);
       dx.Pad();
       delay(d);
       // ERASE BALL
       gotoxy(c,r);
       cout<<' ';
       // ERASE BAT
       gotoxy(batc,23);
       cout<<"          ";
       if(kbhit())
	 ch=getch();
       // DIRECTION TO BAT WITH KEYS
       if(ch=='a')
	 if(batc>2)  batc-=2;
       if(ch=='d')
	 if(batc<70) batc+=2;
       // CRITERIA FOR SCORE
       if(scr==10)
	 h=h--;
       if(scr==100)
	 h=h--;
       if(scr==1000)
	 h=h--;
       if(scr==10000)
	 h=h--;
       // DIRECTIONS
       if(dir==1)
	 {c++;r--;}
       if(dir==2)
	 {c--;r--;}
       if(dir==3)
	 {c--;r++;}
       if(dir==4)
	 {c++;r++;}
    }

   // CHANGE IN DIRECTION OF BALL

   if(c==1)
   { c=2;
     if(dir==2)
       dir=1;
     if(dir==3)
       dir=4;
   }
   if(c==80)
   { if(dir==1)
       dir=2;
     if(dir==4)
       dir=3;
     c=79;
   }

   if(r==1)
   { r=2;
     if(dir==2)
       dir=3;
     if(dir==1)
       dir=4;
   }

   // CONDITION IF BALL HITS THE BAT

   if((r==23)&&(c>=batc)&&(c<=batc+9))
   { r=22;
     if(dir==3)
       dir=2;
     if(dir==4)
       dir=1;
   }

   // CONDITION IF BALL DOESN'T HIT THE BAT

   if((r==23)&&((c<batc)||(c>batc+9)))
   // DEDUCTION OF CHANCES
   { // CONDITION IF CHANCE LEFT = 0
    if(chnc==0)
    { gotoxy(35,12);
      textcolor(4);textbackground(15);cprintf("GAME OVER!");
      gotoxy(28,15);
      textcolor(1);textbackground(15);cprintf("YOUR TOTAL SCORE : ");
      textcolor(0);
      cprintf("%d",scr-1);
      gotoxy(28,16);
      textcolor(1);textbackground(15);cprintf("\n Enter your name :");cin>>nm;
      s.Putdata(nm,scr-1);
      Save();
      Remove();
      delay(1000);
      ch=getch();
      dx.Menu();

    }
    --chnc;
    gotoxy(20,1);
    cout<<chnc;
    // LOOP FOR ANOTHER CHANCE OR QUIT
   A:gotoxy(16,15);
    textcolor(2);textbackground(15);cprintf("FOR ANOTHER CHANCE PRESS 'R' OR TO QUIT PRESS 'Q' ");
    ch=getch();
    gotoxy(25,12);
    textcolor(4);textbackground(15);cprintf("                          ");
    // IF THE USER TYPE 'Q' AT TIME OF CHOICE
    if((ch=='q')||(ch=='Q'))
    // ERASING THE PREVIOUS INPUT
    { gotoxy(16,15);
      cout<<"                                                 ";
      gotoxy(33,11);
      cout<<"               ";
      gotoxy(35,12);
      textcolor(4);textbackground(15);cprintf("GAME OVER!");
      gotoxy(28,15);
      textcolor(1);textbackground(15);cprintf("YOUR TOTAL SCORE : ");cout<<scr-1;
      gotoxy(28,16);
      textcolor(1);textbackground(15);cprintf("\n Enter your name :");cin>>nm;
      s.Putdata(nm,scr-1);
      Save();
      Remove();
      ch=getch();
      dx.Menu();

    }
    // IF THE USER TYPE 'R' AT TIME OF CHOICE
    else if((ch=='r')||(ch=='R'))
    // RESTART THE GAME
    { gotoxy(16,15);
      cout<<"                                                 ";
      gotoxy(33,11);
      cout<<"               ";
      // RE-ASSIGN ALL THE VALUES
      c=62;r=22;
      batc=58;
      // WHEN ANOTHER CHANCE STARTS, DISPLAY BAT AND BALL
      gotoxy(c,r);
      dx.Ball();
      gotoxy(batc,23);
      dx.Pad();
      ch=getch();
      if(ch=='a')
	dir=2;
      if(ch=='d')
	dir=1;
      // END OF GOTOXY LOOP
    }

    else
    {gotoxy(30,12);
     textcolor(4);textbackground(15);cprintf("Enter A Valid Choice");
     getch();
     goto A;
    }
    // END OF IF LOOP
   }

  // END OF WHILE LOOP

  }

 }