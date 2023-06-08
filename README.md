
#include <stdio.h>
#include <stdlib.h>
typedef struct{
float cc;
float exm;
float myn;
}module;

module m;
typedef struct{
module mod[20];
char nom [10];
int nmbrm;
}semestre;

typedef struct {
    char mat[100];
    char Nom[100];
    char Prenom [100];
    char Dns[100];
    char datin[100];
    semestre L[6];
    semestre m[4];

}etudien;
void inscrl (etudien *e){
    int j,i,k=0,n,q=0;

for(j=0;j<5;j++){
printf("__ SEMESTRE N %d \n  ",j+1);
printf("\n entre le nombre des etudien licence \n ");
    scanf("%d",&n);
printf(" entre le nombre de module dans ce semestre :\n ");
scanf("%d",&e->L[0].nmbrm);
  q=0;
  do{
  printf("\n MATRICULE : ");
  scanf("%s",&e[q].mat);
  printf("NOM : ");
  scanf("%s",&e[q].Nom);
  printf("PRENOM : ");
  scanf("%s",&e[q].Prenom);
  printf("Date de naissance  : ");
  scanf("%s",&e[q].Dns);
  printf("Date d inscrpt : ");
  scanf("%s",&e[q].datin);
  q=q+1;
  for(i=0;i<e[q].L[0].nmbrm;i++){
printf("\n LE MODULE N :%d" ,i+1);
printf("\n nome de module : ");
  scanf("%s",&e[q].L[0].nom);
  printf("\n entre la note de controle : ");
  scanf(" %f",&e[q].L[0].mod[i].cc);

    printf("\n entre la note de exmn : ");
   scanf("%f",&e[q].L[0].mod[i].exm);
     printf("\nentre la myn de module : ");
    scanf("%f",&e[q].L[0].mod[i].myn);}
      }while(q<n);}}



void inscrm(etudien *e){
int j,i,k=0,n,q=0;
for(j=0;j<4;j++){
printf("__ SEMESTRE N %d ",j+1);
printf("\n entre le nombre des etudiens masters dans ce smstr : \n ");
    scanf("%d",&n);
printf(" entre le nombre de module dans ce semestre :\n ");
scanf("%d",&e->m[0].nmbrm);

  q=0;
  do{
  printf("\n MATRICULE : ");
  scanf("%s",&e[q].mat);
  printf("NOM : ");
  scanf("%s",&e[q].Nom);
  printf("PRENOM : ");
  scanf("%s",&e[q].Prenom);
  printf("Date de naissance  : ");
  scanf("%s",&e[q].Dns);
  printf("Date d inscrpt : ");
  scanf("%s",&e[q].datin);
  q=q+1;
  for(i=0;i<e[q].m[0].nmbrm;i++){
printf("\n LE MODULE N :%d" ,i+1);
printf("\n nome de module : ");
  scanf("%s",&e[q].m[0].nom);
  printf("\n entre la note de controle : ");
  scanf(" %f",&e[q].m[0].mod[i].cc);

    printf("\n entre la note de exmn : ");
   scanf("%f",&e[q].m[0].mod[i].exm);
     printf("\nentre la myn de module : ");
    scanf("%f",&e[q].m[0].mod[i].myn);}
      }while(q<n);}}

void inscri (etudien *e){
    int n,i,m;
printf("__ Inscription des licences\n __");

    inscrl(e);

printf("__ Inscription des Masters\n__");
    inscrm(e);
}
/* saise les notes d un etudien */
void note (etudien *e){

int n,i,a,m;
printf("entre le numero de semestre : ");
scanf("%d",&n);


printf("entre le numero de l etudien ");
scanf("%d",&a);

if(n<=6){
    ("\n etudien de niveau Licence \n");
        printf("entre le numbre  de module  : ");
scanf("%d",&e[a-1].L[n-1].nmbrm);
    for(i=0;i<e[a-1].L[n-1].nmbrm;i++){

        printf("\n LE MODULE N :%d" ,i+1);
  printf("\n nome de module : ");
  scanf("%s",&e[a-1].L[n-1].nom);
  printf("\n entre la note de controle : ");
  scanf(" %f",&e[a-1].L[n-1].mod[i].cc);

    printf("\n entre la note de exmn : ");
   scanf("%f",&e[a-1].L[n-1].mod[i].exm);
     printf("\nentre la myn de module : ");
    scanf("%f",&e[a-1].L[n-1].mod[i].myn);
    }
}
else if(n>6) {
    printf("\n etudien de niveau MASTER \n");
printf("entre le numbre  de module : ");
scanf("%d",&e[a-1].m[n-1].nmbrm);
    for(i=0;i<e[a-1].m[n-7].nmbrm;i++){
         printf("\n LE MODULE N :%d" ,i+1);
  printf("\n nome de module : ");
  scanf("%s",&e[a-1].m[n-7].nom);
  printf("\n entre la note de controle : ");
  scanf(" %f",&e[a-1].m[n-7].mod[i].cc);

    printf("\n entre la note de exmn : ");
   scanf("%f",&e[a-1].m[n-7].mod[i].exm);
     printf("\nentre la myn de module : ");
    scanf("%f",&e[a-1].m[n-7].mod[i].myn);

}
}}
float Moyenne(etudien*e,int n) {
    int i, a;
    float s = 0, moyenne = 0;


    if (n <= 6) {
        printf("Niveau : Licence\n");
        printf("Nombre de modules : ");
        scanf("%d", &(e[a - 1].L[n - 1].nmbrm));
        for (i = 0; i < e[a - 1].L[n - 1].nmbrm; i++) {
            s= s+e[a - 1].L[n - 1].mod[i].myn;
        }
        moyenne = s / e[a - 1].L[n - 1].nmbrm;
    } else if (n > 6) {
        printf("Niveau : Master\n");
        printf("Nombre de modules : ");
        scanf("%d", &(e[a - 1].m[n - 7].nmbrm));
        for (i = 0; i < e[a - 1].m[n - 7].nmbrm; i++) {
            s += e[a - 1].m[n - 7].mod[i].myn;
        }
        moyenne = s/ e[a - 1].m[n - 7].nmbrm;
    }
    return moyenne;
}
void affiche (etudien *e[100]){
    float m=0;
    int i,j,n;

    printf("\n les etudien licence admise:\n ");
 for(i=0;i<6;i++){
    printf("\n entre le nombre des etudien dans ce semestre \n ");
    scanf("%d",&n);
    for(j=0;j<n;j++){
    if(Moyenne(e[j],j)>=10){
            printf("%s",e[j]->Nom);
            printf("%s",e[j]->Prenom);
            c++;

       }}}
       printf("\n les etudien Mastere admise: \n");
for(i=0;i<4;i++){
    printf("\n entre le nombre des etudien dans ce semestre \n ");
    scanf("%d",&k;
    for(j=0;j<n;j++){
    if(Moyenne(e[j],j)>=10){
            printf("%s",e[j]->Nom);
            printf("%s",e[j]->Prenom);
c++;
       }}}
       
       }
int main()
{int i,choix,n;
etudien e[100];
printf("______ bienvenu sur platforme etudien____\n");
printf("-->Pour inscris les licencs : entre 1 \n --> Pour inscris les masters  : entre 2 \n --> Pour inscris les deux niveau : entre 3\n");
printf("votre choix est : ");
scanf("%d",&choix);
if(choix==1){
   inscrl(e);
}
else if (choix==2){
    inscrm(e);
}
else if (choix==3){
    inscri(e);
}
printf("\n saise les notes d un etudien\n  : ");
note(e);
printf("\n les etudien admis \n");
affiche(e);
