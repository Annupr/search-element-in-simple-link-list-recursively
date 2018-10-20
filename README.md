# search-element-in-simple-link-list-recursively
Here is the program to find search element in single link list recursively
#include<stdio.h>
#include<stdlib.h>
#include<stdbool.h>
struct Node{
	int data;
	struct Node *next;
};
void create(struct Node **head_ref,int ele)
{
	struct Node *new_node=(struct Node*)malloc(sizeof(struct Node*));
	new_node->data=ele;
	new_node->next=(*head_ref);
	*head_ref=new_node;	
}
void printList(struct Node * ptr)
{
	while(ptr!=NULL){
		printf("%d ",ptr->data);
		ptr=ptr->next;
	}
}
int search(struct Node *ptr,int num)
{
	if(ptr==NULL){
		return false;
	}
	
		if(ptr->data==num)
		{
			return true;
		}
		else return(ptr->next,num);

}
void main(){
	
	int i,n,ele,sr;
	int s;
	struct Node *head=NULL;

	printf("\nEnter the number of nodes:\n");
	scanf("%d",&n);
	
	for(i=0;i<n;i++){
		printf("\n Enter the value in  node:\n");
		scanf("%d",&ele);
		create(&head,ele);
	}
	printf("\nThe Input Link List is :\n");
	printList(head);
	printf("\nEnter the element you want to search:\n");
	scanf("%d",&sr);
	
	search(head, sr)? printf("Yes") : printf("No");
}
