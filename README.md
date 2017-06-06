# spideralgotask0b
#include<iostream.h>
#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
class stack
{
  int top;
  int data[100];
  public:
  stack()
{
   top=-1;
  }
  void push(int);
  void sell(int);
  void display();
  void sell2(int ,int);
  void sell3(int ,int);
  };

void main()
{
 clrscr();
 int size,ch;
 cout<<"\n                           WELCOME TO JASMINE CURTAIN SHOP";
 cout<<"\n                          ----------------------------------";
 cout<<"\nENTER THE SIZE OF THE STACK\n";
 cin>>size;
 stack s;
 program:
 cout<<"-----------------------------------------------------------------------------";
 cout<<"\nENTER THE CHOICE";
 cout<<"\n1.CURTAIN DETAILS ENTRY";
 cout<<"\n2.CURTAIN SELL";
 cout<<"\n3.CURTAIN DISPLAY";
 cout<<"\n4.EXIT:"<<endl;
 cin>>ch;
 switch(ch)
 {
   case 1:
   s.push(size);
   goto program;

   case 2:
   {
   int a,choice;
   cout<<"\nENTER THE CURTAIN SIZE TO BE CUT(in meters):"<<endl;
   cin>>a;
   cout<<"ENTER THE METHOD OF SELLING"<<endl;
   cout<<"1.idea 1"<<endl;
   cout<<"2.idea 2"<<endl;
   cout<<"3.idea 3"<<endl;
   cin>>choice;
    switch(choice)
    {
     case 1:
     s.sell(a);
     goto program;
     case 2:
     s.sell2(a,size);
     goto program;
     case 3:
     s.sell3(a,size);
     goto program;
     default:
     cout<<"ENTERED WRONG CHOICE"<<endl;
     goto program;
   }
   }
   case 3:
   s.display();
   goto program;

   case 4:
   exit(0);

   default:
   exit(0);


 }
}
 void stack:: push(int size)
 {
    if(top==size-1)
    cout<<"\nSTACK IS FULL";
    else
    {
     for(int i=top;i<=size-2;i++)
     {
     top++;
     cout<<"ENTER "<<top+1<<" CURTAIN SIZE(in meters)"<<":";
     cin>>data[top];
     }
   }
  }
 void stack :: sell(int flag)
 {
  int t =top,check=0;
  if(t==-1)
   cout<<"NO MORE CURTAINS IN THE STACK"<<endl;
  else
  {
    for(int i=t;i>=0;i--)
    {
      if(data[t]>=flag)
       {
	   data[t]=data[t]-flag;
	   check=-1;
	   if(data[t]==0)
	    {
	      for(int i=t;i<top;i++)
	      data[t]=data[t+1];
	      top--;
	     }
	  break;
	}
	t--;
      }
    if (check==0)
    cout<<"THE REQUIRED LENGTH OF CURTAIN IS NOT AVALIABLE"<<endl;
    else
    display();
   }
  }
  void stack :: display()
  {
   int t= top;
   cout<<"--------------------------------------------------------------------------------";
   cout<<"\nTHE CURRENT CURTAINS IN THE STACK";
   if(t<0)
   cout<<"NO MORE CURTAINS IN THE STACK"<<endl;
   while(t>=0)
   {
    cout<<"\n"<<data[t]<<endl;
    t--;
   }
}
 void stack:: sell2(int sellsize,int asize)
 {
   if(top==-1)
   cout<<"NO MORE CURTAINS IN THE STACK"<<endl;
   else
   {
   int temp[100],element,check=0;
   for(int i=0;i<asize;i++)
    {
      temp[i]=data[i];
     }

   for(i=0;i<asize-1;i++)
     {
       for(int j=i+1;j<asize;j++)
	{
	  if(temp[i]>temp[j])
	   {
	    int  a = temp[i];
	    temp[i]=temp[j];
	    temp[j]=a;
	   }
	}
      }
   for(i=0;i<asize;i++)
    {
      if(temp[i]>=sellsize)
      {
      check=-1;
      element=temp[i];
      break;

      }
     }
    for(i=asize-1;i>=0;i--)
      {
       if(data[i]== element)
       break;
      }
      if(check==-1)
      {
      data[i]=data[i]-sellsize;
      if(data[i]==0)
       {
	 for(int j=i;j<top;j++)
	  data[j]=data[j+1];
	  top--;
       }
       display();
       }
  else
  cout<<"THE REQUIRED LENGTH OF CURTAIN IS NOT AVALIABLE"<<endl;


 }
 }
 void stack:: sell3(int sellsize,int asize)
 {
   if(top==-1)
   cout<<"NO MORE CURTAINS IN THE STACK"<<endl;
   else
   {
   int temp[100],element;
   for(int i=0;i<asize;i++)
    {
      temp[i]=data[i];
     }

   for(i=0;i<asize-1;i++)
     {
       for(int j=i+1;j<asize;j++)
	{
	  if(temp[i]>temp[j])
	   {
	    int  a = temp[i];
	    temp[i]=temp[j];
	    temp[j]=a;
	   }
	}
      }
    if(temp[asize-1]<=sellsize)
    cout<<"THE REQUIRED LENGTH OF CURTAIN IS NOT AVALIABLE"<<endl;
    else
    {
      for(i=0;i<asize;i++)
      {
       if(data[i]==temp[asize-1])
       break;
      }

      data[i]=data[i]-sellsize;
      if(data[i]==0)
       {
	 for(int j=i;j<top;j++)
	  data[j]=data[j+1];
	  top--;
       }
  display();

 }
 }
}


