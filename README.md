Binary-Tree-level-Order-Traversal-II
====================================


/**
 * Definition for binary tree
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
public class Solution {
    public ArrayList<ArrayList<Integer>> levelOrderBottom(TreeNode root) {
        // Start typing your Java solution below
        // DO NOT write main() function
        
        ArrayList<ArrayList<Integer>> result = new ArrayList<ArrayList<Integer>>();
        
         ArrayList<ArrayList<Integer>> answer = new ArrayList<ArrayList<Integer>>();
         
        if(root == null) return result;
        
        ArrayList<Integer> a = new ArrayList<Integer>();
        
        ArrayList<TreeNode> toVisit = new ArrayList<TreeNode>();
        
        int level = 0;
        
        toVisit.add(root);
        //a.add(root.val);
        //result.add(a);
        
        //HashMap<ArrayList<TreeNode>, Integer> table = new HashMap<ArrayList<TreeNode>,Integer>();
        
        //table.put(toVisit,level);
        
        while(!toVisit.isEmpty()){
            
            ArrayList<Integer> list = new ArrayList<Integer>();
            
            ArrayList<TreeNode> temp = new ArrayList<TreeNode>();
            
            
             for(int i = 0; i < toVisit.size();i++){
                 
            list.add(toVisit.get(i).val);
                      
             }
             
              result.add(list);
            
            
            for(int i = 0; i < toVisit.size();i++){
                TreeNode node = toVisit.get(i);
                if(node.left !=null) temp.add(node.left);
                
                if(node.right !=null) temp.add(node.right);
            }
            
            
            
            level++;
           
            toVisit = temp;
        }
        
        for(int i = result.size()-1; i>=0; i--){
            ArrayList<Integer> temp = new ArrayList<Integer>();
            
            temp = result.get(i);
            
            answer.add(temp);
        }
        
        return answer;
        
        
    }
}
