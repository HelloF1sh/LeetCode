# LeetCode 刷题记录 (python)
### 树
##### 二叉树
```python
# 前序遍历
# 递归(隐式栈),python函数应该是引用传递
def preorderTraversal(self, root: TreeNode) -> List[int]:
   def traver(root: TreeNode, res: List) :
       if not root:
           return 
       res.append(root.val)
       traver(root.left, res)
       traver(root.right, res)

   res = []
   traver(root, res)
   return res
# 迭代(显示栈)
def preorderTraversal(self, root: TreeNode) -> List[int]:
  stack, res = [],[]
  cur = root
  while cur or stack:
      if cur:
        res.append(cur.val)
        stack.append(cur)
        cur = cur.left
      else:
        cur = stack.pop()
        cur = cur.right
        
# 中序遍历
# 遍历
def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        stack, res =[], []
        cur = root
        while stack or cur:
            if cur:
                stack.append(cur)
                cur = cur.left
            else:
                cur = stack.pop()
                res.append(cur.val)
                cur = cur.right
        
        return res
