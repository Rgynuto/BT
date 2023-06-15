/**
 * Traverses a binary tree
 * @param {Object} root - The root node of the binary tree
 * @param {Function} callback - The callback function to be called on each node
 */
function traverseBinaryTree(root, callback) {
  // Check if root is valid
  if (!root) {
    console.error('Root node is invalid');
    return;
  }

  // Check if callback is valid
  if (typeof callback !== 'function') {
    console.error('Callback is not a function');
    return;
  }

  // Traverse the tree
  (function traverse(node) {
    // Call the callback on the node
    callback(node);

    // Traverse the left subtree
    if (node.left) {
      traverse(node.left);
    }

    // Traverse the right subtree
    if (node.right) {
      traverse(node.right);
    }
  })(root);
}
