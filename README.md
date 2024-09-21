# Binary-Tree-Level-Order-Traversal

Given the root of a binary tree, return the level order traversal of its nodes' values. (i.e., from left to right, level by level).

class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        self.d=defaultdict(list)
        def foo(x,depth):
            self.d[depth].append(x.val)
            if x.left: foo(x.left,depth+1)
            if x.right: foo(x.right,depth+1)
        if root: foo(root,0)
        return [self.d[i] for i in sorted(self.d.keys())]
