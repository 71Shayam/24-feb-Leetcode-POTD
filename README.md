ListNode* deleteDuplicates(ListNode* head) {
        if(head == NULL || head->next == NULL){
            return head;
        }

        int temp = head->val;
        ListNode* tempHead = head->next;
        ListNode* prev = head;
        while(tempHead != NULL){
            if(tempHead->val != temp){
                temp = tempHead->val;
                prev = tempHead;
                tempHead = tempHead->next;
            }
            else{
                prev->next = tempHead->next;
                tempHead = prev->next;
            }
        }

        return head;
    }
