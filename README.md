# Construct-BST-from-a-sorted-array
BinaryTreeNode<int>* constructTree(int *input, int n) {
	// Write your code here
	if(n == 0){
		return NULL;
	}
	if(n == 1){
			BinaryTreeNode<int>* root = new BinaryTreeNode<int>(input[0]);
			return root;

	}
	int mid;
	if(n % 2 == 0){
		mid = (n/2)-1;
	}
	else{
		mid = n/2;
	}
	BinaryTreeNode<int>* root = new BinaryTreeNode<int>(input[mid]);
	root->left = constructTree(input, mid);
	root->right = constructTree(input + mid + 1, n - mid - 1);
	return root;
}
