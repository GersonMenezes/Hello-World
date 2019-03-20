#include <stdio.h>
#include <stdlib.h>

void remover(int *x, int *p){
	
	
    for(int t=0; t<*x; t++){
        for(int i=0; i<*x; i++){
            if(p[t]==p[i] && &p[t]!=&p[i]){
                p[t] = p[*x-1];
                *x = *x-1;
                p = (int*) realloc(p, (*x)*sizeof(int));
            }
        }

    }

}
int main(){

int *p, x;

    printf("Diga a quantidade de numero que desejas adicionar: ");
    scanf("%d", &x);

    p = (int*) malloc(x*sizeof(int));
        if(p == NULL) printf("No memory available");

    for(int c=0; c<x; c++){
        printf("diga os valores: ");
        scanf("%d", &p[c]);

        }

    remover(&x, p);
	
    for(int z=0; z<x; z++){
    printf("\n%d\n", p[z]);
    }

return 0;
}
