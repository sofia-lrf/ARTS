# 给定一个单链表，将其反转，并返回反转后的链表的头节点
```
class ListNode:
    def __init__(self, val=0):
        self.val = val
        self.next = None

def reverseLinkedList(head):
    current = head
    previous = None

    while current:
        # 暂存当前节点的下一个节点
        next_node = current.next
        # 将当前节点的 next 指针指向前一个节点
        current.next = previous
        # 更新 previous 和 current 节点
        previous = current
        current = next_node

    # 返回反转后的链表的头节点
    return previous

# 创建链表 1 -> 2 -> 3 -> 4 -> 5
head = ListNode(1)
head.next = ListNode(2)
head.next.next = ListNode(3)
head.next.next.next = ListNode(4)
head.next.next.next.next = ListNode(5)

# 反转链表
reversed_head = reverseLinkedList(head)

# 打印反转后的链表
current = reversed_head
while current:
    print(current.val, end=" -> ")
    current = current.next

```

- 上述代码定义了一个链表节点类 ListNode，以及一个函数 reverseLinkedList 来反转链表。通过迭代访问链表节点，每次将当前节点的 next 指向前一个节点，然后更新 previous 和 current 节点，直到遍历完整个链表。最后返回反转后的链表的头节点 previous。

- 运行代码后，会输出反转后的链表的节点值：5 -> 4 -> 3 -> 2 -> 1