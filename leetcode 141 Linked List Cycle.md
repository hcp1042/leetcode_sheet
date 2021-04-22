141. Linked List Cycle

使用快慢指针 来判断是否成环

class Solution:
    def hasCycle(self, head: ListNode) -> bool:
        '''
        fast and slow pointer
        
        '''
        if not head:
            return False
        
        
        fast = head
        slow = head
        second = 0
        
        while fast.next:
            
            slow = slow.next  
            
            if fast.next.next:
                fast = fast.next.next
            else:
                return False
            
            if slow is fast:
                return True
