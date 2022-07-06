# Linked List

## STL
[list](https://cplusplus.com/reference/list/list/)

## Qusetions

- made new dummy node because the next element in result should point
  somewhere, and at last return from 2nd element of linklist.

[leetcode question](https://leetcode.com/problems/merge-two-sorted-lists)
```cpp
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
        if(l1==NULL) return l2;
        if(l2==NULL) return l1;
        
        ListNode *merged=new ListNode(0);
        ListNode *tail=merged;
        while(l1!=NULL and l2!=NULL){
            if(l1->val < l2->val){
                tail->next = l1;
                l1=l1->next;
            }
            else {
                tail->next=l2;
                // tail=l2;
                l2=l2->next;
            }
            tail=tail->next;
        }
        if(l1==NULL) tail->next=l2;
        else tail->next=l1;
        return merged->next;
    }
};
```
