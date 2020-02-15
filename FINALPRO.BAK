#include<fstream.h>
#include<conio.h>
#include<iomanip.h>
#include<stdio.h>
#include<graphics.h>
#include<string.h>
int i,d;
int choice,n,p,gr,exitvar=0;char ch1,ch2,ch3,ch4;
struct administrator
{ int aid,aip;}OBJ;
struct menu
{char item[10][70];float price[10];};
struct hotel
{char name[20],address[50];char phone[12];menu y;}x,modobj,dispobj;
struct bill
{char name[10],address[50];char phone[15];int mop,order[10][2];float tp;}z;
void admin_mode();
void firstpage()
{
u1:
int g_dr=DETECT,mode;
initgraph(&g_dr,&mode,"c:\\TC\\BGI");
int x,y;
x=getmaxx()/2;
y=getmaxy()/2;
setbkcolor(YELLOW);
setcolor(BLUE);
setlinestyle(SOLID_LINE,0,NORM_WIDTH);
setfillstyle(XHATCH_FILL,2);
floodfill(50,50,RED);
settextstyle(SLASH_FILL,HORIZ_DIR,3);
floodfill(x,y,BLUE);
settextstyle(TRIPLEX_FONT,HORIZ_DIR,11);
outtextxy(165,10,"FOOD");
settextstyle(TRIPLEX_FONT,HORIZ_DIR,11);
outtextxy(120,100,"PANDA");
settextstyle(TRIPLEX_FONT,HORIZ_DIR,3);
outtextxy(45,250,"DEVELOPED BY S.SHREYA AND P.VISHNU PRIYA");
setcolor(MAGENTA);
settextstyle(TRIPLEX_FONT,HORIZ_DIR,4);
outtextxy(50,300,"1.ADMIN");
outtextxy(350,300,"2.CUSTOMER");
outtextxy(50,350,"3.EXIT");
outtextxy(50,400,"ENTER YOUR CHOICE 1 OR 2 or 3:");
char c,s[5];
c=getch();
s[0]=c;
s[1]='\0';
outtextxy(600,400,s);
getch();
cleardevice();
closegraph();
if(strcmpi(s,"1")==0)
      {	admin_mode();goto u1;}
else if(strcmpi(s,"3")==0)
    {   exitvar=1;
	return;
 }
 }
