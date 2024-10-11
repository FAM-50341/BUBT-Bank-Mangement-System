#include<stdio.h>
#include<stdlib.h>
#include<windows.h>
#include <errno.h>
#include<conio.h>
int i,j;
int main_exit;
void menu();
struct date{
 int month,day,year;
 };
struct {
 char name[60],st_name[20];
 int cl_pass,st_id;
 int acc_no,age ,n_id;
 char address[60];
 char citizenship[15];
 double phone;
 char acc_type[10];
 float amt;
 float amtt ;
 struct date dob;
 struct date deposit; 
struct date withdraw;
 }add,upd,check,rem,chacount,chpersonal,transaction,stpaym;
float interest(float t,float amount,int rate)
{
 float SI;
 SI=(rate*t*amount)/100.0;
 return (SI);
}
void fordelay(int j)
{ int i,k ;
 for(i=0;i<j;i++)
 k=i;
}
void stupay(void)
{
 int test=0,rate;
 float time;
 float intrst;
 int choice;
 FILE *old,*newrec;
 old=fopen("mainfile.txt","r");
 newrec=fopen("new.txt","w");
 printf("\n\n\t\tEnter the account no:");
scanf("%d",&stpaym.acc_no);
 printf("\t\tEnter the Pasword:");
 scanf("%d",&stpaym.cl_pass);
 while (fscanf(old,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&ad
d.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit.
day,&add.deposit.year)!=EOF)
 {
 if((add.acc_no==stpaym.acc_no)&&(add.cl_pass==stpaym.cl_pass))
 { test=1;
 system("cls");
 
if(strcmpi(add.acc_type,"fixed1")==0||strcmpi(add.acc_type,"fixed2")==0||strcmpi(add.acc_type,"fixe
d3")==0)
 {
 printf("\a\a\a\n\n\n\t\tYOU CANNOT DEPOSIT OR WITHDRAW CASH IN FIXED 
ACCOUNTS!!!!!");
 fordelay(1000000000);
 system("cls");
 main();
 }
 printf("\n\n\t\tDo you want to\n\t\t1.Pay\n\t\t2.Exit?\n\n\t\tEnter your choice:");
 scanf("%d",&choice);
 if (choice==1)
 {
 system("cls");
 printf("\n\n\t\tEnter the amount you want to Pay:$ ");
 scanf("%f",&stpaym.amt);
 add.amt-=stpaym.amt;
fprintf(newrec,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.age
,add.address,add.citizenship,add.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.d
eposit.year);
 printf("\n\n\t\tPayment successfully!");
 printf("\n\t\tYour current balance is :$ %.2f\n\n",add.amt);
 }
 else
 {
 system("cls");
 close();
 }
 }
 else
 {
 fprintf(newrec,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.age
,add.address,add.citizenship,add.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.d
eposit.year);
 }
 }
 fclose(old);
 fclose(newrec);
 remove("mainfile.txt");
 rename("new.txt","mainfile.txt");
 if(test!=1)
 {
 printf("\n\n\t\tRecord not found!!");
 transact_invalid:
 printf("\n\n\n\t\tEnter 0 to try again,1 to return to main menu and 2 to exit:"); 
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==0)
 stupay(); //transact();
 else if (main_exit==1)
 user();
 else if (main_exit==2)
 close();
 else
 {
 printf("\n\n\t\tInvalid!");
 goto transact_invalid;
 }
 }
 else
 {
 printf("\n\t\tEnter 1 to go to the main menu and 0 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 user();
 else
 close();
 }
}
void ch_account()
{
 int test=0,rate;
 int choice,st_id,st_amount;
 char st_name ,inform;
 float time;
 float intrst;
 FILE *old,*newrec;
 old=fopen("mainfile.txt","r");
 printf("\n\n\t\tEnter the account no :");
 scanf("%d",&chacount.acc_no);
 printf("\t\tEnter the Password :");
 scanf("%d",&chacount.cl_pass);
 while (fscanf(old,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&ad
d.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit.
day,&add.deposit.year)!=EOF)
 {
 if((add.acc_no==chacount.acc_no)&&(add.cl_pass==chacount.cl_pass))
 { system("cls");
 test=1;
 printf("\n\n\t\t\tYour Account Information \n\n");
 printf("\n\t\tType Of Account :%s ",add.acc_type);
printf("\n\t\tAmount deposited :$ %.2f",add.amt);
 printf("\n\t\tDate Of Deposit 
:%d/%d/%d\n\n",add.deposit.month,add.deposit.day,add.deposit.year);
 if(strcmpi(add.acc_type,"fixed1")==0)
 {
 time=1.0;
 rate=9;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $%.2f as interest on 
%d/%d/%d",intrst,add.deposit.month,add.deposit.day,add.deposit.year+1);
 }
 else if(strcmpi(add.acc_type,"fixed2")==0)
 {
 time=2.0;
 rate=11;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $.%.2f as interest on 
%d/%d/%d",intrst,add.deposit.month,add.deposit.day,add.deposit.year+2);
 }
 else if(strcmpi(add.acc_type,"fixed3")==0)
 {
 time=3.0;
 rate=13;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $.%.2f as interest on 
%d/%d/%d",intrst,add.deposit.month,add.deposit.day,add.deposit.year+3);
 }
 else if
(strcmpi(add.acc_type,"saving")==0)
{
 time=(1.0/12.0);
 rate=8;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $.%.2f as interest on %d of every 
month",intrst,add.deposit.day);
 }
 else if(strcmpi(add.acc_type,"current")==0)
 {
 printf("\n\n\t\tYou will get no interest\a\a");
 }
 }
 }
 fclose(old);
 if(test!=1)
 {
 printf("\n\n\t\tRecord not found!!");
 ch_account_invalid:
 printf("\n\n\n\t\tEnter 0 to try again,1 to return to main menu and 2 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==0)
 ch_account();
 else if (main_exit==1)
user();
 else if (main_exit==2)
 close();
 else
 {
 printf("\n\t\tInvalid!");
 goto ch_account_invalid;
 }
 }
 else
 {
 printf("\n\n\t\tEnter 1 to go to the User Menu and 0 to Exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 user();
 else
 close();
 }
}
void ch_personal()
{
 FILE *old,*newrec;
 int test=0,rate;
int choice,st_id,st_amount;
 char st_name ,inform;
 float time;
 float intrst;
 old=fopen("mainfile.txt","r");
 printf("\n\n\t\tEnter the account no :");
 scanf("%d",&chpersonal.acc_no);
 printf("\t\tEnter the Password :");
 scanf("%d",&chpersonal.cl_pass);
 while (fscanf(old,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&ad
d.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit.
day,&add.deposit.year)!=EOF)
 {
 if((add.acc_no==chpersonal.acc_no)&&(add.cl_pass==chpersonal.cl_pass))
 {
 system("cls");
 test=1;
 printf("\n \t\t\t Your Personal Information \n\n");
 printf("\n\t\tAccount NO. :%d",add.acc_no);
 printf("\n\t\tAccount pass :%d",add.cl_pass);
 printf("\n\t\tName :%s",add.name);
 printf("\n\t\tDOB 
:%d/%d/%d",add.dob.month,add.dob.day,add.dob.year);
 printf("\n\t\tNID :%d",add.n_id);
 printf("\n\t\tAge :%d",add.age);
 printf("\n\t\tAddress :%s",add.address);
 printf("\n\t\tCitizenship No :%s",add.citizenship);
printf("\n\t\tPhone number :0%.0lf",add.phone);
 }
 }
 fclose(old);
 if(test!=1)
 {
 printf("\n\n\t\tRecord not found!!");
 ch_personal_invalid:
 printf("\n\n\n\t\tEnter 0 to try again,1 to return to User login menu and 2 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==0)
 ch_personal();
 else if (main_exit==1)
 user();
 else if (main_exit==2)
 close();
 else
 {
 printf("\n\t\tInvalid!");
 goto ch_personal_invalid;
 }
 }
 else
{
 printf("\n\n\t\tEnter 1 to go to the User login Menu and 0 to Exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 user();
 else
 close();
 }
}
void user(void)
{
 int test=0,rate;
 int choice,st_id,st_amount;
 char st_name ,inform ;
 float time;
 float intrst;
 FILE *old,*newrec;
 old=fopen("mainfile.txt","r");
 printf("\n\n\t\tDo you want to log in by \n\n");
 printf("\n\t\t 1.Account no ");
 printf("\n\t\t 2.user Name ");
printf("\n\t\t 3.Exit\n");
 printf("\n\t\t Enter your choice: ");
 scanf("%d",&choice);
 if (choice==1)
 {
 system("cls");
 printf("\n\n\t\tEnter the account number:");
 scanf("%d",&check.acc_no);
 printf("\t\tEnter your pasward :");
 scanf("%d",&check.cl_pass);
 while (fscanf(old,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,&add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&a
dd.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit
.day,&add.deposit.year)!=EOF)
 {
 if((add.acc_no==check.acc_no)&&(add.cl_pass==check.cl_pass))
 {
 system("cls");
 test=1;
 printf("\n\n\t\tDo you want to \n");
 printf("\n\t\t1.Check Your personal Information");
 printf("\n\t\t2.check Your Account Information ");
 printf("\n\t\t3.Pay your tution Fees ");
 printf("\n\t\t4.Exit \n\n");
 printf("\n\t\tEnter your choice :");
 scanf("%d",&inform);
system("cls");
 switch(inform)
 {
 case 1:ch_personal();
 break;
 case 2:ch_account();
 break;
 case 3:stupay();
 break ;
 case 4:close () ;
 break;
 }
 }
 }
 }
 else if (choice==2)
 {
 system("cls");
 printf("\n\n\t\tEnter the name:");
 scanf("%s",&check.name);
 printf("\t\tEnter the pasward:");
 scanf("%d",&check.cl_pass);
 while (fscanf(old,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,&add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&a
dd.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit
.day,&add.deposit.year)!=EOF)
 {
//if(strcmpi(add.name,check.name)==0 && (add.cl_pass,check.cl_pass))
 if((strcmpi(add.name,check.name)==0)&&(add.cl_pass==check.cl_pass))
 {
 test=1;
 system("cls");
 printf("\n\n\t\tDo you want to \n");
 printf("\n\t\t1.Check Your personal Information");
 printf("\n\t\t2.check Your Account Information ");
 printf("\n\t\t3.Pay your tution Fees ");
 printf("\n\t\t4.Exit \n\n");
 printf("\n\t\tEnter your choice :");
 scanf("%d",&inform);
 system("cls");
 switch(inform)
 {
 case 1:ch_personal();
 break;
 case 2:ch_account();
 break;
 case 3:stupay();
 break ;
 case 4:close () ;
 break;
 }
}
 }
 }
 else
 {
 //system("cls");
 close();
 }
 fclose(old);
 if(test!=1)
 {
 printf("\n\n\t\tRecord not found!!");
 ch_personal_invalid:
 printf("\n\n\n\t\tEnter 0 to try again,1 to return to Main Menu and 2 to Exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==0)
 user();
 else if (main_exit==1)
 main();
 else if (main_exit==2)
 close();
 else
 {
printf("\n\t\tInvalid!");
 goto ch_personal_invalid;
 }
 }
 else
 {
 printf("\n\n\t\tEnter 1 to go to the User Menu and 0 to Exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 main();
 else
 close();
 }
return 0 ;
}
void erase(void)
{
 FILE *old,*newrec;
 int test=0;
 old=fopen("mainfile.txt","r");
 newrec=fopen("new.txt","w");
 printf("\n\n\t\tFor account deletion \n\t\tEnter the account no.:");
scanf("%d",&rem.acc_no);
 while (fscanf(old,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&ad
d.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit.
day,&add.deposit.year)!=EOF)
 {
 if(add.acc_no!=rem.acc_no)
 fprintf(newrec,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.age
,add.address,add.citizenship,add.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.d
eposit.year);
 else
 {test++;
 printf("\n\t\tRecord deleted successfully!\n");
 }
 }
 fclose(old);
 fclose(newrec);
 remove("mainfile.txt");
 rename("new.txt","mainfile.txt");
 if(test!=1)
 {
 printf("\n\t\tRecord not found!!\a\a\a");
 erase_invalid:
 printf("\n\t\tEnter 0 to try again,1 to return to main menu and 2 to exit:");
 scanf("%d",&main_exit);
 if (main_exit==1)
 menu();
 else if (main_exit==2)
 close();
 else if(main_exit==0)
erase();
 else
 {printf("\nInvalid!\a");
 goto erase_invalid;}
 }
 else
 {printf("\n\t\tEnter 1 to go to the main menu and 0 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 menu();
 else
 close();
 }
}
void transact(void)
{
 int choice,test=0;
 FILE *old,*newrec;
 old=fopen("mainfile.txt","r");
 newrec=fopen("new.txt","w");
 printf("\n\n\t\tEnter the account no. of the customer:");
 scanf("%d",&transaction.acc_no);
 while (fscanf(old,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&ad
d.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit.
day,&add.deposit.year)!=EOF)
{
 if(add.acc_no==transaction.acc_no)
 { test=1;
 
if(strcmpi(add.acc_type,"fixed1")==0||strcmpi(add.acc_type,"fixed2")==0||strcmpi(add.acc_type,"fixe
d3")==0)
 {
 printf("\a\a\a\n\n\t\tYOU CANNOT DEPOSIT OR WITHDRAW CASH IN FIXED 
ACCOUNTS!!!!!");
 fordelay(1000000000);
 system("cls");
 menu();
 }
 printf("\n\n\t\tDo you want to\n\t\t1.Deposit\n\t\t2.Withdraw?\n\n\t\tEnter your 
choice:");
 scanf("%d",&choice);
 if (choice==1)
 {
 printf("\n\t\tEnter the amount you want to deposit:$ ");
 scanf("%f",&transaction.amt);
 add.amt+=transaction.amt;
 fprintf(newrec,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.age
,add.address,add.citizenship,add.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.d
eposit.year);
 printf("\n\n\t\tDeposited successfully!");
 printf("\n\t\tYour current balance is :$ %.2f",add.amt);
 }
 else
 {
 printf("\n\t\tEnter the amount you want to withdraw:$ ");
scanf("%f",&transaction.amt);
 add.amt-=transaction.amt;
 fprintf(newrec,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.age
,add.address,add.citizenship,add.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.d
eposit.year);
 printf("\n\n\t\tWithdrawn successfully!");
 printf("\n\t\tYour current balance is :$ %.2f",add.amt);
 }
 }
 else
 {
 fprintf(newrec,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.age
,add.address,add.citizenship,add.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.d
eposit.year);
 }
 }
 fclose(old);
 fclose(newrec);
 remove("mainfile.txt");
 rename("new.txt","mainfile.txt");
 if(test!=1)
 {
 printf("\n\n\t\tRecord not found!!");
 transact_invalid:
 printf("\n\n\n\t\tEnter 0 to try again,1 to return to main menu and 2 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==0)
 transact();
else if (main_exit==1)
 menu();
 else if (main_exit==2)
 close();
 else
 {
 printf("\n\t\tInvalid!");
 goto transact_invalid;
 }
 }
 else
 {
 printf("\n\n\t\tEnter 1 to go to the main menu and 0 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 menu();
 else
 close();
 }
}
void edit(void)
{
 int choice,test=0;
 FILE *old,*newrec;
old=fopen("mainfile.txt","r");
 newrec=fopen("new.txt","w");
 printf("\n\t\twhose information you want to change!!");
 printf("\n\n\t\tEnter the account no.:");
 scanf("%d",&upd.acc_no);
 while(fscanf(old,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&ad
d.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit.
day,&add.deposit.year)!=EOF)
 {
 if (add.acc_no==upd.acc_no)
 { test=1;
 printf("\n\t\tWhich information do you want to 
change?\n\t\t1.Address\n\t\t2.Phone\n\t\tEnter your choice:");
 scanf("%d",&choice);
 system("cls");
 if(choice==1)
 {printf("\n\n\t\tEnter the new address:");
 scanf("%s",upd.address);
 fprintf(newrec,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,&add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.ag
e,upd.address,add.citizenship,add.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.
deposit.year);
 system("cls");
 printf("\n\n\t\tChanges saved!");
 }
 else if(choice==2)
 {
 printf("\t\tEnter the new phone number:");
 scanf("%lf",&upd.phone);
fprintf(newrec,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.age
,add.address,add.citizenship,upd.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.d
eposit.year);
 system("cls");
 printf("\n\n\t\tChanges saved!");
 }
 }
 else
 fprintf(newrec,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.age
,add.address,add.citizenship,add.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.d
eposit.year);
 }
 fclose(old);
 fclose(newrec);
 remove("mainfile.txt");
 rename("new.txt","mainfile.txt");
if(test!=1)
 { system("cls");
 printf("\n\t\tRecord not found!!\a\a\a");
 edit_invalid:
 printf("\n\t\tEnter 0 to try again,1 to return to main menu and 2 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 menu();
 else if (main_exit==2)
 close();
else if(main_exit==0)
 edit();
 else
 {printf("\n\t\tInvalid!\a");
 goto edit_invalid;}
 }
 else
 {printf("\n\n\n\t\tEnter 1 to go to the main menu and 0 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 menu();
 else
 close();
 }
}
void close(void)
{
 printf("\n\n\n\n\t\tThis C Mini Project is developed by Code With \n\n \t\tERROR!!! Team!");
 printf("\n\n\n\t\tEnter 1 to go to the Log in menu and 2 to go to Exit:");
 scanf("%d",&main_exit);
 if (main_exit==1)
 {
 system("cls");
 main();//menu
 }
else
 {
 system("cls");
 printf("\n\n\t\tThe End!!!\n\n");
 return 0;
 }
}
void view_list()
{
 FILE *view;
 view=fopen("mainfile.txt","r");
 int test=0;
 system("cls");
 printf("\nAccount No.\tClaint Name\t\tNational ID\t\tClaint Address\t\tMobail Number\n");
 while(fscanf(view,"%d %s %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,&add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&a
dd.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit
.day,&add.deposit.year)!=EOF)
 {
 
printf("\n%6d\t\t%10s\t\t%10d\t\t%10s\t\t0%.0lf",add.acc_no,add.name,add.n_id,add.address,add.phone
);
 test++;
 }
fclose(view);
 if (test==0)
 { system("cls");
 printf("\nNO RECORDS!!\n");}
 view_list_invalid:
 printf("\n\n\nEnter 1 to go to the main menu and 0 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 menu();
 else if(main_exit==0)
 close();
 else
 {
 printf("\nInvalid!\a");
 goto view_list_invalid;
 }
}
void see(void)
{
 FILE *ptr;
 int test=0,rate;
 int choice;
 float time;
 float intrst;
 ptr=fopen("mainfile.txt","r");
printf("\n\n\t\tDo you want to check by\n\t\t1.Account no\n\t\t2.Name\n\t\tEnter your 
choice:");
 scanf("%d",&choice);
 if (choice==1)
 {
 printf("\t\tEnter the account number:");
 scanf("%d",&check.acc_no);
 while (fscanf(ptr,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,&add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&a
dd.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit
.day,&add.deposit.year)!=EOF)
 {
 if(add.acc_no==check.acc_no)
 { system("cls");
 test=1;
 printf("\n\n\t\t\tUser Information");
 printf("\n\n\t\tAccount NO. :%d",add.acc_no);
 printf("\n\t\tPassward :%d",add.cl_pass);
 printf("\n\t\tName :%s",add.name);
 printf("\n\t\tDOB 
:%d/%d/%d",add.dob.month,add.dob.day,add.dob.year);
 printf("\n\t\tNID :%d",add.n_id);
 printf("\n\t\tAge :%d",add.age);
 printf("\n\t\tAddress :%s",add.address);
 printf("\n\t\tCitizenship No :%s",add.citizenship);
 printf("\n\t\tPhone number :%.0lf",add.phone);
 printf("\n\n\t\tDo you want to check ?\n\n\t\t1.Account Details \n\t\t2.Menu 
\n\t\t3.Exit \n\n\t\tEnter your Option :");
scanf("%d",&choice);
 if(choice==1)
 {
 system("cls");
 printf("\n\n\t\t\t Your Account Information ");
 printf("\n\n\t\tType Of Account :%s ",add.acc_type);
 printf("\n\t\tAmount deposited :$ %.2f",add.amt);
 printf("\n\t\tDate Of Deposit 
:%d/%d/%d\n\n",add.deposit.month,add.deposit.day,add.deposit.year);
 if(strcmpi(add.acc_type,"fixed1")==0)
 {
 time=1.0;
 rate=9;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $%.2f as interest on 
%d/%d/%d",intrst,add.deposit.month,add.deposit.day,add.deposit.year+1);
 }
 else if(strcmpi(add.acc_type,"fixed2")==0)
 {
 time=2.0;
 rate=11;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $.%.2f as interest on 
%d/%d/%d",intrst,add.deposit.month,add.deposit.day,add.deposit.year+2);
 }
 else if(strcmpi(add.acc_type,"fixed3")==0)
 {
 time=3.0;
 rate=13;
intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $.%.2f as interest on 
%d/%d/%d",intrst,add.deposit.month,add.deposit.day,add.deposit.year+3);
 }
 else if(strcmpi(add.acc_type,"saving")==0)
 {
 time=(1.0/12.0);
 rate=8;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $.%.2f as interest on %d of every 
month",intrst,add.deposit.day);
 }
 else if(strcmpi(add.acc_type,"current")==0)
 {
 printf("\n\n\t\tYou will get no interest\a\a");
 }
 }
 else if (choice==2)
 {
 system("cls");
 menu();
 }
 else
 {
system("cls");
 close();
 }
 }
 }
 }
 else if (choice==2)
 {
 printf("\t\tEnter the name:");
 scanf("%s",check.name);
 while (fscanf(ptr,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d",&add.acc_no,&add.cl_pass,&add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,&a
dd.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.deposit
.day,&add.deposit.year)!=EOF)
 {
 if(strcmpi(add.name,check.name)==0)
 { system("cls");
 test=1;
 printf("\n\n\t\t\tUser Information");
 printf("\n\n\t\tAccount NO. :%d",add.acc_no);
 printf("\n\t\tPassward :%d",add.cl_pass);
 printf("\n\t\tName :%s",add.name);
 printf("\n\t\tDOB 
:%d/%d/%d",add.dob.month,add.dob.day,add.dob.year);
 printf("\n\t\tNID :%d",add.n_id);
 printf("\n\t\tAge :%d",add.age);
 printf("\n\t\tAddress :%s",add.address);
 printf("\n\t\tCitizenship No :%s",add.citizenship);
 printf("\n\t\tPhone number :%.0lf",add.phone);
printf("\n\n\t\tDo you want to check ?\n\t\t1. Account Details \n\t\t2. Exit 
\n\t\tEnter your Option :");
 scanf("%d",&choice);
 if(choice==1)
 {
 system("cls");
 printf("\n\n\t\t Your Account information");
 printf("\n\n\t\tType Of Account :%s ",add.acc_type);
 printf("\n\t\tAmount deposited :$ %.2f",add.amt);
 printf("\n\t\tDate Of Deposit 
:%d/%d/%d\n\n",add.deposit.month,add.deposit.day,add.deposit.year);
 if(strcmpi(add.acc_type,"fixed1")==0)
 {
 time=1.0;
 rate=9;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $%.2f as interest on 
%d/%d/%d",intrst,add.deposit.month,add.deposit.day,add.deposit.year+1);
 }
 else if(strcmpi(add.acc_type,"fixed2")==0)
 {
 time=2.0;
 rate=11;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $.%.2f as interest on 
%d/%d/%d",intrst,add.deposit.month,add.deposit.day,add.deposit.year+2);
 }
 else if(strcmpi(add.acc_type,"fixed3")==0)
 {
time=3.0;
 rate=13;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $.%.2f as interest on 
%d/%d/%d",intrst,add.deposit.month,add.deposit.day,add.deposit.year+3);
 }
 else if(strcmpi(add.acc_type,"saving")==0)
 {
 time=(1.0/12.0);
 rate=8;
 intrst=interest(time,add.amt,rate);
 printf("\n\n\t\tYou will get $.%.2f as interest on %d of every 
month",intrst,add.deposit.day);
 }
 else if(strcmpi(add.acc_type,"current")==0)
 {
 printf("\n\n\t\tYou will get no interest\a\a");
 }
 }
 else if (choice==2)
 {
 system("cls");
 close();
 }
}
 }
 }
 fclose(ptr);
 if(test!=1)
 { system("cls");
 printf("\n\t\tRecord not found!!\a\a\a");
 see_invalid:
 printf("\n\t\tEnter 0 to try again,1 to return to main menu and 2 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 menu();
 else if (main_exit==2)
 close();
 else if(main_exit==0)
 see();
 else
 {
 system("cls");
 printf("\nInvalid!\a");
 goto see_invalid;}
 }
 else
 {
printf("\n\t\tEnter 1 to go to the main menu and 0 to exit:");
scanf("%d",&main_exit);}
 if (main_exit==1)
 {
 system("cls");
 menu();
 }
 else
 {
 system("cls");
 close();
 }
}
void new_acc()
{
 int choice;
 FILE *ptr;
 ptr=fopen("mainfile.txt","a+");
 account_no:
 system("cls");
 printf("\n\t\t\t\xB2\xB2\xB2\ ADD RECORD \xB2\xB2\xB2\xB2");
 printf("\n\n\t\tEnter today's date(mm/dd/yyyy):");
 scanf("%d/%d/%d",&add.deposit.month,&add.deposit.day,&add.deposit.year);
 printf("\n\t\tEnter the account number:");
 scanf("%d",&check.acc_no);
%d/%d/%d\n",&add.acc_no,&add.cl_pass,&add.name,&add.n_id,&add.dob.month,&add.dob.day,&add.dob.year,
&add.age,add.address,add.citizenship,&add.phone,add.acc_type,&add.amt,&add.deposit.month,&add.depos
it.day,&add.deposit.year)!=EOF)
 {
 if (check.acc_no==add.acc_no)
 {printf("\n\t\tAccount no. already in use!");
 fordelay(10000000);
 goto account_no;
 }
 }
 add.acc_no=check.acc_no;
 printf("\n\t\tSet User pasword:");
 scanf("%d",&add.cl_pass);
 printf("\n\t\tEnter User name:");
 scanf("%s",add.name);
 printf("\n\t\tEnter your National Id:");
 scanf("%d",&add.n_id);
 printf("\n\t\tEnter the date of birth(mm/dd/yyyy):");
 scanf("%d/%d/%d",&add.dob.month,&add.dob.day,&add.dob.year);
 printf("\n\t\tEnter the age:");
 scanf("%d",&add.age);
 printf("\n\t\tEnter the address:");
 scanf("%s",add.address);
 printf("\n\t\tEnter the citizenship number:");
 scanf("%s",add.citizenship);
 printf("\n\t\tEnter the phone number:");
 scanf("%lf",&add.phone);
 printf("\n\t\tEnter the amount to deposit:$");
scanf("%f",&add.amt);
 printf("\n\t\tType of account:\n\t\t\t#Saving\n\t\t\t# Current\n\t\t\t# Fixed1(for 1 
year)\n\t\t\t# Fixed2(for 2 years)\n\t\t\t# Fixed3(for 3 years)\n\n\t\t\tEnter your choice:");
 scanf("%s",add.acc_type);
 fprintf(ptr,"%d %d %s %d %d/%d/%d %d %s %s %lf %s %f 
%d/%d/%d\n",add.acc_no,add.cl_pass,add.name,add.n_id,add.dob.month,add.dob.day,add.dob.year,add.age
,add.address,add.citizenship,add.phone,add.acc_type,add.amt,add.deposit.month,add.deposit.day,add.d
eposit.year);
 fclose(ptr);
 printf("\n\t\t\tAccount created successfully!");
 add_invalid:
 printf("\n\n\n\t\t\tEnter 1 to go to the main menu and 0 to exit:");
 scanf("%d",&main_exit);
 system("cls");
 if (main_exit==1)
 menu();
 else if(main_exit==0)
 close();
 else
 {
 printf("\n\t\tInvalid!\a");
 goto add_invalid;
 }
}
void menu(void)
{
 int choice;
system("cls");
 system("color 9");
 //textcolor(RED);
 printf("\n\n\t\t\tCUSTOMER ACCOUNT BANK MANAGEMENT SYSTEM");
 printf("\n\n\n\t\t\t\xB2\xB2\xB2\xB2\xB2\xB2\xB2 WELCOME TO THE MAIN MENU 
\xB2\xB2\xB2\xB2\xB2\xB2\xB2");
 printf("\n\n\t\t1.Create new account\n\t\t2.Update information of existing account\n\t\t3.For 
transactions\n\t\t4.Check the details of existing account\n\t\t5.Removing existing 
account\n\t\t6.View user's list\n\t\t7.Exit\n\n\n\n\n\t\t Enter your choice:");
 scanf("%d",&choice);
 system("cls");
 switch(choice)
 {
 case 1:new_acc();
 break;
 case 2:edit();
 break;
 case 3:transact();
 break;
 case 4:see();
 break;
 case 5:erase();
 break;
 case 6:view_list();
 break;
 //case 7:st_tu();
 //break;
 case 7:close();
 break;
}
}
void admin(void)
{
 char pass[10],password[10]="1234";
 char ch ;
 int i=0;
 printf("\n\n\t\tEnter the password to login:");
 while((ch =_getch())!=13){
 pass[i]=ch ;
 i++ ;
 printf("*");
 }
 pass[i]='\0';
 if (strcmp(pass,password)==0)
 {printf("\n\n\t\tPassword Match!\n\t\tLOADING");
 for(i=0;i<=8;i++)
 {
 fordelay(100000000);
 printf(".");
 }
 system("cls");
 menu();
 }
 else
 { printf("\n\n\t\tWrong password!!\a\a\a");
 login_try:
 printf("\n\t\tEnter 1 to try again and 0 to exit:");
 scanf("%d",&main_exit);
 if (main_exit==1)
 {
 system("cls");
 main();
 }
 else if (main_exit==0)
 {
 system("cls");
 close();}
 else
 {printf("\n\t\tInvalid!");
 fordelay(100000000);
 system("cls");
 goto login_try;}
 }
 return 0;
}
int main()
{
 char ch;
 system("CLS");
 system("color 9");
 printf("\n\t\t\t\t\tBUBT Bank Management System (BBMS) ");
printf("\n\n\t\t\t\t\t1. Login as Admin");
 printf("\n\t\t\t\t\t2. Login as user");
 printf("\n\n\t\t\t\t\tEnter your choice (1/2) : ");
 scanf("%d",&ch);
 system("CLS");
 switch(ch)
 {
 case 1:admin();
 break;
 case 2:user();
 break;
 case 3:close();
 break;
 }
 return 0;
}

