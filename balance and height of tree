/**
 * Assessment 1 COMP5180 
 * 
 * Setting up binary search trees for storing data on students electing to study remotely and their module choices.
 * Nodes consist of int keys for student ids and string arrays for module choices data
 *
 * @version 4
 *   
 * @author Anish Joshi 
 * 
 * @author akj22 (v3, 2) 
 * @author smk (v1)
 * 
 * Changes: edited from v2 (class exercises) for the assignment
 * 
 * Autumn 2021
 * 
 * Task 2-A recommendation for a flexible data strucutre would be a Tree. This is 
 * because, due to its flexibility,it makes it easy to add and manipulate data within the 
 * data structue and easy to keep track off due to each node being assigned a pointer for easy accessibility. This allows large data sets such as change of student and module deatils
 * easier to add and remove within the data structure. Although a substantial amount of memory
 * is dedidcated to the data references(75%), it is may more flexible for allowing more data about 
 * the online students to be added in the future, making it much easier to due to the spontaneity of choosing different modules or deatils about the students. 
 * Whereas, fixed data structure only allow
 * a fixed amount of space and may run into a stop-the-world scenario(neccessary to free up memory within the computer). 
 *  
 * The way I would implement the tree data structure for the array modules is by creating a class called Node and define the initial node, the left and right node. Then we can create our manin class called modules
 * and after we can define the constructor method and create the root node and set the nodes to null. No changes to the constructor are required besides this.
 * Then we can create our own methods to mainupalate the data structure such as insert,search and delete. Each method will need to store the node paramenter in order to keep track of each node.
 * inserted,deleted or searched(depending on what function of the method).
 * This will make it much easier to manipulate the data structure as it is no longer fixed, and can
 * grow over time depending the amount of data held on the modules of the students. 
 * 
 */

import java.util.Random;
import java.lang.Math;

public class RemoteStudyBST
{
    // instance variables 
    private int key;
    private RemoteStudyBST left,right;
    private String[] modules; 

    //fixed BST that is the dedicated empty tree, by convention
    public static final RemoteStudyBST empty=new RemoteStudyBST();
    
    //global random number generator
    private static final Random rg=new Random();
    
    //private constructor, only used for empty tree, once
    private RemoteStudyBST() {}
    
    public static RemoteStudyBST empty() { return empty; }
    public boolean isEmpty() { return this==empty; }
    
    /**
     * Constructor for singleton BST
     * Use this constructor
     */
    public RemoteStudyBST(int studentID, String[] studentModules)
    {
        key=studentID;

        modules = studentModules;

        //set up left and right child nodes
        left=right=empty;
    }

    public boolean search(int k) {
        if (isEmpty()) return false;
        if (k==key) return true;
        if (k<key) return left.search(k);
        else return right.search(k);
    }
    
    public int size() {
        if (isEmpty()) return 0;
        return left.size()+right.size()+1;
    }
    
    //add k to BST if it is not already there
    public RemoteStudyBST insert(int studentID, String[] studentModules) {
        if (isEmpty()) return new RemoteStudyBST(studentID, studentModules);
        if (studentID<key) {
            left=left.insert(studentID, studentModules);
        } else if (studentID>key) {
            right=right.insert(studentID, studentModules);
        }
        return this;
    }
    
    //create a random tree by inserting n distinct random numbers (between 1 and 4n)
    //into an empty tree
    public static RemoteStudyBST randomTree(int n) {
        RemoteStudyBST res=empty;
        for (int i=0; i<n; i++) {
            int k;
            do {//loop ensures number is fresh
                k=rg.nextInt(4*n)+1;
            } while (res.search(k));
            res=res.insert(k, null);
        }
        return res;
    }
    /**
     * Finds the true height of the tree
     */
    public int height() {
        if(isEmpty()){
          return -1;
       }
    
       int leftDepth = left.height();
       int rightDepth = right.height();
    
        if (leftDepth > rightDepth)
            return (leftDepth + 1);
        else
            return (rightDepth + 1);
            
        }
    
    
   /**
    * Finds if the tree is AVL or not
    */
   public boolean isAVL() {
        return avlHeight() != -1;
    }
    private int avlHeight() {
        if (isEmpty()){
            return -1;// checks if tree is empty
        }
        
        int l=left.avlHeight();// uses recursion to find the avlHeight
        int r=right.avlHeight();
        
        if (l==-1 || r==-1){
            return -1;// 
        }
        if (l+1<r || r+1<l){
            return -1;
        }
        return Math.max(l,r)+1;
    }
    
