<div align="center">

## Bovine Roulette \(like Russian Roulette\)


</div>

### Description

This is the first game I ever coded. I whipped it out in a few minutes and decided that it might be useful(ha!) for other people. Should work on any compiler in any OS. Sorta fun to play if your really bored, shows use of simple random numbers.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Ben Jacobs](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/ben-jacobs.md)
**Level**          |Beginner
**User Rating**    |2.3 (7 globes from 3 users)
**Compatibility**  |C
**Category**       |[Games](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/games__3-13.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/ben-jacobs-bovine-roulette-like-russian-roulette__3-806/archive/master.zip)

### API Declarations

```
<stdio.h>
<stdlib.h>
<time.h>
```


### Source Code

```
/* Coded by Ben Jacobs of Nonsense Software 2000.
 * Personal comments: I whipped this together in about half an hour and it's
 * the first game I've ever programmed in C. For some reason the random
 * number generator doesn't work that well, I try to fix it so it works better
 * sometime. Send comments to dooberwah@crosswinds.net
 */
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
int main(void)
{
	int i, r, d=0;
	char key;
	srand((unsigned)time(NULL));
	for(i=1;i<10;i++)
	{
		if(d==1)
			break;
		printf("\nBovine Roulette\n");
		printf("You are on cow %i of 10.\n",i);
		printf("Press \"m\" to start [m]ilking. ");
		for(;;)
		{
			key=getchar();
			if(key=='m')
				break;
		}
		r=rand()%100;
		if(r<10)
		{
			printf("Oops, you got kicked by the cow you were milking and died.\n");
			d=1;
		}
		if(r==11)
		{
			printf("The cow who you were milking's bullfriend comes to her rescue and beats you up. You die.\n");
			d=1;
		}
		if(r>12)
		{
			printf("You milk the cow without getting kicked. Onward to the next one!\n");
		}
	}
	if(d==1)
	{
		printf("Darn, it seems you have died. Check out www.nonsensesoftware.com for more \"cool\" games by");
		printf(" Nonsense Software.\n");
		getchar();
	}
	if(d==0)
	{
		printf("YAY! You won! (this should make you feal very happy for no reason at all) Check out");
		printf("www.nonsensesoftware.com for more \"cool\" games by Nonsense Software.\n");
		getchar();
	}
}
```

