#include <stdio.h>
void printSeries(int start, int end) {
    if (start <= end) {
        printf("%d ", start);
        printSeries(start + 1, end);
    }
}
int main() {
    int n;
    printf("Enter the value of n: ");
    scanf("%d", &n);

    printf("Series from 1 to %d: ", n);
    printSeries(1, n);
    printf("\n");
    return 0;
}
