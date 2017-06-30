### 141. Linked List Cycle



 Given a linked list, determine if it has a cycle in it.

 Follow up:  
 Can you solve it without using extra space?





Solutions:

June 30, 2017

/\*\*

 \* Definition for singly-linked list.

 \* struct ListNode {

 \*     int val;

 \*     ListNode \*next;

 \*     ListNode\(int x\) : val\(x\), next\(NULL\) {}

 \* };

 \*/

class Solution {

public:

    bool hasCycle\(ListNode \*head\) {

        // At least three 

        if\(head == NULL \|\| head-&gt;next == NULL\) return false;

        ListNode\* fast = head;

        ListNode\* slow = head;

        while\(fast-&gt;next != NULL && fast-&gt;next-&gt;next != NULL\) {

            fast = fast-&gt;next-&gt;next;

            slow = slow-&gt;next;

            if\(slow == fast\) return true;

        }

        return false;

    }

};





