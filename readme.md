#include<stdio.h>
#include<math.h>
int main()
{
	int n, i, desti, sum, k, final = 0;
	scanf("%d", &n);
	sum = n;
	for (i = 0;; i++)                    /*判断转化的二进制的数位*/
	{
		if (pow(2, i) <= n)
		{
			continue;
		}
		else
		{
			break;
		}
	}
	for (k = i; k > 0; k--)               /*从高位到低位凑数*/
	{
		if (pow(2, k-1) > sum)
		{
			desti = 0;
		}
		else if(pow(2, k-1) < sum)
		{
			desti = 1;
		}
		else
		{
			desti = 1;
		}
		final += pow(10, k-1) * desti;
		sum -= desti * pow(2, k-1);
	}
	printf("%d", final);
}
