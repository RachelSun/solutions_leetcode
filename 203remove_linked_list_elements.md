# 203.Remove Linked List Elements

**Problem:**

Remove all elements from a linked list of integers that have value val.

Example

Given: 1 --> 2 --> 6 --> 3 --> 4 --> 5 --> 6, val = 6

Return: 1 --> 2 --> 3 --> 4 --> 5

**My Solutions:**

Date: March 21, 2016

    // Definition for singly-linked list.{
    struct ListNode {
      int val;
      ListNode *next;
      ListNode(int x) : val(x), next(NULL) {}
     };
     
    class Solution{
    public:
        ListNode* removeElements(ListNode* head, int val) {
        if(head == NULL) return NULL; 
        if(head->val == val) 
        return removeElements(head->next, val); 
        head->next = removeElements(head->next,val);
        return head;
        }
    };

