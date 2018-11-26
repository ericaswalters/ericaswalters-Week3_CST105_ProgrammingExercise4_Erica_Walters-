# ericaswalters-Week3_CST105_ProgrammingExercise4_Erica_Walters-
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */

/**
 *
 * @author J40514
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
