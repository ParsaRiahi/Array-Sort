# Array-Sort
// Originally called Array2.c

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void jona(int *array, int i)
{
    int box;
    box = array[i];
    array[i] = array[i - 1];
    array[i - 1] = box;
}
                                    
void poldi(int *array, int size)
{
    for (int i = 1; i < size; i = i + 1) 
    {
        for (int j = i; j > 0 && array[j] < array[j - 1]; j = j - 1) 
        {
            jona(array, j); 
        }
    }
}

int main(void)
{
    int array[20];    //array that has 20 integers
    int i;    //counter

    srand(time(NULL));

    printf("Original array:\n");
    for(i = 0; i < 20; i = i + 1)
    {
        array[i] = (rand() % 100) + 1;
        printf("%d ", array[i]);
    }
    printf("\n");
    
    poldi(array, 20);

    printf("Sorted array:\n");
    for (i = 0; i < 20; i = i + 1)
    {
        printf("%d ", array[i]);
    }
    printf("\n");
    
    return 0;
}





