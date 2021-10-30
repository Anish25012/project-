mport java.util.ArrayList; 
import java.lang.Math;
/**
 * Keep track of multiple ambulances.
 * @author-Anish Joshi 
 * @version-21/11/2020
 */
public class AmbulanceControl
{
    public ArrayList<Ambulance> totalAmbulance;
     
    /**
     * This part creates an arraylist called totalAmbulance.
     */
    public AmbulanceControl()
    {
     totalAmbulance = new ArrayList<>();
     
      
    }
    
    /**A
     *This adds a new ambulance to the arraylist
     * 
     */
    public void addAmbulance(Ambulance ambulance)
    {
        totalAmbulance.add(ambulance);
        
    }
    
    /**
     * 
     * returns the number of ambulances in the arraylist.
     */
    public int getNumberOfAmbulances()
    {
        return totalAmbulance.size();
    }
    
    /**
     * Gets and returns the number of ambulances in the given area.
     * 
     */
    public int getNumberOfAmbulances(int area)
    {
        int index = 0;
        for(Ambulance a : totalAmbulance) {
            if (a.getArea() == area){
                index++;
        
            }
        }
        return index;
    }
    
    /**
     * Lists all of the ambulances and outputs their deatils.
     */
    public void list()
    {
        for (Ambulance a : totalAmbulance) {
             System.out.println(a.getDetails());
            
            
        }
        
    }
    
    /**
     * Removes the ambulance with the given id.
     * .
     */
    public boolean removeAmbulance(int id){ 
        for (Ambulance a:totalAmbulance) {
           if(a.getID() == id){
               totalAmbulance.remove(a);
               return true; 
           }
           
               
            }
       return false;
           
        }
        
    
    
    /**
     * checks whether there is a free ambulance or not.
     */
    public void setStatus(int id, int area, boolean free)
    {
        
        for (Ambulance a :totalAmbulance){
            if (id == a.getID()){
                a.moveTo(area);
                
            }
            if (free == true){
                a.setFree();
            }
            else{
                free = false;
                a.setBusy();
            }
        
        }
    }
    
    /**
     * Find and returns the nearest free ambulance to the given area.
     * .
     */
    public Ambulance findNearestFree(int area){
        int distance = 0; 
        Ambulance returnValue = null;
        for(Ambulance a: totalAmbulance){
            if (a.isFree()){
                int d = Math.abs(a.getArea()-area);
                if (returnValue == null){
                    distance = d; 
                    returnValue = a; 
                    
                }
                else{
                    if (d < distance){
                        distance = d;
                        returnValue = a;
                    }    
                   
                    else if (distance == d && a.getID() < returnValue.getID()){
                        returnValue = (a); 
                  
                    }
        
                }
          
            }
        
        }
        return returnValue; 
            
  
            
        }
        
    }

