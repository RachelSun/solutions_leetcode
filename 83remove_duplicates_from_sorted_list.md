# 83.Remove Duplicates from Sorted List

**Problem:**

Given a sorted linked list, delete all duplicates such that each element appear only once.

    For example,
    Given 1->1->2, return 1->2.
    Given 1->1->2->3->3, return 1->2->3.
    
    
** My Solutions:**

Date: April 29, 2016

     // Solution 16ms, beat 8.21%
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
        ListNode* deleteDuplicates(ListNode* head) {
            if(!head || !head->next) return head;
            ListNode* cur = head;
            while(cur){
                if(cur->next && cur->val == cur->next->val)
                    cur->next=cur->next->next;
                else
                    cur=cur->next;
            }
            return head;
        }
    };