void admin_mode()
{
clrscr();
fstream f;
f.open("dummy.dat",ios::in|ios::binary);
int counter1=0,counter2=0;
char newname[20],newaddress[50],newphone[9];
int intnewphone[8],adminid,adminpass;
int menucount=0,flag1=0,flag2=0;
int choosecat, chooseoutlet;
cout<<"\t ()()() ()()() ()()() ()()     ()()()   ()   ()  () ()()     ()  \n";
cout<<"\t ()     ()  () ()  () ()  ()   ()  () ()  () ()()() ()  () ()  ()\n";
cout<<"\t ()()() ()  () ()  () ()  ()   ()()() ()()() () (() ()  () ()()()\n";
cout<<"\t ()     ()  () ()  () ()  ()   ()     ()  () ()  () ()  () ()  ()\n";
cout<<"\t ()     ()()() ()()() ()()     ()     ()  () ()  () ()()   ()  ()\n";
cout<<"\t\t\t\t\t\t\t-YOUR FOOD EXPERT\n";
cout<<"\t\tWELCOME TO ADMINISTRATOR MODE";
fstream ADMIN( "admin.dat",ios::binary|ios::in);
 while((counter1<3)&&(flag1!=1))
 {  if(counter1==0)
	cout<<"\nENTER YOUR ADMIN ID ";
    else
	 cout<<"ADMIN ID NOT FOUND.ENTER AGAIN ";
    cin>>adminid;
    fstream ADMIN( "admin.dat",ios::binary|ios::in);
    while(ADMIN.read((char*)&OBJ,sizeof(OBJ)))
       { if(OBJ.aid==adminid)
		{flag1=1;break;}
	 if(!ADMIN)
		 break;
	  }
 counter1++;
 }
 if (counter1==3)
	{ cout<<"THREE CHANCES EXCEEDED! GOING BACK TO PAGE 1";
	  getch();
	 return;}
 while((counter2<3)&&(!flag2))
		{if(counter2==0)
			cout<<"\nENTER YOUR PASSWORD ";
		else
			cout<<"WRONG PASSWORD.ENTER AGAIN ";
		cin>>adminpass;
		if(OBJ.aip==adminpass)
			{flag2=3;break;}
		counter2++;
	}
 if (counter2==3)
	{ cout<<"THREE CHANCES EXCEEDED! GOING BACK TO PAGE 1";
	  getch();
	 return;}
ADMIN.close();
wp1:
getch();
clrscr();
cout<<"\t\t\t\t WORK PAGE 1\nSelect the category to work with:";
cout<<"\n\t\t1.Chat\n\t\t2.Pizzas and Burgers\n\t\t3.South Indian snacks";
cout<<"\n\t\t4.Coffee and drinks\n\t\t5.Bread and cakes\n\t\t6.Icecreams";
cout<<"\n\t\t7.Indian sweets\n\t\t8.Go back to main page";
cout<<"\nEnter your choice: ";

cin>>choosecat;
while(!(choosecat>=1&&choosecat<=8))
{ cout<<"ENTER AGAIN FROM 1-7";
   cin>>choosecat;}
if(choosecat==8)
       {
	 return;}

wp2:
getch();
clrscr();
cout<<"\t\t\t\tWORK PAGE 2\nChoose the operation on the file:";
cout<<"\n1.MODIFY DETAILS OF FOOD OUTLETS";
cout<<"\n2.DELETE FOOD OUTLETS";
cout<<"\n3.ADD FOOD OUTLETS";
cout<<"\n4.MODIFY THE CONTENTS OF THE FOOD OUTLETS\nenter your choice:";
int choicefn;
cin>>choicefn;
while(!(choicefn>=1&&choicefn<=4))
	{cout<<"Enter again from 1 to 4";
	cin>>choicefn;}
	getch();
f.close();


if(choicefn==1)
{clrscr();
	  fstream f1,f2,f3,f4;
	     fstream buffer("buffer.dat",ios::binary|ios::out);
	     switch(choosecat)
 {case 1:  f1.open("chat.dat",ios::binary|ios::in);  break;
  case 2:  f1.open("pizza.dat",ios::binary|ios::in); break;
  case 3:  f1.open("south.dat",ios::binary|ios::in); break;
  case 4:  f1.open("coffee.dat",ios::binary|ios::in);break;
  case 5:  f1.open("bakery.dat",ios::binary|ios::in);break;
  case 6:  f1.open("ice.dat",ios::binary|ios::in);   break;
  case 7:  f1.open("sweet.dat",ios::binary|ios::in); break;
}
  menucount=0;
     while(f1.read((char*)&modobj,sizeof(modobj)))
     { cout<<++menucount<<"."<<modobj.name<<"\n"<<modobj.address;
     cout<<"\n"<<modobj.phone<<"\n";
     if(!f1)break;
     }
	     cout<<"ENTER THE NUMBER OF THE FOOD OUTLET YOU WANT TO MODIFY";
	     cin>>chooseoutlet;
	     cout<<"\nENTER NEW NAME:";
	   gets(newname);
	   cout<<"ENTER NEW ADDRESS:";
	   gets(newaddress);
	   cout<<"ENTER THE EIGHT DIGIT PHONE NUMBER:";
	   gets(newphone);

	     char extractname[20];
	     f1.close();
	     switch(choosecat)
 {case 1:  f2.open("chat.dat",ios::binary|ios::in);  break;
  case 2:  f2.open("pizza.dat",ios::binary|ios::in); break;
  case 3:  f2.open("south.dat",ios::binary|ios::in); break;
  case 4:  f2.open("coffee.dat",ios::binary|ios::in);break;
  case 5:  f2.open("bakery.dat",ios::binary|ios::in);break;
  case 6:  f2.open("ice.dat",ios::binary|ios::in);   break;
  case 7:  f2.open("sweet.dat",ios::binary|ios::in); break;
}
	     f2.seekg(((chooseoutlet-1)*(sizeof(modobj))),ios::beg);
	     f2.read((char*)&modobj,sizeof(modobj));
	     strcpy(extractname,modobj.name);
	    strcpy(modobj.name,newname);
	  strcpy(modobj.address,newaddress);
	  strcpy(modobj.phone,newphone);

	     f2.seekg(0);
	     while(f2.read((char*)&dispobj,sizeof(dispobj)))
	     {if(strcmpi(extractname,dispobj.name))
		  buffer.write((char*)&dispobj,sizeof(dispobj));
	     else break;
	       if(!f2) break;
	       }
		buffer.write((char*)&modobj,sizeof(modobj));
	       while(f2.read((char*)&dispobj,sizeof(dispobj)))
	       {   buffer.write((char*)&dispobj,sizeof(dispobj));
	       if(!f2)
	       break;}
	       f2.close();
	       buffer.close();
	       switch(choosecat)
 {case 1:  f3.open("chat.dat",ios::binary|ios::out|ios::trunc);  break;
  case 2:  f3.open("pizza.dat",ios::binary|ios::out|ios::trunc); break;
  case 3:  f3.open("south.dat",ios::binary|ios::out|ios::trunc); break;
  case 4:  f3.open("coffee.dat",ios::binary|ios::out|ios::trunc);break;
  case 5:  f3.open("bakery.dat",ios::binary|ios::out|ios::trunc);break;
  case 6:  f3.open("ice.dat",ios::binary|ios::out|ios::trunc);   break;
  case 7:  f3.open("sweet.dat",ios::binary|ios::out|ios::trunc); break;
}
	     fstream buffer2("buffer.dat",ios::binary|ios::in);
	     while(buffer2.read((char*)&modobj,sizeof(modobj)))
	     { f3.write((char*)&modobj,sizeof(modobj));
	       if(!buffer2) break;
	       }
	       f3.close();
	       buffer2.close();
	       switch(choosecat)
 {case 1:  f4.open("chat.dat",ios::binary|ios::in);  break;
  case 2:  f4.open("pizza.dat",ios::binary|ios::in); break;
  case 3:  f4.open("south.dat",ios::binary|ios::in); break;
  case 4:  f4.open("coffee.dat",ios::binary|ios::in);break;
  case 5:  f4.open("bakery.dat",ios::binary|ios::in);break;
  case 6:  f4.open("ice.dat",ios::binary|ios::in);   break;
  case 7:  f4.open("sweet.dat",ios::binary|ios::in); break;
}
clrscr();
	       menucount=0;
cout<<"Modification successfully done!Current status\n";
     while(f4.read((char*)&modobj,sizeof(modobj)))
     { cout<<++menucount<<"."<<modobj.name<<"\n"<<modobj.address;
     cout<<"\n"<<modobj.phone<<"\n";
     if(!f4)break;
     }
     f4.close();

	  }
else  if(choicefn==2)
	  { clrscr();
	  fstream f1,f2,f3,f4;
	     fstream buffer("buffer.dat",ios::binary|ios::out);
	     switch(choosecat)
 {case 1:  f1.open("chat.dat",ios::binary|ios::in);  break;
  case 2:  f1.open("pizza.dat",ios::binary|ios::in); break;
  case 3:  f1.open("south.dat",ios::binary|ios::in); break;
  case 4:  f1.open("coffee.dat",ios::binary|ios::in);break;
  case 5:  f1.open("bakery.dat",ios::binary|ios::in);break;
  case 6:  f1.open("ice.dat",ios::binary|ios::in);   break;
  case 7:  f1.open("sweet.dat",ios::binary|ios::in); break;
}
  menucount=0;
     while(f1.read((char*)&modobj,sizeof(modobj)))
     { cout<<++menucount<<"."<<modobj.name<<"\n"<<modobj.address;
     cout<<"\n"<<modobj.phone<<"\n";
     if(!f1)break;
     }
	     cout<<"ENTER THE NUMBER OF THE FOOD OUTLET YOU WANT TO DELETE";
	     cin>>chooseoutlet;
	     char extractname[20];
	     f1.close();
	     switch(choosecat)
 {case 1:  f2.open("chat.dat",ios::binary|ios::in);  break;
  case 2:  f2.open("pizza.dat",ios::binary|ios::in); break;
  case 3:  f2.open("south.dat",ios::binary|ios::in); break;
  case 4:  f2.open("coffee.dat",ios::binary|ios::in);break;
  case 5:  f2.open("bakery.dat",ios::binary|ios::in);break;
  case 6:  f2.open("ice.dat",ios::binary|ios::in);   break;
  case 7:  f2.open("sweet.dat",ios::binary|ios::in); break;
}
	     f2.seekg(((chooseoutlet-1)*(sizeof(modobj))),ios::beg);
	     f2.read((char*)&modobj,sizeof(modobj));
	     strcpy(extractname,modobj.name);
	     f2.seekg(0);
	     while(f2.read((char*)&modobj,sizeof(modobj)))
	     {if(strcmpi(extractname,modobj.name))
		  buffer.write((char*)&modobj,sizeof(modobj));
	       if(!f2) break;
	       }
	       f2.close();
	       buffer.close();
	       switch(choosecat)
 {case 1:  f3.open("chat.dat",ios::binary|ios::out|ios::trunc);  break;
  case 2:  f3.open("pizza.dat",ios::binary|ios::out|ios::trunc); break;
  case 3:  f3.open("south.dat",ios::binary|ios::out|ios::trunc); break;
  case 4:  f3.open("coffee.dat",ios::binary|ios::out|ios::trunc);break;
  case 5:  f3.open("bakery.dat",ios::binary|ios::out|ios::trunc);break;
  case 6:  f3.open("ice.dat",ios::binary|ios::out|ios::trunc);   break;
  case 7:  f3.open("sweet.dat",ios::binary|ios::out|ios::trunc); break;
}
	     fstream buffer2("buffer.dat",ios::binary|ios::in);
	     while(buffer2.read((char*)&modobj,sizeof(modobj)))
	     { f3.write((char*)&modobj,sizeof(modobj));
	       if(!buffer2) break;
	       }
	       f3.close();
	       buffer2.close();
	       switch(choosecat)
 {case 1:  f4.open("chat.dat",ios::binary|ios::in);  break;
  case 2:  f4.open("pizza.dat",ios::binary|ios::in); break;
  case 3:  f4.open("south.dat",ios::binary|ios::in); break;
  case 4:  f4.open("coffee.dat",ios::binary|ios::in);break;
  case 5:  f4.open("bakery.dat",ios::binary|ios::in);break;
  case 6:  f4.open("ice.dat",ios::binary|ios::in);   break;
  case 7:  f4.open("sweet.dat",ios::binary|ios::in); break;
}
clrscr();
	       menucount=0;
cout<<"Deletion successfully done!Current status\n";
     while(f4.read((char*)&modobj,sizeof(modobj)))
     { cout<<++menucount<<"."<<modobj.name<<"\n"<<modobj.address;
     cout<<"\n"<<modobj.phone<<"\n";
     if(!f4)break;
     }
     f4.close();
		  }

else  if (choicefn==3)
	  {clrscr();
	  f.close();
	   switch(choosecat)
	   {case 1:  f.open("chat.dat",ios::binary|ios::app|ios::in);  break;
	    case 2:  f.open("pizza.dat",ios::binary|ios::app|ios::in); break;
	    case 3:  f.open("south.dat",ios::binary|ios::app|ios::in); break;
	    case 4:  f.open("coffee.dat",ios::binary|ios::app|ios::in);break;
	   case 5:  f.open("bakery.dat",ios::binary|ios::app|ios::in);break;
	  case 6:  f.open("ice.dat",ios::binary|ios::app|ios::in);   break;
	   case 7:  f.open("sweet.dat",ios::binary|ios::app|ios::in); break;
	    }
	   cout<<"\nENTER THE NAME OF THE HOTEL:";
	   gets(modobj.name);
	   cout<<"ENTER THE PHONE NUMBER:";
	   gets(modobj.phone);
	   cout<<"ENTER  ADDRESS OF THE HOTEL:";
	  gets(modobj.address);
	  cout<<"ENTER ITEMS AND THEIR PRICE INTO THE MENU:";
	  for(int i=0;i<10;i++)
	  { cout<<"ENTER ITEM"<<i+1<<":";
	    gets(modobj.y.item[i]);
	    if(choosecat==2)
		cout<<"ENTER PRICE OF PERSONAL PIZZA";
	    else
		cout<<"ENTER THE PRICE FOR ITEM";
	    cout<<i+1<<":";
	    cin>>modobj.y.price[i];  }
	    f.write((char*)&modobj,sizeof(modobj));
	  getch();
	  clrscr();
	  cout<<"\nData Added Successfully!. Current Status:";
	  menucount=0;
	  f.seekg(0,ios::beg);
	  while(f.read((char*)&modobj,sizeof(modobj)))
	 {  cout<<++menucount<<"."<<modobj.name<<"\n";
	   cout<<modobj.address<<"\n"<<modobj.phone<<"\n";
	  if(f.eof()) break; }
	  f.close();
		  }
else
	  { clrscr();
	  fstream f1,f,f3,f4;
	  fstream buffer("buffer.dat",ios::binary|ios::out);
	    switch(choosecat)
	    {case 1:  f1.open("chat.dat",ios::binary|ios::in);  break;
	     case 2:  f1.open("pizza.dat",ios::binary|ios::in); break;
	     case 3:  f1.open("south.dat",ios::binary|ios::in); break;
	     case 4:  f1.open("coffee.dat",ios::binary|ios::in);break;
	     case 5:  f1.open("bakery.dat",ios::binary|ios::in);break;
	     case 6:  f1.open("ice.dat",ios::binary|ios::in);   break;
	     case 7:  f1.open("sweet.dat",ios::binary|ios::in); break;
	    }
     menucount=0;
     while(f1.read((char*)&modobj,sizeof(modobj)))
     { cout<<++menucount<<modobj.name<<"\n"<<modobj.address;
     cout<<"\n"<<modobj.phone<<"\n";
     if(f1.eof()) break;
     }
	     f1.close();
	     cout<<"\nENTER THE NUMBER OF THE FOOD OUTLET ";
	     cout<<"WHOSE DETAILS YOU WANT TO MODIFY";
	     cin>>chooseoutlet;
	     switch(choosecat)
	    {case 1:  f.open("chat.dat",ios::binary|ios::in);  break;
	     case 2:  f.open("pizza.dat",ios::binary|ios::in); break;
	     case 3:  f.open("south.dat",ios::binary|ios::in); break;
	     case 4:  f.open("coffee.dat",ios::binary|ios::in);break;
	     case 5:  f.open("bakery.dat",ios::binary|ios::in);break;
	     case 6:  f.open("ice.dat",ios::binary|ios::in);   break;
	     case 7:  f.open("sweet.dat",ios::binary|ios::in); break;
	    }
	    f.seekg((chooseoutlet-1)*sizeof(modobj),ios::beg);
	    f.read((char*)&modobj,sizeof(modobj));
	  clrscr();
   cout<<"\n"<<modobj.name<<"\n"<<modobj.address<<"\n"<<modobj.phone;
   cout<<"\n";
   if(choosecat==1||choosecat==3||choosecat==4)
       {cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE"<<"\n";
	for(int i=0;i<10;i++)
	 {cout<<setw(2)<<i+1;
	  cout<<setw(25)<<modobj.y.item[i]<<setw(20)<<modobj.y.price[i]<<"\n";
	  } }
   else if(choosecat==5||choosecat==6||choosecat==7)
       {cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE/kg"<<"\n";
	for(int i=0;i<10;i++)
	  {cout<<setw(2)<<i+1;
	   cout<<setw(25)<<modobj.y.item[i]<<setw(20);
	   cout<<modobj.y.price[i]<<"\n";}}
   else
       {cout<<setw(15)<<"ITEM"<<setw(40)<<"PRICE\n";
	cout<<setw(35)<<"PERSONAL"<<setw(19)<<"MEDIUM"<<setw(19)<<"LARGE\n";
	for(int i=0;i<10;i++)
	  {cout<<setw(2)<<i+1;
	   cout<<setw(23)<<modobj.y.item[i]<<setw(7);
	   cout<<modobj.y.price[i]<<setw(20);
	   cout<<modobj.y.price[i]+100<<setw(20)<<modobj.y.price[i]+200<<"\n";
	   }    }
	  cout<<"\nENTER FUNCTION\n1.MODIFY THE NAME AND PRICE OF ITEM";
	  cout<<"\n2.CHANGE THE PRICE OF AN ITEM\n Enter Choice:";
	   int random;
	   cin>>random;
	   cout<<"\nEnter the item number you want to change:";
	     int changechoice;float changedprice;
	     cin>>changechoice;
	   if (random ==1)
	  { char changeitem[20];
	    cout<<"\nEnter New Name";
	    gets(changeitem);
	    cout<<"Enter the New Price";
	    cin>>changedprice;
	    strcpy(modobj.y.item[changechoice-1],changeitem);
	    modobj.y.price[changechoice-1]=changedprice;
		}
	 else if(random==2)
	    { cout<<"Enter the New Price";
	    cin>>changedprice;
	    modobj.y.price[changechoice-1]=changedprice;
	    }
	    char extractname[20];
	    strcpy(extractname,modobj.name);

	     f.seekg(0);
	     while(f.read((char*)&dispobj,sizeof(dispobj)))
	     {if(strcmpi(extractname,dispobj.name))
		  buffer.write((char*)&dispobj,sizeof(dispobj));
	     else break;
	       if(!f) break;
	       }
		buffer.write((char*)&modobj,sizeof(modobj));
	       while(f.read((char*)&dispobj,sizeof(dispobj)))
	       {   buffer.write((char*)&dispobj,sizeof(dispobj));
	       if(!f)
	       break;}
	       f.close();
	       buffer.close();
	       switch(choosecat)
 {case 1:  f3.open("chat.dat",ios::binary|ios::out|ios::trunc);  break;
  case 2:  f3.open("pizza.dat",ios::binary|ios::out|ios::trunc); break;
  case 3:  f3.open("south.dat",ios::binary|ios::out|ios::trunc); break;
  case 4:  f3.open("coffee.dat",ios::binary|ios::out|ios::trunc);break;
  case 5:  f3.open("bakery.dat",ios::binary|ios::out|ios::trunc);break;
  case 6:  f3.open("ice.dat",ios::binary|ios::out|ios::trunc);   break;
  case 7:  f3.open("sweet.dat",ios::binary|ios::out|ios::trunc); break;
}
	     fstream buffer2("buffer.dat",ios::binary|ios::in);
	     while(buffer2.read((char*)&modobj,sizeof(modobj)))
	     { f3.write((char*)&modobj,sizeof(modobj));
	       if(!buffer2) break;
	       }
	       f3.close();
	       buffer2.close();
	       switch(choosecat)
 {case 1:  f4.open("chat.dat",ios::binary|ios::in);  break;
  case 2:  f4.open("pizza.dat",ios::binary|ios::in); break;
  case 3:  f4.open("south.dat",ios::binary|ios::in); break;
  case 4:  f4.open("coffee.dat",ios::binary|ios::in);break;
  case 5:  f4.open("bakery.dat",ios::binary|ios::in);break;
  case 6:  f4.open("ice.dat",ios::binary|ios::in);   break;
  case 7:  f4.open("sweet.dat",ios::binary|ios::in); break;
}
clrscr();

cout<<"Modification successfully done!Current status\n";
cout<<"\n"<<modobj.name<<"\n"<<modobj.address<<"\n"<<modobj.phone;
   cout<<"\n";
   if(choosecat==1||choosecat==3||choosecat==4)
       {cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE"<<"\n";
	for(int i=0;i<10;i++)
	 {cout<<setw(2)<<i+1;
	  cout<<setw(25)<<modobj.y.item[i]<<setw(20)<<modobj.y.price[i]<<"\n";
	  } }
   else if(choosecat==5||choosecat==6||choosecat==7)
       {cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE/kg"<<"\n";
	for(int i=0;i<10;i++)
	  {cout<<setw(2)<<i+1;
	   cout<<setw(25)<<modobj.y.item[i]<<setw(20);
	   cout<<modobj.y.price[i]<<"\n";}}
   else
       {cout<<setw(15)<<"ITEM"<<setw(40)<<"PRICE\n";
	cout<<setw(35)<<"PERSONAL"<<setw(19)<<"MEDIUM"<<setw(19)<<"LARGE\n";
	for(int i=0;i<10;i++)
	  {cout<<setw(2)<<i+1;
	   cout<<setw(23)<<modobj.y.item[i]<<setw(7);
	   cout<<modobj.y.price[i]<<setw(20);
	   cout<<modobj.y.price[i]+100<<setw(20)<<modobj.y.price[i]+200<<"\n";
	   }    }

     f4.close();
     getch();


	 }
int finalevar;
cout<<"press\n1 to go to FRONT PAGE\n2 to WORK PAGE 1\n3 to WORKPAGE 2";
cin>>finalevar;
switch(finalevar)
{ case 1: firstpage(); break;
  case 2: goto wp1;
  case 3: goto wp2;
  }   }

