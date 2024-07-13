# GlobalTrend_Programming_Assessment
C++ Global trend Programming questions 
#include <iostream>
using namespace std;

class ListNode 
{
public:
    int val;
    ListNode* next;
    ListNode(int x) 
    {
        val = x;
        next = nullptr;
    }
};

ListNode* reverseList(ListNode* head) 
{
    ListNode* prev = nullptr;
    ListNode* curr = head;   
    while (curr != nullptr) 
    {
        ListNode* nextTemp = curr->next;
        curr->next = prev;
        prev = curr;
        curr = nextTemp;
    } 
    return prev;
}

void printList(ListNode* head) 
{
    ListNode* current = head;
    while (current != nullptr) 
    {
        cout << current->val << " ";
        current = current->next;
    }
    cout << endl;
}
int main() 
{
    ListNode* head = new ListNode(1);
    head->next = new ListNode(2);
    head->next->next = new ListNode(3);
    head->next->next->next = new ListNode(4);
    head->next->next->next->next = new ListNode(5);
    cout << "Original list: ";
    printList(head);
    ListNode* reversedHead = reverseList(head);
    cout << "Reversed list: ";
    printList(reversedHead);
    return 0;
}
