# ericaswalters-Week3_CST105_ProgrammingExercise4_Erica_Walters-
/* The following program is the original work of Erica Walters.
 * This program reads from my created text.txt file. The file contains a phrase "It was the perfect night"
 * The program will read the text file and translate the phrase to pig latin.
 * The translated phrase will appeat in the display window at the bottom.
 */

/** Program: Pig Latin
 * File: PigLatin.java
 * Author: Erica Walters
 * Date: November 25, 2018 
 */

import java.io.*;
public class PigLatin {
    final static String VOWELS = "a,e,i,o,u";
    public static int indexOfFirstVowel(String words){
    String loweredWord = words.toLowerCase();
    
    for (int index = 0; index < loweredWord.length(); index++){
        if (VOWELS.contains(String.valueOf(loweredWord.charAt(index)))){
            return index;
        }
    }
    return -1;
    }
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new FileReader((test));           
        try{
        String input = br.readLine();
        String [] words;
        words = input.split(" ");
        System.out.println("Original Input: " + input);
        System.out.println("In Pig Latin: ");
         for (String word : words){
            if (word.startsWith("a")  || word.startsWith("e") || word.startsWith("i") || word.startsWith("o") || word.startsWith("u") || word.startsWith("y") || word.startsWith("A")  || word.startsWith("E") || word.startsWith("I") || word.startsWith("O") || word.startsWith("U") || word.startsWith("Y")) {
                System.out.print(word.toLowerCase() + "yay ");
             }
            else{
                int vowelLoc = indexOfFirstVowel(word);
                String ending = word.substring(0, vowelLoc);
                String editedWord = word.replace(ending, "");
                String finishedWord = editedWord + ending + "ay ";
                System.out.print(finishedWord.toLowerCase());
            }
        } 
        }  catch(StringIndexOutOfBoundsException indexE){
            System.out.println("Invalid input");
           }
    } 
}