void billp()
{int c,o,u,n=0;char pzz;
 z.tp=0;char a[10];
 do
 {cout<<"enter item no. ";
  cin>>o;
  while(!(o>=1&&o<=10))
	{cout<<"enter from 1 to 10";
	 cin>>o;}
  z.order[n][0]=o;
  cout<<"enter units ";
  cin>>u;
  z.order[n][1]=u;
  cout<<"Press 'p' for personal,'m'for medium,'l' for large ";
  cin>>pzz;
  while(!(pzz=='p'||pzz=='m'||pzz=='l'))
	{cout<<"enter 'p' or 'm' or 'l' ";
	 cin>>pzz;}
  a[n++]=pzz;
  cout<<"press 1 to order more,2 to proceed further ";
  cin>>c;
  while(!(c==1||c==2))
	{cout<<"Enter again (1/2)";
	cin>>c;}
  }
  while(c!=2);
  cout<<"Enter your name\n";
  gets(z.name);
  cout<<"Enter your address\n";
  gets(z.address);
  cout<<"Enter your phone no.\n";
  gets(z.phone);
  cout<<"Press 1 for CASH ON DELIVERY,2 for CARD payment ";
  cin>>z.mop;
  while(!(z.mop==1||z.mop==2))
	{cout<<"Enter 1 or 2 ";
	 cin>>z.mop;}
  char bz[20],cz[30];
  int iz=0,jz;char dz[4];
  if(z.mop==2)
	{
	int cccounter=0;
	while(cccounter!=16)
	{cout<<"Enter 16 digit credit card number: ";
	gets(bz);
	cccounter=strlen(bz);
	}
	cout<<"Enter name in the credit card(in caps): ";
	gets(cz);
	cout<<"Enter 4 digit pin: ";
	while(iz<4)
	{dz[iz]=getch();
	 cout<<"*";
	 iz++;
	}
	getch() ;
	cout<<"\nCustomer Name: "<<cz;
	cout<<"\nCustomer credit card number: ";
	cout<<"**** **** ****";
	for(jz=12;jz<16;jz++)
	cout<<bz[jz];
	cout<<"\nAmount credited successfully!";
	}
  for(int i=0;i<n;i++)
	{if(a[i]=='p')
		 z.tp+=x.y.price[z.order[i][0]-1]*(z.order[i][1]);
	 else if(a[i]=='m')
		 z.tp+=(x.y.price[z.order[i][0]-1]+100)*(z.order[i][1]);
	 else
		 z.tp+=(x.y.price[z.order[i][0]-1]+200)*(z.order[i][1]);}

  clrscr();
  cout<<"\n\t\t\tBILL\n\t\t\t____";
  cout<<"\nFood outlet details:\n";
  cout<<"Name: "<<x.name<<"\nAddress: "<<x.address<<"\nPhone: "<<x.phone;
  cout<<"\n";
  cout<<"Customer details:\n";
  cout<<"Name: "<<z.name<<"\nAddress: "<<z.address<<"\nPhone: ";
  cout<<z.phone<<"\nMode of payment: ";
  if(z.mop==1)
	cout<<"Cash on delivery\n";
  else
       {cout<<"Card payment\nCustomer credit card number: ";
	cout<<"**** **** ****";
	for(jz=12;jz<16;jz++)
	cout<<bz[jz];}
  cout<<"\n\t\t\t\t      ORDER:\n";
  cout<<setw(20)<<"ITEM"<<setw(20)<<"P/M/L"<<setw(20);
  cout<<"PRICE"<<setw(20)<<"UNITS\n";
  for(i=0;i<n;i++)
       {cout<<setw(22)<<x.y.item[z.order[i][0]-1]<<setw(18);
	if(a[i]=='p')
		cout<<"Personal";
	else if(a[i]=='m')
		cout<<"Medium";
	else
		cout<<"Large";
	cout<<setw(19);
	if(a[i]=='p')
		cout<<x.y.price[z.order[i][0]-1];
	else if(a[i]=='m')
		cout<<x.y.price[z.order[i][0]-1]+100;
	else
		cout<<x.y.price[z.order[i][0]-1]+200;
	cout<<setw(20)<<z.order[i][1]<<"\n";}
  cout<<"TRP:Rs."<<z.tp;
  cout<<"\nTAX:Rs.50";
  cout<<"\nNET BILL AMOUNT:Rs."<<z.tp+50;
  cout<<"\nYour order will arrive within an hour";
  cout<<"\n\t\t\tTHANK YOU!!!";
  getch();
}
void bill()
{int c,o,u,n=0;
 z.tp=0;
 do
 {cout<<"enter item no. ";
  cin>>o;
  while(!(o>=1&&o<=10))
	{cout<<"enter from 1 to 10";
	 cin>>o;}
  z.order[n][0]=o;
  cout<<"enter units ";
  cin>>u;
  z.order[n++][1]=u;
  cout<<"press 1 to order more,2 to proceed further ";
  cin>>c;
  while(!(c==1||c==2))
	{cout<<"Enter again (1/2)";
	cin>>c;}
  }
 while(c!=2);
  cout<<"Enter your name\n";
  gets(z.name);
  cout<<"Enter your address\n";
  gets(z.address);
  cout<<"Enter your phone no.\n";
  gets(z.phone);
  cout<<"Press 1 for CASH ON DELIVERY,2 for CARD payment ";
  cin>>z.mop;
  while(!(z.mop==1||z.mop==2))
	{cout<<"Enter 1 or 2 ";
	 cin>>z.mop;}
  char bz[20],cz[30];
  int iz=0,jz;char dz[4];
  if(z.mop==2)
	{ int cccounter=0;
	 while(cccounter!=16)
	 {
	cout<<"Enter the 16 digit credit card number: ";
	gets(bz);
	cccounter=strlen(bz);   }
	cout<<"Enter name in the credit card(in caps): ";
	gets(cz);
	cout<<"Enter 4 digit pin: ";
	while(iz<4)
	{dz[iz]=getch();
	 cout<<"*";
	 iz++;
	}
	getch() ;
	cout<<"\nCustomer Name: "<<cz;
	cout<<"\nCustomer credit card number: ";
	cout<<"**** **** ****";
	for(jz=12;jz<16;jz++)
	cout<<bz[jz];
	cout<<"\nAmount credited successfully!";
	}
  for(int i=0;i<n;i++)
	 z.tp+=x.y.price[z.order[i][0]-1]*(z.order[i][1]);
  clrscr();
  cout<<"\n\t\t\tBILL\n\t\t\t----";
  cout<<"\nFOOD OUTLET DETAILS:\n";
  cout<<"Name: "<<x.name<<"\nAddress: "<<x.address<<"\nPhone: "<<x.phone;
  cout<<"\n";
  cout<<"CUSTOMER DETAILS:\n";
  cout<<"Name: "<<z.name<<"\nAddress: "<<z.address<<"\nPhone ";
  cout<<z.phone<<"\nMode of payment: ";
  if(z.mop==1)
	cout<<"Cash on delivery\n";
  else
       {cout<<"Card payment\nCustomer credit card number: ";
	cout<<"**** **** ****";
	for(jz=12;jz<=15;jz++)
	cout<<bz[jz];}
  cout<<"\n\t\t\t\t   ORDER\n";
  cout<<setw(20)<<"ITEM"<<setw(20)<<"PRICE"<<setw(20)<<"UNITS\n";
  for(i=0;i<n;i++)
       {cout<<setw(20)<<x.y.item[z.order[i][0]-1]<<setw(20);
	cout<<x.y.price[z.order[i][0]-1]<<setw(20)<<z.order[i][1]<<"\n";}
  cout<<"TRP:Rs."<<z.tp;
  cout<<"\nTAX:Rs.10";
  cout<<"\nTOTAL BILL AMOUNT:Rs."<<z.tp+10;
  cout<<"\nYour order will arrive within an hour";
  cout<<"\n\t\t\t\tTHANK YOU!!!";
  getch();
}
void main()
{
clrscr();
firstpage();
g1:
if(exitvar==1)
	return;
fstream f1,f2,f3,f4,f5,f6,f7;

do
{l1:
clrscr();
cout<<"\t ()()() ()()() ()()() ()()     ()()()   ()   ()  () ()()     ()  \n";
cout<<"\t ()     ()  () ()  () ()  ()   ()  () ()  () ()()() ()  () ()  ()\n";
cout<<"\t ()()() ()  () ()  () ()  ()   ()()() ()()() () (() ()  () ()()()\n";
cout<<"\t ()     ()  () ()  () ()  ()   ()     ()  () ()  () ()  () ()  ()\n";
cout<<"\t ()     ()()() ()()() ()()     ()     ()  () ()  () ()()   ()  ()\n";
cout<<"\t\t\t\t\t\t\t-YOUR FOOD EXPERT\n";
cout<<"\n\t\t\tWhat's your choice today?\n";
cout<<"\n\t\t1.Chat\n\t\t2.Pizzas and Burgers\n\t\t3.South Indian snacks";
cout<<"\n\t\t4.Coffee and drinks\n\t\t5.Bread and cakes\n\t\t6.Icecreams";
cout<<"\n\t\t7.Indian sweets\n\t\t8.No thanks,I'm full";
cout<<"\nI want to binge on (press you choice no.) or press 9 to go to main";
cout<<"page  ";
cin>>choice;
while(!(choice>=1&&choice<=9))
	{cout<<"Enter choice again from 1-9";
	 cin>>choice;}
if(choice==9)
       {firstpage();goto g1;}

l2:
d=0;

//printing food outlets
switch(choice)
{case 1: { clrscr();
	     cout<<"\t\t\tYOUR FOOD OUTLETS\n";
	  f1.open("chat.dat",ios::binary|ios::in);
	   while(  f1.read((char*)&x,sizeof(x)))
     {	cout<<++d<<". "<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
       cout<<"\n";
       if(f1.eof())
	break;}
       f1.close();} break;
 case 2: { clrscr();
	      cout<<"\t\t\tYOUR FOOD OUTLETS\n";
	  f2.open("pizza.dat",ios::binary|ios::in);
	     while(  f2.read((char*)&x,sizeof(x)))
       {  cout<<++d<<". "<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
	cout<<"\n";
       if(f2.eof())
	break;}
      f2.close(); } break;
 case 3: { clrscr();
	   cout<<"\t\t\tYOUR FOOD OUTLETS\n";
	   f3.open("south.dat",ios::binary|ios::in);
	    while(  f3.read((char*)&x,sizeof(x)))
	{  cout<<++d<<". "<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
	   cout<<"\n";
	 if(f3.eof())
	  break;}
       f3.close();} break;
 case 4: { clrscr();
	   cout<<"\t\t\tYOUR FOOD OUTLETS\n";
	  f4.open("coffee.dat",ios::binary|ios::in);
	   while(  f4.read((char*)&x,sizeof(x)))
      {    cout<<++d<<". "<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
	   cout<<"\n";
	  if(f4.eof())
	   break;}
       f4.close();}break;
 case 5:{ clrscr();
	   cout<<"\t\t\tYOUR FOOD OUTLETS\n";
	  f5.open("bakery.dat",ios::binary|ios::in);
	   while(  f5.read((char*)&x,sizeof(x)))
      {	cout<<++d<<". "<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
       cout<<"\n";
	if(f5.eof())
	break;}
     f5.close();}break;
 case 6: { clrscr();
	    cout<<"\t\t\tYOUR FOOD OUTLETS\n";
	 f6.open("ice.dat",ios::binary|ios::in);
	  while(  f6.read((char*)&x,sizeof(x)))
      {	cout<<++d<<". "<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
       cout<<"\n";
       if(f6.eof())
	break;}
      f6.close();}  break;
 case 7: { clrscr();
	cout<<"\t\t\tYOUR FOOD OUTLETS\n";
      f7.open("sweet.dat",ios::binary|ios::in);
      while(  f7.read((char*)&x,sizeof(x)))
      {	cout<<++d<<". "<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
       cout<<"\n";
	if(f7.eof())
	break;}
      f7.close();}break;
 case 8:  cout<<"Goodbye.Visit again.";goto e;
 }

cout<<"\nProceed?press y ,otherwise n to go back to main page ";
cin>>ch1;
while(!(ch1=='y'||ch1=='n'))
	{cout<<"Enter y or n";
	 cin>>ch1;}
if(ch1=='y')
  {cout<<"\nPress your choice no. ";
   cin>>n;
   switch(choice)
{case 1:  f1.open("chat.dat",ios::binary|ios::in);  break;
 case 2:  f2.open("pizza.dat",ios::binary|ios::in); break;
 case 3:  f3.open("south.dat",ios::binary|ios::in); break;
 case 4:  f4.open("coffee.dat",ios::binary|ios::in);break;
 case 5:  f5.open("bakery.dat",ios::binary|ios::in);break;
 case 6:  f6.open("ice.dat",ios::binary|ios::in);   break;
 case 7:  f7.open("sweet.dat",ios::binary|ios::in); break;
 }


   if(choice==1)
       {clrscr();
     f1.seekg((n-1)*sizeof(x),ios::beg);
     f1.read((char*)&x,sizeof(x));
    cout<<"\n"<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
    cout<<"\n";
    cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE"<<"\n";
	for(int i=0;i<10;i++)
	 {cout<<setw(2)<<i+1;
	  cout<<setw(25)<<x.y.item[i]<<setw(20)<<x.y.price[i]<<"\n";}
     f1.close();
      }
   else if(choice==3)
   {clrscr();
     f3.seekg((n-1)*sizeof(x),ios::beg);
     f3.read((char*)&x,sizeof(x));
    cout<<"\n"<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
    cout<<"\n";
    cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE"<<"\n";
	for(int i=0;i<10;i++)
	 {cout<<setw(2)<<i+1;
	  cout<<setw(25)<<x.y.item[i]<<setw(20)<<x.y.price[i]<<"\n";}
    f3.close();  }
  else if (choice==4)
   {clrscr();
     f4.seekg((n-1)*sizeof(x),ios::beg);
     f4.read((char*)&x,sizeof(x));
    cout<<"\n"<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
    cout<<"\n";
    cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE"<<"\n";
	for(int i=0;i<10;i++)
	 {cout<<setw(2)<<i+1;
	  cout<<setw(25)<<x.y.item[i]<<setw(20)<<x.y.price[i]<<"\n";}
    f4.close();  }



   else if(choice==5)
       {clrscr();
    f5.seekg((n-1)*sizeof(x),ios::beg);
     f5.read((char*)&x,sizeof(x));
   cout<<"\n"<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
   cout<<"\n";
   cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE/kg"<<"\n";
	for(int i=0;i<10;i++)
	  {cout<<setw(2)<<i+1;
	   cout<<setw(25)<<x.y.item[i]<<setw(20)<<x.y.price[i]<<"\n";}
   f5.close();  }
   else if(choice==6)
  {clrscr();
    f6.seekg((n-1)*sizeof(x),ios::beg);
     f6.read((char*)&x,sizeof(x));
   cout<<"\n"<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
   cout<<"\n";
   cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE/kg"<<"\n";
	for(int i=0;i<10;i++)
	  {cout<<setw(2)<<i+1;
	   cout<<setw(25)<<x.y.item[i]<<setw(20)<<x.y.price[i]<<"\n";}
    f6.close(); }
  else if(choice==7)
  {clrscr();
    f7.seekg((n-1)*sizeof(x),ios::beg);
     f7.read((char*)&x,sizeof(x));
   cout<<"\n"<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
   cout<<"\n";
   cout<<setw(20)<<"ITEM"<<setw(25)<<"PRICE/kg"<<"\n";
	for(int i=0;i<10;i++)
	  {cout<<setw(2)<<i+1;
	   cout<<setw(25)<<x.y.item[i]<<setw(20)<<x.y.price[i]<<"\n";}
    f7.close();    }

   else if(choice==2)
       {clrscr();
 f2.seekg((n-1)*sizeof(x),ios::beg);
     f2.read((char*)&x,sizeof(x));
   cout<<"\n"<<x.name<<"\n"<<x.address<<"\n"<<x.phone;
   cout<<"\n";

	cout<<setw(15)<<"ITEM"<<setw(30)<<"PRICE\n";
	cout<<"\n";
	cout<<setw(40)<<"PERSONAL"<<setw(10)<<"MEDIUM"<<setw(10)<<"LARGE\n";
	for(int i=0;i<10;i++)
	   {cout<<i+1<<".";
	    cout<<setw(25)<<x.y.item[i]<<setw(10)<<x.y.price[i]<<setw(10);
	    cout<<x.y.price[i]+100<<setw(10)<<x.y.price[i]+200<<"\n";
      f2.close();	    }
       cout<<"\nProceed to ordering?\nPress y/n to go back to food outlets ";
       cin>>ch4;
       while(!(ch4=='y'||ch4=='n'))
	{cout<<"Enter y or n";
	 cin>>ch4;}

	  if(ch4=='y')
	       {billp();
	       goto l1;}
	  else if(ch4=='n')
	       {  goto l2;  }
	     }
  cout<<"\nProceed to ordering?\nPress y or n to go back to food outlets ";
  cin>>ch2;
  while(!(ch2=='y'||ch2=='n'))
	{cout<<"Enter y or n";
	 cin>>ch2;}
  if(ch2=='y')
       {bill();
	goto l1;
	}
  else if(ch2=='n')
	goto l2;}
else if (ch1=='n')
	goto l1;
e:
}while (choice!=8);
r1:
getch();}