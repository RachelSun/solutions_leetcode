# 61.Rotate List

** Problem:**
Given a list, rotate the list to the right by k places, where k is non-negative.

    For example:
    Given 1->2->3->4->5->NULL and k = 2,
    return 4->5->1->2->3->NULL.
    
** My Solution:**

Date: April 29, 2016


    // The solution is from the discussion board

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
        ListNode* rotateRight(ListNode* head, int k) {

        ListNode* l = head, *r = head;
            int length = 0;
            for(ListNode* i = head; i!= NULL; i = i->next){
                ++length;
            }
            // do nothing if length = 0
            if(length == 0){
                return head;
            }
            // make sure k < length
            k %= length;
            // do nothing if k = 0
            if(k == 0){     
                return head;
            }
            for(int i = 1;i < k && r != NULL; ++i){
                r = r->next;
            }
            ListNode* pre;
            while(l->next != NULL && r->next != NULL){
                pre = l;
                l = l->next;
                r = r->next;
            }
            r->next = head;
            pre->next = NULL;
            return l;
        }
    };