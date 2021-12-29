# Tic-Tac-Toe-using-C

#include<stdio.h>
#include<conio.h>

void check(char,char);
char a[9]={ '1','2','3','4','5','6','7','8','9'};

void gameName()
{
	printf("\n\t\t\t Tic Tak Toe Game : \n");
}

void show()
{
	printf("\t\t\t---|---|---\n");
	printf("\t\t\t  %c|  %c|  %c \n",a[0],a[1],a[2]);
	printf("\t\t\t---|---|---\n");
    printf("\t\t\t  %c|  %c|  %c\n",a[3],a[4],a[5]);
	printf("\t\t\t---|---|---\n");
	printf("\t\t\t  %c|  %c|  %c\n",a[6],a[7],a[8]);
	printf("\t\t\t---|---|---\n");
}

void inputSymbol()
{
	printf("\n Player 1 symbol :x:");
	printf("\n Player 2 symbol :o:");
}

void start()
{
	char pa;
	printf("\n Who will start the game : Player 1 or Player 2\n");
	scanf("%c",&pa);
}
   
int count=0;
void play()
{
   	char p,s;
   	printf("\n Enter the position & symbol for the player:\n");
   	fflush(stdin);
   	scanf("%c",&p);
   	fflush(stdin);
   	scanf("%c",&s);
   	count++;
   	
   	check(p,s);
}
   
void check(char P, char S)
{
    int i;
   	for(i=0;i<=8;i++)
   	{
		 
   	    if(a[i]==P)
   		 {
   			a[i]=S;
		 }
	  }
   }
   
int end() 
{
   if((a[0]=='x'&&a[1]=='x'&&a[2]=='x')||(a[0]=='x'&&a[3]=='x'&&a[6]=='x')||(a[0]=='x'&&a[4]=='x'&&a[8]=='x'))
 	return(100);
   else if((a[0]=='o'&&a[1]=='o'&&a[2]=='o')||(a[0]=='o'&&a[3]=='o'&&a[6]=='o')||(a[0]=='o'&&a[4]=='o'&&a[8]=='o'))
    return(200);
    
   else if(a[1]=='x'&&a[4]=='x'&&a[7]=='x')	
	return(100);
   else if(a[1]=='o'&&a[4]=='o'&&a[7]=='o')
   return(200);
   
   else if(a[2]=='x'&&a[5]=='x'&&a[8]=='x')	
	return(100);
   else if(a[2]=='o'&&a[5]=='o'&&a[8]=='o')
   return(200);
   
   else if(a[3]=='x'&&a[4]=='x'&&a[5]=='x')	
	return(100);
   else if(a[2]=='o'&&a[4]=='o'&&a[5]=='o')
   return(200);
   
   else if(a[2]=='x'&&a[4]=='x'&&a[6]=='x')	
	return(100);
   else if(a[2]=='o'&&a[4]=='o'&&a[6]=='o')
   return(200);
   
   else if(a[6]=='x'&&a[7]=='x'&&a[8]=='x')	
	return(100);
   else if(a[6]=='o'&&a[7]=='o'&&a[8]=='o')
   return(200);
   
   return(300);
   
}  

void main()
{
	int k;
	char ch;
	
	label2:
		system("cls");
		gameName();
		show();
		inputSymbol();
		start();
		play();
		
	label1:
	    system("cls");
	    show();
	    play();
	    k=end();
	    system("cls");
	    
	    show();
	    if(count<9)
	    {
	    	if(k==100)
	    	{
	    		printf("\nPlayer 1 is the winner.");
	    	    count=0;
			}
			else if(k==200)
			{
				printf("\nPlayer 2 is the winner.");
	    	    count=0;
			}
			else
			 goto label1;
	   	}
	   	else
	   	{
	   		printf("\nGame Over");
	   		count=0;
	   	}
	   	
	   	printf("\nDo you want to continue the game: Enter y for YES & n for NO");
	   	fflush(stdin);
	   	scanf("%c",&ch);
	   	if(ch=='y'||ch=='Y')
	   	{
	   		a[0]='1';
	   		a[1]='2';
	   		a[2]='3';
	   		a[3]='4';
	   		a[4]='5';
	   		a[5]='6';
	   		a[6]='7';
	   		a[7]='8';
	   		a[8]='9';
	   		goto label2;
	   			
		}
	getch();
		
}
