#include<bits/stdc++.h>
using namespace std;
struct Node {
    int data;
    struct Node* left, *right;
};
Node* newNode(int data)
{
    Node* temp = new Node;
    temp->data = data;
    temp->left = temp->right = nullptr;
    return temp;
}
// A function to print all left boundary nodes, except a
// leaf node. Print the nodes in TOP DOWN manner
void printBoundaryLeft(Node* root)
{
    if (root == nullptr)
        return;

    if (root->left) {
        // to ensure top-down order, print the node
        // before calling itself for the left subtree
        cout << root->data << " ";
        printBoundaryLeft(root->left);
    }
    else if (root->right) {
        cout << root->data << " ";
        printBoundaryLeft(root->right);
    }
    // do nothing if it is a leaf node, this way we avoid
    // duplicates in output
}
// A function to print all right boundary nodes, except a
// leaf node. Print the nodes in BOTTOM UP manner
void printBoundaryRight(Node* root)
{
    if (root == nullptr)
        return;

    if (root->right) {
        // to ensure bottom-up order, first call for the right
        // subtree, then print this node
        printBoundaryRight(root->right);
        cout << root->data << " ";
    }
    else if (root->left) {
        printBoundaryRight(root->left);
        cout << root->data << " ";
    }
    // do nothing if it is a leaf node, this way we avoid
    // duplicates in output
}
// A function to print all leaf nodes
void printLeaves(Node* root)
{
    if (root == nullptr)
        return;

    printLeaves(root->left);

    // Print it if it is a leaf node
    if (!root->left && !root->right)
        cout << root->data << " ";

    printLeaves(root->right);
}

// A function to do boundary traversal of a given binary tree
void printBoundary(Node* root)
{
    if (root == nullptr)
        return;

    cout << root->data << " ";

    // Print the left boundary in top-down manner.
    printBoundaryLeft(root->left);
    printLeaves(root);

    printBoundaryRight(root->right);
}
int main()
{
    // Let us construct the tree given in the above diagram
    Node* root = newNode(20);
    root->left = newNode(8);
    root->left->left = newNode(4);
    root->left->right = newNode(12);
    root->left->right->left = newNode(10);
    root->left->right->right = newNode(14);
    root->right = newNode(22);
    root->right->right = newNode(25);
    printBoundary(root);
    return 0;
}
