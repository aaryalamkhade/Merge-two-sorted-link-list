# Merge-two-sorted-link-list
Hacker rank solution for Merging  two sorted link list
```
SinglyLinkedListNode* mergeLists(SinglyLinkedListNode* head1, SinglyLinkedListNode* head2) 
{ 
SinglyLinkedListNode* p=head1;       //1st link list
SinglyLinkedListNode* q=head2;       //2nd link list
SinglyLinkedListNode*ll;             //for traverse a link list
SinglyLinkedListNode*head;           //New merging link list head
head=NULL;
  while(p!=NULL && q!=NULL)          //If any one of the list gets empty;
  {  SinglyLinkedListNode*temp=(struct SinglyLinkedListNode*)malloc(sizeof(struct SinglyLinkedListNode));      //new node creation
      temp->next=NULL;  
   if(p->data<=q->data)           //1st link list value is lesser
     {   temp->data=p->data;      //add it  to the new linklist
          if(head==NULL)           //if head is null
          {  
             head=temp;
             head->next=NULL;
         }
          else                       //if head is not null
          {
            ll=head;
            while(ll->next!=NULL)
            {
                ll=ll->next;
            }
            ll->next=temp;  
          }
          p=p->next;
     }
     else                        //If 2nd link list value is greater than the 1st one
     {
          temp->data=q->data;        
          if(head==NULL)          //If head is null
          {
              head=temp;
              head->next=NULL;
          }
          else                         //f head is not null
          {
            ll=head; 
            while(ll->next!=NULL)
            {
                ll=ll->next;
            }
            ll->next=temp;  
          }
          q=q->next;
     }
  }
  while(q!=NULL)                 //if in one list elements are there then we add it at the last
  {   SinglyLinkedListNode*temp=(struct SinglyLinkedListNode*)malloc(sizeof(struct    SinglyLinkedListNode));
      temp->data=q->data;
      temp->next=NULL;
      ll=head;
      while(ll->next!=NULL)
      {
          ll=ll->next;
      }
      ll->next=temp;
      q=q->next;
  }
  while(p!=NULL)           //if in one list elements are there then we add it at the last
  {   SinglyLinkedListNode*temp=(struct SinglyLinkedListNode*)malloc(sizeof(struct  SinglyLinkedListNode));
      temp->data=p->data;
      temp->next=NULL;
      ll=head;
      while(ll->next!=NULL)
      {
          ll=ll->next;
      }
      ll->next=temp;
      p=p->next;
  }
  return head;
}
```
