//5.Given a binary search tree and data of two nodes, find 'LCA' (Lowest Common Ancestor) of the given two nodes in the BST.

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

Tree<int>*BST(Tree<int>*root,int val)
{
	if(root==NULL)
	{
		Tree<int>*nn=new Tree<int>(val);
		return nn;
		
	}
	else
	{
		if(root->data>val)
			root->left=BST(root->left,val);
		
		else
			root->right=BST(root->right,val);
		
		
	}
	return root;
}

void inorder(Tree<int>*root)
{
	if(root==NULL)
	return;
	
	inorder(root->left);
	cout<<root->data<<" ";
	inorder(root->right);
}



Tree<int>*lowestCommonAncestor(Tree<int>* root,int p,int q) {
        
        if(root==NULL)
            return NULL;
        
        if((root->data)==p || (root->data)==q)
            return root;
        
        Tree<int>* l=lowestCommonAncestor(root->left,p,q);
        Tree<int>* r=lowestCommonAncestor(root->right,p,q);
        
        if(l!=NULL && r!=NULL)
            return root;
        else
        {
            if(l!=NULL && r==NULL)
                return l;
            else
                return r;
        }
        
        
    }

int main()
{
	Tree<int>*root;
	int n;
	cout<<"Enter number of nodes= ";
	cin>>n;
	
	for(int i=1;i<=n;i++)
	{
		int x;
		if(i==1)
		{
			cout<<"Enter data of root= ";
			cin>>x;
			root=new Tree<int>(x);
			
			
		}
		else
		{
			cout<<"Enter data of node "<<i<<" = ";
			cin>>x;
			root=BST(root,x);
			
		}
	}
	int p,q;
	cout<<"Enter data two nodes= ";
	cin>>p>>q;
	cout<<"Inorder Traversal of BST= "<<endl;
	inorder(root);
	
	cout<<endl<<"Lowest Common Ancestor= "<<lowestCommonAncestor(root,p,q)->data;
	
	
	return 0;
}

/*
Enter number of nodes= 5
Enter data of root= 43
Enter data of node 2 = 7
Enter data of node 3 = 9
Enter data of node 4 = 2
Enter data of node 5 = 4
Enter data two nodes= 2
4
Inorder Traversal of BST=
2 4 7 9 43
Lowest Common Ancestor= 2
*/
