#include<iostream>
#include<bits/stdc++.h>

using namespace std;

template<typename T>
class Tree{
	
	public:
		T data;		
		Tree* left;
		Tree* right;
		
		Tree(T data)
		{
			this->data=data;
			left = NULL;
			right = NULL;
		}
		
		~Tree()
		{
			delete left;
			delete right;
		}
};

Tree<int>*input()
{
	int val;
	cout<<"Enter root data= ";
	cin>>val;
	Tree<int>*root=new Tree<int>(val);
	queue<Tree<int>*>q;
	
	q.push(root);
	
	while(!q.empty())
	{
		Tree<int>*temp=q.front();
		q.pop()	;
		
		cout<<"Enter left child of "<<temp->data<<" = ";
		int x;
		cin>>x;
		if(x!=-1)
		{
			Tree<int>*child=new Tree<int>(x);
			temp->left=child;
			q.push(child);
			
		}
		
		cout<<"Enter right child of "<<temp->data<<" = ";
		int y;
		cin>>y;
		if(y!=-1)
		{
			Tree<int>*child2=new Tree<int>(y);
			temp->right=child2;
			q.push(child2);
		}
		
	}
	return root;		
	
}

int isbalance(Tree<int>*root)
{
	if(root==NULL)
	return 0;
	
	int l=isbalance(root->left);
    int r=isbalance(root->right);
    
    if(abs(l-r)>1)
        return -1;
    if(l==-1 || r==-1)
        return -1;
        
    return max(l,r)+1;

}

int main()
{
	Tree<int>*root=input();
	
	if(isbalance(root)==-1)
		cout<<"Tree is not balanced";
	else
		cout<<"Tree is balanced";
	
	return 0;
}

/*
Enter root data= 4
Enter left child of 4 = 1
Enter right child of 4 = 2
Enter left child of 1 = 4
Enter right child of 1 = -1
Enter left child of 2 = -1
Enter right child of 2 = 7
Enter left child of 4 = 1
Enter right child of 4 = -1
Enter left child of 7 = -1
Enter right child of 7 = 9
Enter left child of 1 = -1
Enter right child of 1 = -1
Enter left child of 9 = -1
Enter right child of 9 = -1
Tree is not balanced
*/
