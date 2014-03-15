/* 
 * File:   main.c
 * Author: brunis46
 *
 * Created on 24 de febrero de 2014, 17:38
 */

#include <stdio.h>
#include <stdlib.h>
#include "cola.h"
#include "listas.h"



void solicitud(TLISTA *a, TCOLA *b, int longitud, POSICION fin){
    POSICION i;
    TIPOELEM e;
    
    do{ printf("Introduzca el codigo asociado al avion (contiene 5 numeros enteros): ");
    scanf("%d", &e);
    }while(e<10000 || e>99999); 
    
         if(longitud==5){
             AnadirCola(b,e);
             printf("Avion con el codigo asociado %d, incluido para lista de espera\n", e);
         }
         else if(longitud>=0 && longitud<5){
          inserta(a,fin,e);
          printf("Avion con el codigo asociado %d, confirmado para lista de aterrizaje\n", e);
         }
         else printf("ERROR\n");
        }

void imprimir(TLISTA a, TCOLA b){
    TIPOELEM e;
    short i;
    POSICION p;
    
    if(longitud(a)>0){
    p=primero(a);
    printf("\nLISTA DE ATERRIZAJE\n\n");
    for(i=0;i<longitud(a);i++){
    recupera(a,p,&e);
    printf("%d) Avion %d\n",i+1,e);
    p=siguiente(a,p);
    }
    if(EsColaVacia(b)==0){
    
    printf("\nCOLA DE ESPERA\n\n");
        PrimeroCola (b,&e);
        printf("El siguiente avion a aterrizar es el %d\n", e);
    }}
    else printf("No hay aviones en la cola de espera\n"); 
}

short int avion(TLISTA a, TCOLA b, TIPOELEM *codigo, POSICION *busqueda, TIPOELEM *primero){
    TIPOELEM e;
    *primero=0;
    
    //Procedimiento para poder enviar por referencia la TLISTA y la TCOLA en la función de modificación de las mismas (aterrizaje).
    
    if (longitud(a)>0){
     printf("Que avion procedera a su aterrizaje? ");
        scanf("%d", &e);
        *busqueda=buscar(a,e);
        if(EsColaVacia(b)==0)
        PrimeroCola(b,primero);
        *codigo=e;
        return 1; }
   
    else return 0;

}


void aterrizaje(TLISTA *a, TCOLA *b, short int longi,TIPOELEM codigo, POSICION busqueda,POSICION finn, TIPOELEM primero){
   
    if(longi==1){
        if(busqueda!=finn){
        if(primero>=10000 && primero<=99999){
           modifica(a,busqueda,primero);
            EliminarCola (b);
            printf("El avion %d ha aterrizado\n", codigo);
          printf("Avion con el codigo %d, puede proceder a la aproximacion hacia la pista de aterrizaje\n", primero);  
        }
        else{
            suprime(a,busqueda);
        printf("El avion %d ha aterrizado\n", codigo); }
        
}
     else printf("El avion %d no esta en lista de aterrizaje\n", codigo);
}
     else printf("No hay aviones en la lista de aterrizaje\n");      
}



int main(int argc, char** argv) {
    char opcion,opcion1;
    TIPOELEM codigo, primero;
    POSICION busqueda, finn;
    TCOLA c_espera;
    TLISTA l_aterriza;
    crea(&l_aterriza);
    ColaVacia(&c_espera);
    
    do{
printf("\n-------- Aeropuerto Lavacoya ------------\n");
	printf("\n1) Solicitud de aterrizaje");
        printf("\n2) Aterrizaje");
        printf("\n3) Salir");
   	printf("\n\n--------------------\n");

	printf("\nOpcion: ");
	scanf(" %c", &opcion);
        getchar();
        
   switch(opcion){
      case '1':
        solicitud(&l_aterriza, &c_espera, longitud(l_aterriza),fin(l_aterriza));
        imprimir(l_aterriza, c_espera);
          break;
                
       case '2':
         aterrizaje(&l_aterriza, &c_espera,avion(l_aterriza, c_espera,&codigo,&busqueda,&primero),codigo,busqueda,fin(l_aterriza),primero);
         imprimir(l_aterriza, c_espera);
           break;
                
       case '3':
          printf("Esta seguro de que desea abandonar el programa? (1=Si, 0=No)\n");
          scanf(" %c", &opcion1); 
          getchar();
          if(opcion1=='1'){
           destruye(&l_aterriza);
          if(EsColaVacia(c_espera)==0)
           EliminarCola(&c_espera);
           printf("Finalizando programa..\n");}
            break;
      
       default: printf("Opcion introducida incorrecta");   }
        
        }while((opcion!='3') || (opcion1!='1'));
    return (EXIT_SUCCESS);
}

