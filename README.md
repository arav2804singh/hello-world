#include <stdio.h>
int hanoi(int n, char fr, char tr, char ar);
int main()
{
    start:
    printf("enter number of discs for the tower of hanoi : ");
    int n,retry;
    scanf("%d",&n);
    printf("follow the below given steps:-\n");
    hanoi(n, 'A', 'C', 'B');  
    printf("\ndo you want to try for a new number(1=yes/0=no) :");
    scanf("%d",&retry);
    if(retry==1)
        goto start;
}
int hanoi(int n, char fr, char tr, char ar)
{
    if (n == 1)
    {
        printf("\n Move disk 1 from rod %c to rod %c", fr, tr);
        return 0;
    }
    hanoi(n-1, fr, ar, tr);
    printf("\n Move disk %d from rod %c to rod %c", n, fr, tr);
    hanoi(n-1, ar, tr, fr);
}

