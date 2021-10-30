import java.util.Scanner;
/**
 * Write a description of class Submission here.
 *
 * @author (Anish Joshi)
 * @version (25/03/2021)
 */

class Node{
    int value;
    Node left;
    Node right;
    int count;
    
    public Node(int value){
       this.value = value;
       left = right = null;
       count = 1;
    }
}
 
public class Submission{
    Node root;
    
    public Submission(){
        root = null;
        
    }
    /**
     * inserts an element into the binary tree
     */
    
    public Node insertElement(Node current_node,int value){   
        if(current_node == null){
            return new Node(value);
            
        }
        if(value == current_node.value){
            current_node.count++;
        }
        else if(value < current_node.value){
             current_node.left = insertElement(current_node.left,value); 
        }
        
        else if(value > current_node.value){
            current_node.right = insertElement(current_node.right,value);
        }
        
        return current_node;
      
    }
       
    public void add(int value){
      if(root == null){
         root = insertElement(root, value);
      }
      else{
          insertElement(root, value);
      }
      
     
    }
    /**
     * finds the element the user is looking for
     */
    public boolean findElement(Node current_node,int value){

        try{
            if(current_node == null){
              System.out.println(value+"(0)");//checks if value exists the binary tree, if it doesn't it will print it out
            } 
        
       
         if(value == current_node.value){
            System.out.println(current_node.value+"("+current_node.count+")");// checks if the value is equal to the current node
            return true;
         }
        
        else{
            return value < current_node.value ? findElement(current_node.left,value): findElement(current_node.right,value);//attempts to find the value you are looking for
        }
        
    }
    catch(NullPointerException e){// prevents an error from occuring
         return false;
    }
} 
    /**
     * returns true if the element the user is looking for is found
     */
    public boolean containElement(int value){
        return findElement(root, value);// finds the element in the recursive element
    }
    
    /**
     * deletes the user's element 
     */
    public Node deleteElement(Node current_node,int value){
        
        if(current_node ==  null){
            return null;
        }
        else if(value < current_node.value){
             current_node.left = deleteElement(current_node.left, value);//deletes the element to the left part if it is less than the root node
              
        }   
        else if(value > current_node.value){
            current_node.right = deleteElement(current_node.right, value);//deletes the element to the right part if it is greater than the root node
           
        }
        else{
            
            if(current_node.count > 1){// decreases the count when the user deletes the node
                 current_node.count--;
           
            }
            
            else if(current_node.left == null && current_node.right == null){
                return null;
            }
            
             else if(current_node.left != null && current_node.right != null){
                 Node temp = current_node.left;
                 Node parent_node = current_node;
                 
                 while(temp.right != null){
                     parent_node = temp;
                     temp = temp.right;
                     
                 }
                 
                 
                 current_node.value = temp.value;
                 current_node.count = temp.count;
                 
                 parent_node.right = temp.left;
                 
                 parent_node.right = deleteElement(temp.left, temp.value);
                 
            }
            
            
            else if(current_node.left != null){
                return current_node.left;
            }
            
            else if(current_node.right != null){
                return current_node.right;
            }
            
        }
        return current_node;
    }
    
    /**
     * calls the deleteElement method to delete the user's element 
     */
    
    public void remove(int value){
         root = deleteElement(root, value);
     }
    
    /**
     * finds the lowest possible value stored in the binary true
     */
    public void minElement(){
       Node current_node = root;
        if(current_node != null){
           while(current_node.left != null){
               current_node = current_node.left;
           }
           System.out.println(current_node.value+"("+current_node.count+")"+" ");
       }
       else{
            System.out.println("0"+"(0)");
       }
       
     
    }
    /**
     * finds the lowest possible value stored in the binary true
     */
    public void maxElement(){
       Node current_node = root;
       if(current_node != null){
           while(current_node.right != null){
               current_node = current_node.right;
           }
           System.out.println(current_node.value+"("+current_node.count+")"+" ");
       }
       else{
            System.out.println("0"+"(0)");
       }
       
      
    }
   
    /**
     * prints the binary tree inOrder
     */
    public void inOrder(Node current_node) {
    if (current_node != null){
        inOrder(current_node.left);
        System.out.print(current_node.value+"("+current_node.count+")"+" ");
        inOrder(current_node.right);
    }
    /**
     * calls the inOrder method
     */
   }
   public void printInOrder(){
       inOrder(root);
   }
   
   /**
     * prints the binary tree in pre-order
     */
   public void preOrder(Node current_node){
    if(current_node == null){
        return;
    }
    else{
        System.out.print(current_node.value+"("+current_node.count+")"+" ");
        preOrder(current_node.left);
        preOrder(current_node.right);
    }
    
  }
  /**
   * calls the preorder method
   */
  public void printPreOrder(){
       preOrder(root);
  }
  /**
     * prints the binary tree in post-order
     */
  public void postOrder(Node current_node){
     if(current_node != null){
        postOrder(current_node.left);
        postOrder(current_node.right);
        System.out.print(current_node.value+"("+current_node.count+")"+" ");
     }
  }
  /**
   * calls the post_order method
   */
  public void printPostOrder(){
       postOrder(root);
  }
  /**
   * creates a binaryTree object and prints a number of options to choose from
   */
   
   public static void main(String[] args)
    {
        Submission tree = new Submission();
        
        Scanner sc = new Scanner(System.in);
        
        // tree.add(6);
        // tree.add(4);
        // tree.add(8);
        // tree.add(3);
        // tree.add(5);
        // tree.add(7);
        // tree.add(9);
        
        while(true){
            // System.out.println("\n1. Insert an element into the BST");
            // System.out.println("2. Search for an element in the BST");
            // System.out.println("3. Find the maximum element from the BST");
            // System.out.println("4. Find the minimum element from the BST");
            // System.out.println("5. Print the elements in the BST in preorder");
            // System.out.println("6. Print the elements in the BST in postorder");
            // System.out.println("7. Print the elements in the BST in inorder");
            // System.out.println("8. Delete an element");
            
            int value = sc.nextInt();
        
        switch(value){
            case 1:
            int new_Value = sc.nextInt();
            tree.add(new_Value);
            break;
            
            case 2:
            new_Value = sc.nextInt();
            tree.containElement(new_Value);
            break;
            
            case 3:
            tree.maxElement();
            break;
            
            case 4:
            tree.minElement();
            break;
            
            case 5:
            tree.printPreOrder();
            break;
            
            case 6:
            tree.printPostOrder();
            break;
            
            case 7:
            tree.printInOrder();
            break;
            
            case 8:
            new_Value = sc.nextInt();
            tree.remove(new_Value);
            break;
          
            
            default:
                //System.out.println("Thank you for using my program");
                System.exit(0);
              
            }
         
            
           


        }
    }
 }


   


    
