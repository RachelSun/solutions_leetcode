# 206.Reverse Linked List
**Problem:**

Reverse a singly linked list. 

**My Solutions:**

Date: March 18, 2016

    /**
     * Definition for singly-linked list.
     * struct ListNode {
     *     int val;
     *     ListNode *next;
     *     ListNode(int x) : val(x), next(NULL) {}
     * };
     */

    class Solution {
    public:
        ListNode* reverseList(ListNode* head) {
            // recursively 
            if(!head || !head->next) return head;
            ListNode* currentHead = reverseList(head->next);
            head->next->next = head;
            head->next = NULL;
            return currentHead;
        }
    };


