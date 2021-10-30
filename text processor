/**
 * Keep track of words.
 *
 * @Anish Joshi
 * @05/01/2021 
 */
import java.util.*; 

public class TextProcessor

{   
    private HashMap<String, Integer> words;
    private String suffix;
   

    /**
     * Constructor for objects of class TextProcessor
     */
    public TextProcessor()
    {
      words = new HashMap<>();
      this.suffix = suffix;
      
    }
    
    /**
    * Add a word to the processor.
     * @param word the word to be added.
     */
    public void addWord(String word)
    {
       
        if(words.containsKey(word)){
            words.put(word,words.get(word)+1);
        }    
        else{
            words.put(word, 1);
        }
        
    }
      
    /**
     * Get the number of times the given word has added
     * via addWord.
     * @param word The word to be looked up.
     * @return How many times the word has been added.
     */
    public int howMany(String word)
    {
        int count = 0;
        if (words.containsKey(word)){
             count =  words.get(word);
        }
        return count; 
    }
    
    /**
     * Return the number of distinct words str is a
     * suffix of in the words added so far.
     * 
     * It counts as a suffix if a word ends with
     * str but str does not also match the whole word.
     * For instance: "thing" matches the following 3 examples:
     *     "something" "nothing" "thing"
     * but only the first two qualify as proper suffix matches.
     * 
     * Each word that contains the suffix must only be counted once,
     * so if "something" has been added 3 times, that only counts
     * as 1 match.
     * @param str The suffix to look for.
     * @return the number of distinct words with the given suffix. 
     */
    public int suffixCount(String str) 
    {
      int count = 0;
      for(String suffix : words.keySet()){
         if( !suffix.equals(str) && suffix.endsWith(str)){
             count++;
         }
         
      }
      
      return count;    
    }
    
     
    /**
     * Count the number of distinct case-insensitive anagrams
     * of the given word that have been added to the processor. 
     * 
     * An anagram consists of exactly the same number of
     * letters as the given word, each character occurring
     * the same number of times. It does not count as an
     * anagram if the two words are already identical.
     * 
     * For instance: "and" is an anagram of "Dan" but
     *               "nan" is neither an anagram of "naan" nor "nan".
     *
     * @param word The word to be compared.
     * @return the number of case-insensitive anagrams
     *         of word.
     */
    public int anagramCount(String word)
    {
       int count = 0;
       boolean s = true;
       for(String w: words.keySet()){
           if(w.length() == words.size()){
               s = false;
           }
            else{
               if(!w.equals(word)){
                 
                   char[] Array1 = word.toCharArray();
                   char[] Array2 = w.toCharArray();
             
                   Arrays.sort(Array1);
                   Arrays.sort(Array2);
             
                   s = Arrays.equals(Array1, Array2);
             
                   if(s){
                       count++;
             } 
          
            }
       
         }
          
       }
       return count;
       
    }
       
  }
    
