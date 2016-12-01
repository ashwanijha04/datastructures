#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node *left;
    struct node *right;
};
typedef struct node *NODE;
NODE getnode()
{
    NODE x;
    x=(NODE)malloc(sizeof(struct node));
    if(x==NULL)printf("memory full\n");
    return x;
}
NODE i_order(NODE root,int ele)
{
    NODE curr, prev,temp;
    temp=getnode();
    temp->data=ele;
    temp->left=NULL;
    temp->right=NULL;
    if(root==NULL)
        return temp;
    else if(ele<root->data)
    {
        temp->right=root;
        root->left=temp;
        return temp;
    }
    prev=NULL;
    curr=root;
    while(curr!=NULL && ele>curr->data)
    {
        prev=curr;
        curr=curr->right;
    }
    if(curr!=NULL)
        curr->left=temp;
    temp->right=curr;
    prev->right=temp;
    temp->left=prev;
    return root;
}
void display(NODE root)
{
    NODE curr;
    if(root==NULL)
        printf("list full\n");
    else
    {
        curr=root;
        while(curr!=NULL)
        {printf("%d\t",curr->data); curr=curr->right;}
        printf("\n");
    }
}

int main()
{
    NODE root;
    root=NULL;
    int ele,i;
    for(;;)
    {
        printf("enter 1 to input element in list, 2 to display\n");
        scanf("%d",&i);
        switch(i)
        {
        case 1:
            printf("enter element\n");
            scanf("%d",&ele);
            root=i_order(root,ele);
            break;
        case 2:
            display(root); break;
        default: exit(0);
        }
    }
    return 0;
}
