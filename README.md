# Cloudvandana
**1. Create an array with the values (1, 2, 3, 4, 5, 6, 7) and shuffle it.**

import java.util.Arrays;

import java.util.Collections;

import java.util.List;

class Main {
    
    public static void main(String[] args) {
        Integer[] myArray = {1, 2, 3, 4, 5, 6, 7};

        List<Integer> list = Arrays.asList(myArray);
        Collections.shuffle(list);
        
        System.out.println("Shuffled Array: " + list);
    }
}

**2. Enter a Roman Number as input and convert it to an integer. (Example: IX = 9)**

import java.util.HashMap;

import java.util.Map;

public class Main {
    
    public static int romanToInteger(String s) {
        Map<Character, Integer> romanValues = new HashMap<>();
        romanValues.put('I', 1);
        romanValues.put('V', 5);
        romanValues.put('X', 10);
        romanValues.put('L', 50);
        romanValues.put('C', 100);
        romanValues.put('D', 500);
        romanValues.put('M', 1000);

        int result = 0;
        int prevValue = 0;

        for (int i = s.length() - 1; i >= 0; i--) {
            int value = romanValues.get(s.charAt(i));
            if (value < prevValue) {
                result -= value;
            } else {
                result += value;
            }
            prevValue = value;
        }

        return result;
    }

    public static void main(String[] args) {
        String romanNumeral = "IX";
        int integerEquivalent = romanToInteger(romanNumeral);
        System.out.println(romanNumeral + " = " + integerEquivalent);
    }
}


**3. Check if the input is pangram or not. (A pangram is a sentence that contains all the
alphabets from A to Z)**

import java.util.HashSet;

import java.util.Scanner;

import java.util.Set;

public class Main {

    public static boolean isPangram(String sentence) {
        sentence = sentence.toLowerCase();
        Set<Character> alphabetSet = new HashSet<>();
        for (char c : sentence.toCharArray()) {
            if (Character.isLetter(c)) {
                alphabetSet.add(c);
            }
        }
        return alphabetSet.size() == 26;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a sentence: ");
        String inputSentence = scanner.nextLine();

        if (isPangram(inputSentence)) {
            System.out.println("The sentence is a pangram.");
        } else {
            System.out.println("The sentence is not a pangram.");
        }

        scanner.close();
    }
}

**JavaScript
1. Take a sentence as an input and reverse every word in that sentence.
Example - This is a sunny day > shiT si a ynnus yad.**

function reverseWords(sentence) 

	{

    const words = sentence.split(" ");
    const reversedWords = words.map(word => {
        return word.split("").reverse().join("");
    });
    const reversedSentence = reversedWords.join(" ");
    
    return reversedSentence;
	}
 	const inputSentence = "This is a sunny day";
	const reversed = reverseWords(inputSentence);
	console.log(reversed);

Output:
	
 sihT si a ynnus yad

**2. Perform sorting of an array in descending order.**

	const numbers = [5, 2, 9, 1, 5, 6];
	
	// Sort the array in descending order
	numbers.sort((a, b) => b - a);
	
	console.log(numbers);

 OutPut :  

 [ 9, 6, 5, 5, 2, 1 ]


 **HTML
1. Create a basic calculator using HTML, CSS, and JavaScript with the functionality of add,
subtract, multiply and divide. Use the following picture forreference**

