import static java.lang.Math.max; 
import java.util.Scanner;
/**
 * Write a description of class Submission here.
 *
 * @author (Anish Joshi)
 * @version (05/03/2021)
 */
public class Submission
{
    public static void main(String args[]){
        int n = Integer.parseInt(args[0]);
        
        Scanner sc = new Scanner(System.in);
        
        int matrix[][] = new int[n][n];
        
        int row,column = 0;
        
        row = n;
        column = n;
        
        int value = -1;
   
        for(int i = 0; i < row; i++)
           //checks the maximum value of the first row 
           value = max(value, matrix[0][i]);
        

        for(int x = 0; x < column; x++){// after we checked the first value of the first row, we check the second value of the first row onwards
          for(int y = 0; y < row; y++){
             matrix[x][y] = sc.nextInt();
          }
        }
        for(int i = 1; i < column; i++){// after we checked the first value of the first row, we check the second value of the first row onwards
           for(int j = 0; j < row; j++){
               if(j > 0 && j < row-1){
                   //checks both paths of the value 
                   matrix[i][j] +=  max(matrix[i-1][j-1],
                                    matrix[i-1][j+1]);
                                  
                   
               }
               //checks the left path of the value
               else if(j > 0){
                   matrix[i][j] += matrix[i-1][j-1];
                                   
               }
               //checks if the right path of the value
               else if(j < row-1){
                   matrix[i][j] += matrix[i-1][j+1];
                                   
               }
               //finds the maximum value 
               value = max(matrix[i][j],value);
            }
        }
        System.out.println(value);// prints the maximum value 
     }
  }
