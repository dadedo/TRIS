TRIS
====

Programma per giocare a filetto


#include<stdio.h>
#include<conio.h>
#include<string.h>

char m[3][3];

void carica();
void stampa();
void gioca();



main()
{
carica();
stampa();
gioca();
getch();
}


void carica()
{
m[0][0]='a';
m[0][1]='b';
m[0][2]='c';
m[1][0]='d';
m[1][1]='e';
m[1][2]='f';
m[2][0]='g';
m[2][1]='h';
m[2][2]='i';
}
void stampa()
{
int i,j;
for(i=0;i<3;i++)
{
for(j=0;j<3;j++)
{
printf("\t%c",m[i][j]);
}
printf("\n\n\n");
}
}
void gioca()
{
int t=0,i,j,cont=0;
char n1,n2,vin;
printf("\nil giocatore1 e' la O e il giocatore2 e' la X!!\n");
printf("INIZIA IL GIOCOOOOO!!!");
do
{
printf("\ngiocatore1:dove vuoi inserire il tuo simbolo?(digitando la lettera corrispondende alla casella)\n");
scanf("%c",&n1);
for(i=0;i<3;i++)
for(j=0;j<3;j++)
{
if(m[i][j]==n1)
{
m[i][j]='O';
}
}
printf("\ngiocatore2:dove vuoi inserire il tuo simbolo?(digitando la lettera corrispondende alla casella)\n");
scanf("%c",&n2);
for(i=0;i<3;i++)
for(j=0;j<3;j++)
{
if(m[i][j]==n2)
{
m[i][j]='X';
}
}
for(i=0;i<3;i++)
{
for(j=0;j<3;j++)
{
printf("\t%c",m[i][j]);
}
printf("\n\n\n");
}
for(i=0;i<3;i++)
for(j=0;j<3;j++)
{
if((m[i][j]==m[i][j+1])&&(m[i][j]==m[i][j+2]))
{vin=m[i][j];
cont==1;}
if((m[i][j]==m[i+1][j])&&(m[i][j]==m[i+2][j]))
{vin=m[i][j];
cont==1;}
if((m[0][0]==m[1][1])&&(m[0][0]==m[2][2]))
{vin=m[i][j];
cont==1;}
if((m[0][2]==m[1][1])&&(m[0][2]==m[2][0]))
{vin=m[i][j];
cont==1;}
}
t++;
}
while((cont==0)&&(t<5));
if(vin=='O')
printf("\n il vincitore e' il giocatore1!!!\n");
if(vin=='X')
printf("\n il vincitore e' il giocatore2!!!\n");
if(t==5)
printf("\n non c'e' vincitore\n");
}
