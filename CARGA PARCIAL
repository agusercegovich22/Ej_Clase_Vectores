/*CARGA PARCIAL
Se ingresan DNI, código de sector (1 a 5) y sueldo de los empleados de una empresa. Se
sabe que como máximo la empresa tiene 100 empleados. Se desea:
a. Cargar los datos de los empleados mediante la función CargaEmpleados. La carga
finaliza con un empleado con DNI 99.
b. Generar un vector con la cantidad de empleados en cada sector mediante la función
CuentaPorSector y mostrarlo en forma de listado.
c. Determinar el importe total a pagar de sueldos mediante la función TotalAPagar.
*/

#include <stdio.h>
#include <stdlib.h>
int validacion(int, int, int);
float MayorACero();
void CuentaPorSector(int[],int);
int Repetido(int, int, int[]);
void TotalAPagar(int, float[]);
void CargaEmpleados(int[], int[], float[]);


int main(){
    int dni[100], sector[100]={0};
    float sueldo[100];
    CargaEmpleados(dni, sector, sueldo);
    printf("\n");
    system("pause");
    return 0;
}

int validacion(int li, int ls, int stop){
    int num;
    scanf("%d", &num);
    while((num<li || num>ls) && num!=stop){
        printf("Numero invalido, intentar de nuevo:");
        scanf("%d", &num);
    }
    return num;
}

float MayorACero(){
    float n;
    scanf("%f", &n);
    while(n<=0){
        printf("Numero invalido, ingrese un numero mayor a cero: ");
        scanf("%f", &n);
    }
    return n;
}

void CuentaPorSector(int sector[], int tope){
    int i, CantSector[5]={0};
    for(i=0;i<tope;i++){
        switch(sector[i]){
        case 1:
            CantSector[0]+=1;
        break;
        case 2:
            CantSector[1]+=1;
        break;
        case 3:
            CantSector[2]+=1;
        break;
        case 4:
            CantSector[3]+=1;
        break;
        case 5:
            CantSector[4]+=1;
        break;
        }
    }
    for(i=0;i<5;i++)
        printf("Cantidad de empleados sector (%d): %d\n", i+1, CantSector[i]);
}

int Repetido(int n, int i, int dni[]){
    int j=0, rep=0;
    while(j<i && rep!=1){
        if(n == dni[j])
            rep = 1;
        j++;
    }
    if(rep==1)
    while(n==dni[j-1]){
        printf("DNI previamente ingresado, ingrese otro empleado: ");
        n = validacion(1000000, 99999999, 99);

    }
    return n;
}

void TotalAPagar(int i, float sueldo[]){
    int j;
    float total;
    for(j=0;j<=i; j++){
        total += sueldo[j];
    }
    printf("El total a pagar es: $%f", total);
}

void CargaEmpleados(int dni[], int sector[], float sueldo[]){
    int i=0, n, n1;
    printf("Cargar los datos de los empleados, DNI (99) para finalizar carga:\n");
    while(i<100 && n!=99){
        printf("Ingresar DNI del empleado(%d): ", i+1);
        n = validacion(1000000, 99999999, 99);
        n1 = Repetido(n, i, dni);
        if(n1!=99){
            dni[i]= n;
        printf("\t\tSector: ");
        sector[i]=validacion(1, 5, 1);
        printf("\t\t\Sueldo: ");
        sueldo[i]= MayorACero();
        i++;
        }
    }
    CuentaPorSector(sector, i);
    TotalAPagar(i, sueldo);

}
