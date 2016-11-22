
#include<stdio.h>
#include<stdlib.h>

#define QUEUE_SIZE 5

int qfull(int);
int qempty(int);
void insert_rear(int, int*, int*, int*);
void delete_front(int*, int*, int*);
void display(int*, int, int);

void main()
{
	int choice, item;
	int f, r, q[QUEUE_SIZE], count;

	f = 0;
	r = -1;

	printf("Circular Queue\n");
	for(;;)
	{
		printf("Please enter a choice\n");
		printf("1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n");
		printf("Choice:\t");
		scanf("%d", &choice);
		
		switch(choice)
		{
			case 1:
				printf("Enter the element to be inserted:\t");
				scanf("%d", &item);
				insert_rear(item, q, &r, &count);
				
				break;

			case 2:
				delete_front(q, &f, &count);
			
				break;

			case 3:
				display(q, f, count);
			
				break;

			default:
				exit(0);
		}
	}
}

int qfull(int count)
{
	return (count == QUEUE_SIZE) ? 1 : 0;
}

void insert_rear(int item, int q[], int *r, int *count)
{
	if(qfull(*count))
	{
		printf("Queue is full\nInsertion not possible\n");
		return;
	}

	*r = (*r + 1) % QUEUE_SIZE;
	q[*r] = item;
	(*count)++;
}

int qempty(int count)
{
	return (count == 0) ? 1 : 0;
}
void delete_front(int q[], int *f, int *count)
{
	int item_deleted;

	if(qempty(*count))
	{
		printf("Queue is empty\nCannot delete\n");
		return;
	}

	item_deleted = q[*f];
	*f = (*f + 1) % QUEUE_SIZE;
	(*count)--;

	printf("The deleted element in queue is:\t%d\n", item_deleted);
}
void display(int q[], int f, int count)
{
	int i, j;

	if(qempty(count))
	{
		printf("Queue is empty\nNo elements to display\n");
		return;
	}

	printf("Displaying the contents of the queue\n");

	i = f;
	for(j = 1; j <= count; j++)
	{
		printf("%d\n", q[i]);
		i = (i +1) % QUEUE_SIZE;
	}
}
