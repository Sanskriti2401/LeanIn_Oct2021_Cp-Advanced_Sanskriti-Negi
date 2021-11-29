/*3.Given a binary tree, remove all leaf nodes from it.Leaf nodes are those nodes, which don't have any children*/

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

void levelOrder(Tree<int>*root)
{
	queue<Tree<int>*>q;
	
	q.push(root);
	
	while(!q.empty())
	{
		int n=q.size();
		for(int i=0;i<n;i++)
		{
			Tree<int>*temp=q.front();
			q.pop();
			if(temp->left!=NULL)
			{
				q.push(temp->left);
			
			}
		
			if(temp->right!=NULL)
			{
				q.push(temp->right);
			
			}
			cout<<temp->data<<" ";
		}
		cout<<endl;
	
		
		
	}		
	
}


Tree<int>*remove(Tree<int>*root)
{
	if(root==NULL)
	return NULL;
	
	if(root->left==NULL && root->right==NULL)
	{
		delete(root);
		return NULL;
	}
	
	root->left=remove(root->left);
	root->right=remove(root->right);
	
	return root;	
	
}

int main()
{
	Tree<int>*root=input();
	
	cout<<"Level Order Traversal of Binary Tree= "<<endl;
	levelOrder(root);
	cout<<endl;	
	root=remove(root);
	levelOrder(root);
	return 0;
}

/*
Enter root data= 4
Enter left child of 4 = 6
Enter right child of 4 = 8
Enter left child of 6 = 2
Enter right child of 6 = -1
Enter left child of 8 = -1
Enter right child of 8 = 5
Enter left child of 2 = 2
Enter right child of 2 = -1
Enter left child of 5 = -1
Enter right child of 5 = -1
Enter left child of 2 = -1
Enter right child of 2 = -1
Level Order Traversal of Binary Tree=
4
6 8
2 5
2

4
6 8
2
*/
