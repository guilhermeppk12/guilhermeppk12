#include <stdio.h>

int main() {
    int numero_aleatorio, tentativa, tentativas = 0;
    int max_tentativas = 10;

    srand(time(0));

    numero_aleatorio = rand() % 100 + 1;

    printf("Bem-vindo ao jogo de adivinhar o número!\n");
    printf("Você tem %d tentativas para adivinhar o número entre 1 e 100.\n", max_tentativas);

    while (tentativas < max_tentativas) {
        printf("Tentativa %d: ", tentativas + 1);
        scanf("%d", &tentativa);
        tentativas++;

        if (tentativa == numero_aleatorio) {
            printf("Parabéns! Você acertou o número em %d tentativas.\n", tentativas);
            break;
        } else if (tentativa > numero_aleatorio) {
            printf("O número é menor!\n");
        } else {
            printf("O número é maior!\n");
        }

        if (tentativas == max_tentativas) {
            printf("Suas tentativas acabaram. O número era: %d\n", numero_aleatorio);
        }
    }

    return 0;
}
