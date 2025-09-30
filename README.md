# Quiz-de-biologia-
Repositório do código de quiz de biologia 
// Jogo de Quiz em C
// Atividade Pontuada EXTRA
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>

int iniciarQuiz() {
    char resposta;
    int pontos = 0;

    printf("\n========== QUIZ DE BIOLOGIA  ==========\n\n");

    printf("Pergunta 1:   Qual organela responsavél pela produção de energia(ATP) na celula'?\n");
    printf("a) Mitocondria\n");
    printf("b) Ribossomo\n");
    printf("c) Lisossomo\n");
    printf("Sua resposta: ");
    scanf(" %c", &resposta);
    if (tolower(resposta) == 'a') {
        printf("Correto!\n\n");
        pontos += 2;
    } else {
        printf("Incorreto! A resposta correta e 'a'\n\n");
    }

    printf("Pergunta 2: Qual e a unidade basica da vida?\n");
    printf("a)Molecula\n");
    printf("b) Celula\n");
    printf("c) Tecido\n");
    printf("Sua resposta: ");
    scanf(" %c", &resposta);
    if (tolower(resposta) == 'b') {
        printf("Correto!\n\n");
        pontos += 2;
    } else {
        printf("Incorreto! A resposta correta e 'b'\n\n");
    }

    printf("Pergunta 3:  Qual e o principal pigmento envolvido na fotossintese?\n");
    printf("a) Clorofila\n");
    printf("b) Melanina\n");
    printf("c) Hemoglobina\n");
    printf("Sua resposta: ");
    scanf(" %c", &resposta);
    if (tolower(resposta) == 'a') {
        printf("Correto!\n\n");
        pontos += 2;
    } else {
        printf("Incorreto! A resposta correta e 'a'\n\n");
    }

    printf("Pergunta 4:  Qual sistema do corpo humano e responsavel pelo transporte de gases e nutrientes?\n");
    printf("a)  Sistema digestorio\n");
    printf("b) Sistema respiratorio\n");
    printf("c) Sistema circulatorio\n");
    printf("Sua resposta: ");
    scanf(" %c", &resposta);
    if (tolower(resposta) == 'c') {
        printf("Correto!\n\n");
        pontos += 2;
    } else {
        printf("Incorreto! A resposta correta e 'c'\n\n");
    }

    printf("Pergunta 5:Os seres vivos que produzem seu proprio alimento sao chamados de:\n");
    printf("a) Heterotrofos\n");
    printf("b) Autotrofos\n");
    printf("c) Carnivoros\n");
    printf("Sua resposta: ");
    scanf(" %c", &resposta);
    if (tolower(resposta) == 'b') {
        printf("Correto!\n\n");
        pontos += 2;
    } else {
        printf("Incorreto! A resposta correta e 'b'\n\n");
    }

    return pontos;
}

void exibirResultado(int pontos) {
    printf("\n========== RESULTADO FINAL ==========\n");
    printf("Pontuacao total: %d pontos\n", pontos);

    if (pontos >= 0 && pontos <= 4) {
        printf("Precisa estudar mais!\n");
    } else if (pontos >= 6 && pontos <= 8) {
        printf("Muito bem!\n");
    } else if (pontos == 10) {
        printf("Excelente, parabens!\n");
    }

    printf("=====================================\n\n");
}

void exibirRegras() {
    printf("\n>>> VER REGRAS <<<\n");
    printf("----------------------------------------\n");
    printf("COMO JOGAR:\n");
    printf("1. O quiz possui 5 perguntas sobre Biologia\n");
    printf("2. Cada pergunta tem 3 alternativas (a, b, c)\n");
    printf("3. Cada resposta correta vale 2 pontos\n");
    printf("4. Pontuacao maxima: 10 pontos\n");
    printf("5. Responda com a letra da alternativa\n");
    printf("----------------------------------------\n");
    printf("Boa sorte e divirta-se!\n\n");
}

int main() {
    int opcao;
    int pontos;
    int continuar = 1;

    printf("========================================\n");
    printf("  BEM-VINDO AO QUIZ DE BIOLOGIA!\n");
    printf("========================================\n");
    printf("Ola! Prepare-se para se divertir com\n");
    printf("várias questões de biologia!\n");
    printf("========================================\n\n");

    while (continuar) {
        printf("===== MENU PRINCIPAL =====\n");
        printf("1 - Iniciar Quiz\n");
        printf("2 - Ver Regras\n");
        printf("3 - Sair\n");
        printf("==========================\n");
        printf("Digite sua opcao: ");
        scanf("%d", &opcao);

        switch(opcao) {
            case 1:
                {
                    char jogarNovamente;
                    do {
                        printf("\n>>> INICIAR QUIZ <<<\n");
                        pontos = iniciarQuiz();
                        exibirResultado(pontos);

                        printf("Deseja jogar novamente? (s/n): ");
                        scanf(" %c", &jogarNovamente);
                        jogarNovamente = tolower(jogarNovamente);

                        if (jogarNovamente == 's') {
                            printf("\n");
                        } else if (jogarNovamente == 'n') {
                            printf("\nVoltando ao menu principal...\n\n");
                        } else {
                            printf("\nOpcao invalida! Voltando ao menu principal...\n\n");
                            jogarNovamente = 'n';
                        }
                    } while (jogarNovamente == 's');
                }
                break;

            case 2:
                exibirRegras();
                break;

            case 3:
                printf("\nObrigado por jogar! Ate logo!\n");
                continuar = 0;
                break;

            default:
                printf("\n>>> OPCAO INVALIDA! <<<\n");
                printf("Por favor, escolha uma opcao entre 1 e 3.\n\n");
                break;
        }
    }

    return 0;
}
