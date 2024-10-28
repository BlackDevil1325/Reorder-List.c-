# Reorder-List.c++


class Solution 
{
public:
    void reorderList(ListNode* head)
     {  
        vector<ListNode*>a;
        ListNode*cur=head;
        while(cur!=0)
        {
            a.push_back(cur);
            cur=cur->next;
        }
        vector<ListNode*>vec;
        int i=0;
        int j=a.size()-1;
        while(i<=j)
        {
            if(i==j)
            {
                vec.push_back(a[i]);
                break;
            }
            vec.push_back(a[i]);
            vec.push_back(a[j]);
            i++;
            j--;
        }
        head->next=0;
        cur=head;
        for(int i=1;i<vec.size();i++)
        {
            ListNode*t=new ListNode(vec[i]->val);
            cur->next=t;
            cur=cur->next;
        }
    }
};
