#include <stdio.h>

#define TAM 10   // Define o tamanho do tabuleiro (10x10)
#define TAM_NAVIO 3  // Define o tamanho fixo dos navios

int main() {
    int tabuleiro[TAM][TAM];  // Matriz que representa o tabuleiro
    int i, j;

    // 1️⃣ Inicializa o tabuleiro com 0 (representa água)
    for (i = 0; i < TAM; i++) {
        for (j = 0; j < TAM; j++) {
            tabuleiro[i][j] = 0;
        }
    }

    // 2️⃣ Define as coordenadas iniciais dos navios
    int linha_navio_h = 2;  // Linha do navio horizontal
    int col_navio_h = 4;    // Coluna inicial do navio horizontal

    int linha_navio_v = 6;  // Linha inicial do navio vertical
    int col_navio_v = 1;    // Coluna do navio vertical

    // 3️⃣ Posiciona o navio horizontal (valor 3)
    for (j = col_navio_h; j < col_navio_h + TAM_NAVIO; j++) {
        if (j < TAM)  // Garante que não ultrapasse o tabuleiro
            tabuleiro[linha_navio_h][j] = 3;
    }

    // 4️⃣ Posiciona o navio vertical (valor 3)
    for (i = linha_navio_v; i < linha_navio_v + TAM_NAVIO; i++) {
        if (i < TAM)  // Garante que não ultrapasse o tabuleiro
            tabuleiro[i][col_navio_v] = 3;
    }

    // 5️⃣ Exibe o tabuleiro no console
    printf("=== TABULEIRO BATALHA NAVAL ===\n\n");

    for (i = 0; i < TAM; i++) {
        for (j = 0; j < TAM; j++) {
            printf("%d ", tabuleiro[i][j]); // Imprime cada posição
        }
        printf("\n"); // Pula linha após cada linha do tabuleiro
    }

    printf("\nLegenda: 0 = Água | 3 = Navio\n");

    return 0;
}
