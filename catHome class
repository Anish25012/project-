import java.util.*;
/**
 * Write a description of class catHome here.
 *
 * @author (Anish Joshi)
 * @version (04/02/2021)
 */
public class catHome
{
    private LinkedList<Cat> catList;
    private HashSet<Cat> catSet;
    public catHome(){
        catList = new LinkedList<Cat>();
        catSet = new HashSet<Cat>();
    }
    /**
     * adds the cat object to the linkedlist
     */
    public void addCat(Cat cat){
        catList.add(cat);
       
    }
    /**
     * prints out all the cats that are unvaccinated
     */
    public void printUnvaccinated(){
        for(Cat c : catList){
            if(c.Vaccinated() == false){
                System.out.println(c.getDetails());
            }
        }
    }
    /**
     * adds the cats to the hashset and removes them from the Linkedlist
     * the method then returns the cats that are vaccinated in the Hashset
     */
    public HashSet getVaccinated(){
        if(catSet == null || catSet.size()> 0){
            Iterator<Cat> newIt = catSet.iterator();
            while(newIt.hasNext()){
                 Cat c = newIt.next();
                 if(c.Vaccinated() == true){
                     catSet.add(c);
                     Iterator<Cat> it = catList.iterator();
                     while(it.hasNext()){
                         Cat cat = it.next();
                         if(c == it){
                             it.remove();
                   }
               }    
               
           }
        }
   
    }
    return catSet;
   } 
}
