#include <iostream>
#include <conio.h>
#include <stdlib.h>
#include <cstdlib>
#include <string>
using namespace std;



class Users{

    int Fb,Tb,Eb,Rb,pt;
    string name,password,gender;
 	

   public:
    //int present=0;
	   Users():Fb(0),Tb(0),Eb(0),Rb(0),pt(0)
	{}
	void SetP(int p){pt=p;}
    void SetName(string n){name=n;}
    void SetGender(string g){gender=g;}
    void SetPassword(string p){password=p;}

    string Getname(){return name;}
    string GetPassword(){return password;}
    string GetGender(){return gender;}
	int GetP(){return pt;}
	    
	void sumRbBi(int bill){ Fb=Fb+bill;}
	void sumRoombBi(int bill){ Rb=Rb+bill;}
	void sumTbBi(int bill){ Tb=Tb+bill;}
	void sumEbBi(int bill){ Eb=Eb+bill;}

    void GetBill(){
    cout<<"resturant bill "<<Fb<<endl;
    cout<<"taranssport bill "<<Tb<<endl;
    cout<<"event bill "<<Eb<<endl;
    cout<<"room bill "<<Rb<<endl;
	
	
	}
};



int main(){


	
	Users user[10];
    string si,password,username,userpassword,ci;
    int a,i,choice,r,bill=0,n,v;
	

	for(;;){
		system ("CLS");

	cout<<"enter your choice"<<endl;               //this is main menu
	cout<<"0.exit"<<endl;
	cout<<"1.resturant services"<<endl;
    cout<<"2.sign up"<<endl;
	cout<<"\t3.book room"<<endl;
	cout<<"\t4.parking"<<endl;
	cout<<"\t5.event booking"<<endl;
	cout<<"\t6.check out"<<endl;
	cout<<"\t7.my info"<<endl;
    
	
	

	fflush(stdin);
    cin>>choice;
	system ("CLS");
	if(choice>=0&&choice<8)
	{switch(choice)
	{case 2:                                         //sign up
	          for(i=0;i<10;i++)
				{if(user[i].GetP()==0)
				break;}
				if(i<10){
					a=i;
	          cout<<"enter your name"<<endl;
              fflush(stdin);
              cin>>si;
              user[a].SetName(si);
              cout<<"enter your gender"<<endl;
              cin>>ci;
              user[a].SetGender(ci);
              cout<<"enter your password"<<endl;
              fflush(stdin);
              cin>>si;
			  cout<<"\t\t\tyour serial no. is    ---->"<<a<<endl<<"press enter";
			  user[a].SetPassword(si);
	          user[a].SetP(1);
			  getche();
				}
				else{cout<<"no space"<<endl<<"\tpress enter"<<endl;
				getche();break;
				}
	break;
	case 0:abort();break;                               //exit
	case 6:                                            //check out
		for(;;){
			  // system ("CLS");
	          cout<<"enter your serial number"<<endl;
	          cin>>a;
	          if(a<0||a>9)
	          cout<<"invalid serial number"<<endl;
	          else
			  {//fflush(stdin);
	          cout<<"enter you password"<<endl;
	          cin>>password;
	          fflush(stdin);
	          userpassword=user[a].GetPassword();
			  r=userpassword.compare(password);}
	          
	          if(r!=0)
	          {cout<<"your password is'nt correct  "<<endl<<"1.re-enter "<<endl<<"2.exit"<<endl;
			  cin>>choice;
			  if(choice==1)
			  continue;
			  else
			  break;}
				  else{
			  user[a].SetP(0);
			  cout<<"your bill is"<<endl;
			  user[a].GetBill();
			 getche();
			  
			  break;}
				  break;}
		;break;
	case 1:                                             //resturant
		cout<<"Are you booked here?"<<endl;
	          cout<<"press 1 for yes"<<endl<<"press 0 to no"<<endl;
	          cin>>n;
			  if(n==1)
			  {for(;;){
	          cout<<"enter your serial number"<<endl;
	          cin>>a;
	          if(a<0||a>9)
	          cout<<"invalid serial number"<<endl;
			  if(user[a].GetP()==0)cout<<"you have already checked out or not booked"<<endl; 
	          else
			  {//fflush(stdin);
	          cout<<"enter you password"<<endl;
	          cin>>password;
	          fflush(stdin);
	          userpassword=user[a].GetPassword();
			  r=userpassword.compare(password);}
	          
	          if(r!=0)
	          {cout<<"1.re-enter "<<endl<<"2.exit"<<endl;
			  cin>>choice;
			  if(choice==1)
			  continue;
			  else if(choice!=1)break;}
				
				  break;}}


			 
			 if(n==0)
				 bill=0;
			 if(n!=0&&n!=1)
				{ cout<<"invalid entry"<<endl<<"press enter"<<endl;
			     getche();
			 break;}

			  	  for(;;)                               //resturant menu
              { system ("CLS");
	          cout<<"select anyone"<<endl;
              cout<<endl<<"1.appetizers"<<endl;
	          cout<<"2.desi"<<endl;
	          cout<<"3.continental"<<endl;
	          cout<<"4.desserts"<<endl;
              cin>>choice;
	          system ("CLS");
              switch(choice){
			   case 1:
                 for(;;)
                 {system ("CLS");
			     cout<<"1.garlic bread   (100)"<<endl;
			     cout<<"2.juice   (70)"<<endl;
                 cin>>choice;
                 switch(choice)
                 {case 1:
				 if(n==0)
				  bill=bill+100;
				 else
                user[a].sumRbBi(100);
				
			     break;
                 case 2:
					  if(n==0)
				  bill=bill+70;
				 else
			    user[a].sumRbBi(70);
   			     break;}
	    		 system ("CLS");
			   cout<<"more appetizers?"<<endl;
			   //to exit submenu of resturant
		       cout<<endl<<"press 1 for appetizer menu"<<endl<<"press 0 to exit"<<endl;
			   cin>>choice;
                   if(choice==0)
                   {break;}
                   else
                   {continue;}}
			   break;

			   case 2:
               for(;;)
               {system ("CLS");
			   cout<<"1.biryani   (100)"<<endl;
			   cout<<"2.karhai   (70)"<<endl;
               cin>>choice;
               switch(choice)
               {case 1:
			    if(n==0)
				  bill=bill+100;
				 else
              user[a].sumRbBi(100);
               case 2:
				    if(n==0)
				  bill=bill+70;
				 else
			   user[a].sumRbBi(70);}
			   system ("CLS");
			   cout<<"more desi stuff?"<<endl;
			   //to exit submenu of resturant
		       cout<<endl<<"press 1 for desi food menu"<<endl<<"press 0 to exit"<<endl;
			   cin>>choice;
                   if(choice==0)
                   {break;}
                   else
                   {continue;}
			   }
		       break;

			   case 3:
               for(;;)
               {system ("CLS");
			   cout<<"1.chineese   (100)"<<endl;
			   cout<<"2.italian   (70)"<<endl;
               cin>>choice;
               switch(choice)
               {case 1:
			    if(n==0)
				  bill=bill+100;
				 else
              user[a].sumRbBi(100);
               case 2:
				    if(n==0)
				  bill=bill+70;
				 else
			  user[a].sumRbBi(70);}
			   system ("CLS");
			   cout<<"more continental stuff?"<<endl;
			   //to exit submenu of resturant
		       cout<<endl<<endl<<"press 1 for continental food menu"<<endl<<"press 0 to exit"<<endl;
			   cin>>choice;
                   if(choice==0)
                   {break;}
                   else
                   {continue;}
			   }
		       break;

			   case 4:
               for(;;)
               {system ("CLS");
			   cout<<"1.custard   (100)"<<endl;
			   cout<<"2.cake   (70)"<<endl;
               cin>>choice;
               switch(choice)
               {case 1:
			    if(n==0)
				  bill=bill+100;
				 else
               user[a].sumRbBi(100);
               case 2:
				    if(n==0)
				  bill=bill+70;
				 else
			   user[a].sumRbBi(70);}
			   system ("CLS");
			   cout<<"more desserts stuff?"<<endl;
			   //to exit submenu of resturant
		       cout<<endl<<"press 1 for desserts menu"<<endl<<"press 0 to exit"<<endl;
			   cin>>choice;
                   if(choice==0)
                   {break;}
                   else
                   {continue;}
			        }
		            break;

			  default:
			  system ("CLS");
			  cout<<"you entered invalid option";
			  break;}
		  
		       //for exit main menu of resturant
			   system ("CLS");
			   cout<<"food?"<<endl;
		       cout<<endl<<"press 1 for main food menu"<<endl<<"press 0 to exit"<<endl;
			   cin>>choice;
                   if(choice==0)
                   {if(n==0)
				   {cout<<bill<<endl;
				   cout<<"press enter"<<endl;
				   getche();break;}
				   break;}
                   else
                   {continue;}
		   }

		break;
	   case 3:
		                                      //book room

		   cout<<"Are you booked here?"<<endl;
	          cout<<"press 1 for yes"<<endl<<"press 0 to no"<<endl;
	          cin>>n;
			  if(n==1)
			  {for(;;){
	          cout<<"enter your serial number"<<endl;
	          cin>>a;
	          if(a<0||a>9)
	          cout<<"invalid serial number"<<endl;
			  if(user[a].GetP()==0)cout<<"you have already checked out or not booked"<<endl; 
	          else
			  {//fflush(stdin);
	          cout<<"enter you password"<<endl;
	          cin>>password;
	          fflush(stdin);
	          userpassword=user[a].GetPassword();
			  r=userpassword.compare(password);}
	          
	          if(r!=0)
	          {cout<<"1.re-enter "<<endl<<"2.exit"<<endl;
			  cin>>choice;
			  if(choice==1)
			  continue;
			 else if(choice!=1)break;}
				
				  break;}}
			   else {cout<<"you've to sign up first"<<endl<<"press enter"<<endl;getche();break;}



		     system ("CLS");
                   cout<<"enter the type of room"<<endl;
                   cout<<"1.luxury   (11,000 per day)"<<endl<<"2.standard   (8,000 per day)"<<endl<<"3.double   (15,000 per day)"<<endl;
                   cin>>choice;
				   system ("CLS");
                   switch(choice)
                   {case 1:
                   cout<<"your luxury room has been booked enjoy!"<<endl;
                   user[a].sumRoombBi(12000);
                   break;
                   case 2:
                   cout<<"your standard room has been booked enjoy!"<<endl;
                   user[a].sumRoombBi(9000);
                   break;
                   case 3:
                   cout<<"your double room has been booked enjoy!"<<endl;
                   user[a].sumRoombBi(16000);
                   break;
                   default:
                   cout<<"ERROR!!!"<<endl;
                   break;}
				   break;
		     break;
	case 4:                                //parking
		
		cout<<"Are you booked here?"<<endl;
	          cout<<"press 1 for yes"<<endl<<"press 0 to no"<<endl;
	          cin>>n;
			  if(n==1)
			  {for(;;){
	          cout<<"enter your serial number"<<endl;
	          cin>>a;
	          if(a<0||a>9)
	          cout<<"invalid serial number"<<endl;
			  if(user[a].GetP()==0)cout<<"you have already checked out or not booked"<<endl; 
	          else
			  {//fflush(stdin);
	          cout<<"enter you password"<<endl;
	          cin>>password;
	          fflush(stdin);
	          userpassword=user[a].GetPassword();
			  r=userpassword.compare(password);}
	          
	          if(r!=0)
	          {cout<<"1.re-enter "<<endl<<"2.exit"<<endl;
			  cin>>choice;
			  if(choice==1)
			  continue;
			  else if(choice!=1)break;}
				
				  break;}}
			  else { system ("CLS");cout<<"you've to sign up first"<<endl<<"press enter"<<endl;getche();break;}


			 // system ("CLS");
                   cout<<"enter the no. of vehicals (100 per day)"<<endl;
                   cin>>v;
                   user[a].sumTbBi(v*100);
                   break;


		break;
	case 5:
		                         //events

		cout<<"Are you booked here?"<<endl;
	          cout<<"press 1 for yes"<<endl<<"press 0 to no"<<endl;
	          cin>>n;
			  if(n==1)
			  {for(;;){
	          cout<<"enter your serial number"<<endl;
	          cin>>a;
	          if(a<0||a>9)
	          cout<<"invalid serial number"<<endl;
			  if(user[a].GetP()==0)cout<<"you have already checked out or not booked"<<endl; 
	          else
			  {//fflush(stdin);
	          cout<<"enter you password"<<endl;
	          cin>>password;
	          fflush(stdin);
	          userpassword=user[a].GetPassword();
			  r=userpassword.compare(password);}
	          
	          if(r!=0)
	          {cout<<"1.re-enter "<<endl<<"2.exit"<<endl;
			  cin>>choice;
			  if(choice==1)
			  continue;
			  else if(choice!=1)break;}
				
				  break;}}
			  else {cout<<"you've to sign up first"<<endl<<"press enter"<<endl;getche();break;}

			   system ("CLS");
                   cout<<"enter the type of event"<<endl;
                   cout<<"1.birthdays   (75,000)"<<endl<<"2.marriage functions   (150,000)"<<endl<<"3.seminars   (65,000)"<<endl;
                   cin>>choice;
                   cout<<"catering services"<<endl<<"enter number of people   (350 per head)"<<endl;
                   cin>>n;
                   switch(choice)
                   {case 1:
				   system ("CLS");
                   cout<<"your birthday event has been booked enjoy!"<<endl;
                   user[a].sumEbBi(n*350+75000);
                   break;
                   case 2:
				   system ("CLS");
                   cout<<"your marriage function has been booked enjoy!"<<endl;
                   user[a].sumEbBi(n*350+150000);
                   break;
                   case 3:
				   system ("CLS");
                   cout<<"your seminar has been booked enjoy!"<<endl;
                   user[a].sumEbBi(n*350+75000);
                   break;
                   default:
					   system ("CLS");
                   cout<<"ERROR!!!"<<endl;
                   break;}

				   

		break;
	case 7:                                    //my info
		system ("CLS");
		cout<<"Are you booked here?"<<endl;
	          cout<<"press 1 for yes"<<endl<<"press 0 to no"<<endl;
	          cin>>n;
			  if(n==1)
			  {for(;;){
	          cout<<"enter your serial number"<<endl;
	          cin>>a;
	          if(a<0||a>9)
	          cout<<"invalid serial number"<<endl;
			  if(user[a].GetP()==0){cout<<"you have already checked out or not booked"<<endl;
			  }
	          else
			  {//fflush(stdin);
	          cout<<"enter you password"<<endl;
	          cin>>password;
	          fflush(stdin);
	          userpassword=user[a].GetPassword();
			  r=userpassword.compare(password);
	          
			  break;}

	          if(r!=0)
	          {cout<<"1.re-enter "<<endl<<"2.exit"<<endl;
			  cin>>choice;
			  if(choice==1)
			  continue;
			  else if(choice!=1)break;}
				
				  break;} }
			  else {cout<<"you've to sign up first"<<endl<<"press enter"<<endl;getche();break;}
			  cout<<"Name: "<<user[a].Getname()<<endl;
			   cout<<"gender: "<<user[a].GetGender()<<endl;
			   cout<<"serial number: "<<a<<endl;
			   cout<<"password: "<<user[a].GetPassword()<<endl;
			  cout<<"press any key to exit"<<endl;
			  getche();
			  break;

	default : cout<<"default";break;}
	}
	else {cout<<endl<<"re-enter"<<endl;
	getche();
	continue;}

	}
	//switch(choice)
	//{}
	//int result = system("C:\\Program Files\\Program.exe");
}

