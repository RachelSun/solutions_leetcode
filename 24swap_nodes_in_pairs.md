# 24.Swap Nodes in Pairs

**Problem:**
Given a linked list, swap every two adjacent nodes and return its head.

    For example,
    Given 1->2->3->4, you should return the list as 2->1->4->3.

Your algorithm should use only constant space. You may not modify the values in the list, only nodes itself can be changed.

**My Solution:**

Date: May 11, 2016
      
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
        ListNode* swapPairs(ListNode* head) {
            if(!head ||!head->next ) return head;
            ListNode *l = new ListNode(0);
            l->next = head;
            ListNode *tmp1 = l;
            ListNode *tmp2 = head;
            while(tmp2&& tmp2->next){
                ListNode *tmp0 = tmp1;
                tmp1 = tmp1->next;
                tmp2 = tmp2->next;
                ListNode *tmp3 = tmp2->next;
                tmp0->next = tmp2;
                tmp2->next = tmp1;
                tmp1->next = tmp3;
                tmp2 = tmp3;
            }
            return l->next;
        }
    };
