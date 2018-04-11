# Remove Nth Node From End of List

``` py
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def removeNthFromEnd(self, head, n):
        """
        :type head: ListNode
        :type n: int
        :rtype: ListNode
        """
        # edge case
        slow = fast = head
        for _ in range(n):
            fast = fast.next
            
        if not fast:
            return head.next
        while fast.next:
            slow = slow.next
            fast = fast.next
        
        slow.next = slow.next.next
        
        return head
```