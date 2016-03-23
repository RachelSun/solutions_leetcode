# 2.Add Two Numbers

** Problem:**

You are given two linked lists representing two non-negative numbers. The digits are stored in reverse order and each of their nodes contain a single digit. Add the two numbers and return it as a linked list.


    Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)

    Output: 7 -> 0 -> 8


**My Solutions:**

Date: March 23, 2016

    // Run Time Error, this is a wrong answer.
    
    /*
     * Definition for singly-linked list.
     * struct ListNode {
     *     int val;
     *     ListNode *next;
     *     ListNode(int x) : val(x), next(NULL) {}
     * };
     */
    class Solution {
    public:
        ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {

            ListNode n(0);
            ListNode* sum = &n;
            int temp;

           // ListNode* sum;
            int flag = 0;
            while(l1 || l2)
            {
                temp = l1->val+l2->val+flag;
                if(temp/10){
                    sum->next =new ListNode(temp%10);
                    flag = 1;
                } 
                else{
                    sum->next = new ListNode(temp);
                    flag = 0;
                }
                sum = sum->next;
                if(l1){
                    l1 = l1->next;
                }
                if(l2){
                    l2 = l2->next;
                }
            }
            if(temp/10!= 0) {
                sum->next = new ListNode(temp/10);
                sum = sum->next;
            }
            return n.next;
        }
    };