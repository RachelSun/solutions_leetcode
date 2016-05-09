# 19.Remove Nth Node From End of List

**Problem:**

Given a linked list, remove the nth node from the end of list and return its head.

    For example,

       Given linked list: 1->2->3->4->5, and n = 2.

       After removing the second node from the end, the linked list becomes 1->2->3->5.
   
Note:
      Given n will always be valid.
      Try to do this in one pass.
      
      
** My Solutions:**

Date: May 9, 2016

    // 4ms
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
        ListNode* removeNthFromEnd(ListNode* head, int n) {
            //if the list is empty, return NULL
            if(!head) return NULL;
            // Define 3 pointers point to this list.
            ListNode* fast = head;
            ListNode* slow = head;
            ListNode* result = slow;
            // if the list only has one element and remove it, return NULL
            if(fast->next == NULL && n == 1) return NULL;
            //Count the list' length-n
            while(n){
                fast = fast->next;
                n--;
            }
            if(fast == NULL){
                slow = slow->next;
                return slow;
            }
            while(fast->next){
                slow = slow->next;
                fast = fast->next;
            }
            slow->next= slow->next->next;
            return result;
        }
    };