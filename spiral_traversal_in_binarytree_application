#include <bits/stdc++.h>
using namespace std;
struct node {
	int data;
	struct node* left;
	struct node* right;
};

struct node* newNode(int data)
{
	node* newnode = new node();
	newnode->data = data;
	newnode->left = NULL;
	newnode->right = NULL;

	return (newnode);
}

int sumOfNodesWithOneLeftChild(struct node* root)
{
	if (root == NULL)
		return 0;

	int sum = 0;

	if(root->left!=NULL&&root->right==NULL)
	{
		sum += root->data;
	}

	// Recursively process the left and right subtrees
	sum += sumOfNodesWithOneLeftChild(root->left);
	sum += sumOfNodesWithOneLeftChild(root->right);

	return sum;
}

int main()
{
	struct node* root = newNode(8);
	
	root->left = newNode(3);
	root->left->left = newNode(10);
	root->left->left->left = newNode(1);
	root->left->left->left->left = newNode(6);
	root->left->right = newNode(9);
	root->right = newNode(14);
	root->right->right = newNode(8);

	int sum = sumOfNodesWithOneLeftChild(root);
	cout << "Sum of elements with only one left child: "<<sum<<endl;

	return 0;
}
/*
#include "bits/stdc++.h"
using namespace std;
struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};
int sumNodesWithOnlyLeftChild(TreeNode* root) {
    if (root == nullptr) {
        return 0;
    }
    int sum = 0;
    if (root->left != nullptr && root->right == nullptr) {
        sum += root->val;
    }
    sum += sumNodesWithOnlyLeftChild(root->left);
    sum += sumNodesWithOnlyLeftChild(root->right);
    return sum;
}
int main() {
    TreeNode* root = new TreeNode(10);
    root->left = new TreeNode(20);
    root->right = new TreeNode(30);
    root->left->left = new TreeNode(40);
    root->left->right = new TreeNode(50);
    root->right->left = new TreeNode(60);
    int sum = sumNodesWithOnlyLeftChild(root);
    cout<<sum<< endl;
}
*/
