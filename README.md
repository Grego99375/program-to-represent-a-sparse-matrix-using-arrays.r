# program-to-represent-a-sparse-matrix-using-arrays.r

#include <stdio.h>

int main() {
    int matrix[10][10];
    int row[100], col[100], value[100];
    int m, n, i, j, k = 0;

    printf("Enter rows and columns: ");
    scanf("%d %d", &m, &n);

    printf("Enter matrix elements:\n");

    for (i = 0; i < m; i++) {
        for (j = 0; j < n; j++) {
            scanf("%d", &matrix[i][j]);

            if (matrix[i][j] != 0) {
                row[k] = i;
                col[k] = j;
                value[k] = matrix[i][j];
                k++;
            }
        }
    }

    printf("\nSparse matrix representation:\n");
    printf("Row\tColumn\tValue\n");

    for (i = 0; i < k; i++) {
        printf("%d\t%d\t%d\n",
               row[i], col[i], value[i]);
    }

    printf("Total non-zero elements: %d\n", k);

    return 0;
}

