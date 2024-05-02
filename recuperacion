#include <stdio.h>

int main(int argc, char *argv[]) {
    int opcion;
    double Montomensual, Totalmeses, Tasainteres;
    double Montocredito, Totalinteres;
    int NumerodeAnios;

    printf("Seleccione una opcion:\n");
    printf("1. Simulador de inversion\n");
    printf("2. Simulador de credito\n");
    scanf("%d", &opcion);

    if (opcion == 1) {
        printf("Ingrese el monto mensual:\n");
        scanf("%lf", &Montomensual);
        printf("Ingrese el total de meses:\n");
        scanf("%lf", &Totalmeses);
        printf("Ingrese el valor de la tasa de interes:\n");
        scanf("%lf", &Tasainteres);
        printf("-----------------------------------------------------------\n");
        printf ("-------------------TABLA DE INVERSION---------------------\n");
        printf("-----------------------------------------------------------\n");

        Tasainteres *= 0.001;

        printf("Mes\tInversion al final del mes\n");
        double inversion = 0;
        for (int mes = 1; mes <= Totalmeses; mes++) {
            double intereses = inversion * Tasainteres;
            inversion += Montomensual + intereses;
            printf("%d\t%.2f\t%.2f\n", mes, inversion, intereses);
        }
    } else if (opcion == 2) {
        printf("Ingrese el monto de credito:\n");
        scanf("%lf", &Montocredito);
        printf("Ingrese la tasa de interes anual (porcentaje):\n");
        scanf("%lf", &Tasainteres);
        printf("Ingrese el numero de años:\n");
        scanf("%d", &NumerodeAnios);

        Tasainteres *= 0.001; 
        Totalinteres = 0;

        printf("-----------------------------------------------------------\n");
        printf("------------------TABLA DE AMORTIZACION-------------------\n");
        printf("-----------------------------------------------------------\n");
        printf("Año\tInteres\t\tCuota mensual\tTotal de interes\n");

        for (int anio = 1; anio <= NumerodeAnios; anio++) {
            double CuotaAnual, InteresAnual, Saldo;

            Saldo = Montocredito;
            InteresAnual = 0;

            for (int mes = 1; mes <= 12; mes++) {
                double InteresMensual = Saldo * (Tasainteres / 12);
                Saldo = Saldo + InteresMensual - (CuotaAnual / 12);
                InteresAnual += InteresMensual;
            }

            CuotaAnual = (Montocredito / NumerodeAnios);
            Totalinteres += InteresAnual;

            printf("%d\t%.2f\t\t%.2f\t\t%.2f\n", anio, InteresAnual, CuotaAnual, Totalinteres);
        }
    } else {
        printf("Opcion invalida. Por favor, seleccione 1 o 2.\n");
    }

    return 0;
}
