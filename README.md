void login()
{
 
int a=0,i=0;
    char uname&#91;10],c=' ';
    char pword&#91;10],code&#91;10];
    char user&#91;10]="user";
    char pass&#91;10]="pass";
    do
{
system("cls");
 
    printf("\n  **************************  LOGIN FORM  **************************  ");
    printf(" \n                       ENTER USERNAME:-");
scanf("%s", &amp;uname);
printf(" \n                       ENTER PASSWORD:-");
while(i&lt;10)
{
    pword&#91;i]=getch();
    c=pword&#91;i];
    if(c==13) break;
    else printf("*");
    i++;
}
pword&#91;i]='\0';
//char code=pword;
i=0;
//scanf("%s",&amp;pword);
if(strcmp(uname,user)==0 &amp;&amp; strcmp(pword,pass)==0)
{
printf("  \n\n\n       WELCOME !!!! LOGIN IS SUCCESSFUL");
 
break;
}
else
{
printf("\n        SORRY !!!!  LOGIN IS UNSUCESSFUL");
a++;
 
getch();
 
}
}
while(a&lt;=2);
if (a&gt;2)
{
printf("\nSorry you have entered the wrong username and password for four times!!!");
 
getch();
 
}
system("cls");
}
int main(){     // MAIN FUNCTION
int i=0;
 
time_t t;
time(&amp;t);
char customername;
char choice;
    login();
    system("cls");
while (1)      // INFINITE LOOP
{
system("cls");
setcolor(10);
for(i=0;i&lt;80;i++)
printf("-");
printf("\n");
printf("   ******************************  |MAIN MENU|  ***************************** \n");
for(i=0;i&lt;80;i++)
printf("-");
printf("\n");
setcolor(10);
printf("\t\t *Please enter your choice for menu*:");
printf("\n\n");
printf(" \n Enter 1 -&gt; Book a room");
printf("\n------------------------");
printf(" \n Enter 2 -&gt; View Customer Record");
printf("\n----------------------------------");
printf(" \n Enter 3 -&gt; Delete Customer Record");
printf("\n-----------------------------------");
printf(" \n Enter 4 -&gt; Search Customer Record");
printf("\n-----------------------------------");
printf(" \n Enter 5 -&gt; Edit Record");
printf("\n-----------------------");
printf(" \n Enter 6 -&gt; Exit");
printf("\n-----------------");
printf("\n");
for(i=0;i&lt;80;i++)
printf("-");
    printf("\nCurrent date and time : %s",ctime(&amp;t));
    for(i=0;i&lt;80;i++)
printf("-");
 
choice=getche();
choice=toupper(choice);
switch(choice)           // SWITCH STATEMENT
{
case '1':
add();break;
case '2':
list();break;
case '3':
delete1();break;
case '4':
search();break;
case '5':
edit();break;
case '6':
system("cls");
printf("\n\n\t *****THANK YOU*****");
printf("\n\t FOR TRUSTING OUR SERVICE");
// Sleep(2000);
exit(0);
break;
default:
system("cls");
printf("Incorrect Input");
printf("\n Press any key to continue");
getch();
}
}
}
void add()
{
FILE *f;
char test;
f=fopen("add.txt","a+");
if(f==0)
{   f=fopen("add.txt","w+");
system("cls");
printf("Please hold on while we set our database in your computer!!");
printf("\n Process completed press any key to continue!! ");
getch();
}
while(1)
{
system("cls");
printf("\n Enter Customer Details:");
printf("\n**************************");
printf("\n Enter Room number:\n");
scanf("\n%s",s.roomnumber);
fflush(stdin);
printf("Enter Name:\n");
scanf("%s",s.name);
printf("Enter Address:\n");
scanf("%s",s.address);
printf("Enter Phone Number:\n");
scanf("%s",s.phonenumber);
printf("Enter Nationality:\n");
scanf("%s",s.nationality);
printf("Enter Email:\n");
scanf(" %s",s.email);
printf("Enter Period(\'x\'days):\n");
scanf("%s",&amp;s.period);
printf("Enter Arrival date(dd\\mm\\yyyy):\n");
scanf("%s",&amp;s.arrivaldate);
fwrite(&amp;s,sizeof(s),1,f);
fflush(stdin);
printf("\n\n1 Room is successfully booked!!");
printf("\n Press esc key to exit,  any other key to add another customer detail:");
test=getche();
if(test==27)
break;
 
}
fclose(f);
}