    public static void randomReport(int size) {
        //try 100 random trees of size
        //what percentage is AVL? what percentage can be expressed as a RB tree
        
    }

    private String printModules()  {
        String modulesString = "";
        for (int i=0; i<modules.length; i++)  {
            modulesString += modules[i] + " ";
        }
        return modulesString;
    }
    
    public String toString() {
        return toString("");
    }
    private String toString(String lead) {
        if (isEmpty()) return lead + "E\n"; 
        return lead + key + "   "  + printModules() + "\n" + left.toString(lead+"    ") + right.toString(lead+"    ");
    }
    
    //a bunch of methods to check whether a tree can be red-black-coloured
    private int stumpHeight() {
        if (isEmpty()) return 0;
        return Math.min(left.stumpHeight(),right.stumpHeight())+1;
    }
    
    private boolean redblackable(int bh,boolean redok) {
        if (isEmpty()) return bh==0;
        int nbh;
        if (stumpHeight()==bh || !redok) { nbh=bh-1; } else { nbh=bh; }
        return left.redblackable(nbh,nbh<bh) && right.redblackable(nbh,nbh<bh);
    }
    
    public boolean redblackable() {
        return redblackable(stumpHeight(),false);
    }

    /** 
     * Task 1- This prints out the the student ID and the list of modules they are taking 
     */
    public void printSortedData(){
        if(!isEmpty()){
            left.printSortedData();
            System.out.println(key+ " "+printModules());//we use in order traversal to find print the id and modules in the specific format required
            right.printSortedData();
        }
        else{
            return;//if the tree is empty, the method will return nothing 
            
        }
         
    }
    
  
    /** 
     * checks if the tree is balanced or not 
     */

     public boolean isBalanced(){
        if(isEmpty()){
           return true;
        }
        
       int leftDepth = left.height();// uses recursion to find the true left height of the tree for our conditional to check if tree is balanced later 
       int rightDepth = right.height();// uses recursion to find the true right height of the tree for our conditional to check if tree is balanced later 
        
        
        if(Math.abs(leftDepth-rightDepth) <= 1 && left.isBalanced() && right.isBalanced()){// checks if the tree is balanced or not 
            return true;
        }
        
        // retuned if tree is not balanced
        return false;
     }

    
public static void main(String[] args)  {

    //set up sample student id data
    int id1 = 3867;
    int id2 = 2345;
    int id3 = 3467;
    int id4 = 4555;
   
    
    //set up sample modules data
    String[] modules1 = {"CO61", "CO62", "CO60"};
    String[] modules2 = {"CO31", "CO32", "CO33", "CO35"};
    String[] modules3 = {"CO33", "CO32", "CO34", "CO35"};
    String[] modules4 = {"CO32", "CO22", "CO24", "CO21"};
  

    RemoteStudyBST binSearchTree = new RemoteStudyBST(id1, modules1);  // set up a new instance of BST with root node of the student with key1 and module1 data
    binSearchTree.insert(id2, modules2); // insert the data for student with key2 and module2 data
    binSearchTree.insert(id3, modules3); // insert the data for student with key3 and module3 data
    binSearchTree.insert(id4, modules4); // insert the data for student with key4 and module4 data
    
    
    System.out.println(binSearchTree.toString()); // use the toString method to look at the contents of the tree
    binSearchTree.printSortedData();

    }
}
