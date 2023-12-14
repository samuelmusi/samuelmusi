#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Función para ordenar una cadena
void ordenar(char *cadena) {
  int i, j;
  char aux;

  for (i = 0; i < strlen(cadena) - 1; i++) {
    for (j = i + 1; j < strlen(cadena); j++) {
      if (cadena[i] > cadena[j]) {
        aux = cadena[i];
        cadena[i] = cadena[j];
        cadena[j] = aux;
      }
    }
  }
}

int main() {
  // Declaramos variables
  char cadena[100];
  FILE *archivo;

  // Solicitamos la cadena al usuario
  printf("Ingrese una cadena: ");
  fgets(cadena, 100, stdin);

  // Ordenamos la cadena
  ordenar(cadena);

  // Creamos el archivo
  archivo = fopen("cadena.txt", "w");

  // Escribimos la cadena en el archivo
  fprintf(archivo, "%s\n", cadena);

  // Cerramos el archivo
  fclose(archivo);

  // Imprimimos la cadena mal escrita y la ordenada
  printf("Cadena mal escrita: %s\n", cadena);
  printf("Cadena ordenada: %s\n", cadena);

  return 0;
}
