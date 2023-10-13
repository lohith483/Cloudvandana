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

	numbers.sort((a, b) => b - a);
	
	console.log(numbers);

 OutPut :  

 	[ 9, 6, 5, 5, 2, 1 ]


 **HTML
1. Create a basic calculator using HTML, CSS, and JavaScript with the functionality of add,
subtract, multiply and divide. Use the following picture forreference**

		<!DOCTYPE html>
		<html>
		<head>
		    <title>Basic Calculator</title>
		    <style>
		        body {
		            font-family: Arial, sans-serif;
		            text-align: center;
		        }
		
		        #calculator {
		            width: 300px;
		            margin: 0 auto;
		            padding: 20px;
		            border: 1px solid #ccc;
		            border-radius: 5px;
		        }
		
		        input[type="text"], input[type="button"] {
		            width: 60px;
		            height: 40px;
		            font-size: 16px;
		        }
		
		        #result {
		            text-align: right;
		            font-size: 20px;
		            margin-bottom: 10px;
		        }
		    </style>
			</head>
			<body>
			
		    <h1>Basic Calculator</h1>
		    <div id="calculator">
		        <input type="text" id="result" disabled>
		        <br>
		        <input type="button" value="1" onclick="appendToResult('1')">
		        <input type="button" value="2" onclick="appendToResult('2')">
		        <input type="button" value="3" onclick="appendToResult('3')">
		        <input type="button" value="+" onclick="appendToResult('+')">
		        <br>
		        <input type="button" value="4" onclick="appendToResult('4')">
		        <input type="button" value="5" onclick="appendToResult('5')">
		        <input type="button" value="6" onclick="appendToResult('6')">
		        <input type="button" value="-" onclick="appendToResult('-')">
		        <br>
		        <input type="button" value="7" onclick="appendToResult('7')">
		        <input type="button" value="8" onclick="appendToResult('8')">
		        <input type="button" value="9" onclick="appendToResult('9')">
		        <input type="button" value="*" onclick="appendToResult('*')">
		        <br>
		        <input type="button" value="C" onclick="clearResult()">
		        <input type="button" value="0" onclick="appendToResult('0')">
		        <input type="button" value="=" onclick="calculateResult()">
		        <input type="button" value="/" onclick="appendToResult('/')">
		    </div>
		
		    <script>
		        function appendToResult(value) {
		            document.getElementById("result").value += value;
		        }
		
		        function clearResult() {
		            document.getElementById("result").value = '';
		        }
		
		        function calculateResult() {
		            try {
		                document.getElementById("result").value = eval(document.getElementById("result").value);
		            } catch (error) {
		                document.getElementById("result").value = 'Error';
		            }
		        }
		    </script>
		    
			</body>
			</html>
   **Create a survey form with Fields; First Name, Last Name, Date of Birth, Country 
(dropdown), Gender (checkbox), Profession, email, and mobile number. All the input 
fields are necessary to submit the form. Create two buttons Submit and Reset. Reset will 
reset the form while clicking on submit, first, it will check all the fields and necessary 
validations and then a popup will appear displaying all the selected values with labels in 
front of it. On closing the popup, the form should reset all the values. Use the following
image for reference**
				
		<!DOCTYPE html>
		<html>
		<head>
		    <title>Customer Survey Form</title>
		    <style>
		        body {
		            font-family: Arial, sans-serif;
		            background-color: #f0f0f0;
		            
		        }
		
		        h1{
		            text-align: center;
		        }
		
		        
		        .container {
		            width: 400px;
		            margin: 0 auto;
		        }
		
		        .form-group {
		            margin-bottom: 10px;
		        }
		
		        label {
		            display: block;
		            font-weight: bold;
		        }
		
		        input[type="text"], input[type="date"], select {
		            width: 100%;
		            padding: 5px;
		        }
		
		        .radio-group {
		            display: inline-block;
		            margin-right: 20px;
		        }
		
		        #submit, #reset {
		            padding: 10px 20px;
		            background-color: #0074D9;
		            color: #fff;
		            border: none;
		            cursor: pointer;
		        }
		    </style>
		</head>
		<body>
		    <h1>Customer Survey Form</h1>
		    <div class="container">
		        <form id="surveyForm">
		            <div class="form-group">
		                <label for="firstName">First Name:</label>
		                <input type="text" id="firstName" required>
		            </div>
		
		            <div class="form-group">
		                <label for="lastName">Last Name:</label>
		                <input type="text" id="lastName" required>
		            </div>
		
		            <div class="form-group">
		                <label for="dob">Date of Birth:</label>
		                <input type="date" id="dob" required>
		            </div>
		
		            <div class="form-group">
		                <label for="country">Country:</label>
		                <select id="country" required>
		                    <option value="" disabled selected>Select your country</option>
		                    <option value="USA">USA</option>
		                    <option value="Canada">Canada</option>
		                    <!-- Add more country options here -->
		                </select>
		            </div>
		
		            <div class="form-group">
		                <label>Gender:</label>
		                <div class="radio-group">
		                    <input type="radio" name="gender" id="male" value="Male" required>
		                    <label for="male">Male</label>
		                </div>
		                <div class="radio-group">
		                    <input type="radio" name="gender" id="female" value="Female" required>
		                    <label for="female">Female</label>
		                </div>
		            </div>
		
		            <div class="form-group">
		                <label for="profession">Profession:</label>
		                <input type="text" id="profession" required>
		            </div>
		
		            <div class="form-group">
		                <label for="email">Email:</label>
		                <input type="email" id="email" required>
		            </div>
		
		            <div class="form-group">
		                <label for="mobile">Mobile Number:</label>
		                <input type="tel" id="mobile" required>
		            </div>
		
		            <div class="form-group">
		                <button type="button" id="submit">Submit</button>
		                <button type="button" id="reset">Reset</button>
		            </div>
		        </form>
		    </div>
		
		    <script>
		        document.getElementById('submit').addEventListener('click', function() {
		            let form = document.getElementById('surveyForm');
		            if (form.checkValidity()) {
		                let firstName = document.getElementById('firstName').value;
		                let lastName = document.getElementById('lastName').value;
		                let dob = document.getElementById('dob').value;
		                let country = document.getElementById('country').value;
		                let gender = document.querySelector('input[name="gender"]:checked').value;
		                let profession = document.getElementById('profession').value;
		                let email = document.getElementById('email').value;
		                let mobile = document.getElementById('mobile').value;
		                let popupContent = `
		                    <h2>Survey Form Data</h2>
		                    <p><strong>First Name:</strong> ${firstName}</p>
		                    <p><strong>Last Name:</strong> ${lastName}</p>
		                    <p><strong>Date of Birth:</strong> ${dob}</p>
		                    <p><strong>Country:</strong> ${country}</p>
		                    <p><strong>Gender:</strong> ${gender}</p>
		                    <p><strong>Profession:</strong> ${profession}</p>
		                    <p><strong>Email:</strong> ${email}</p>
		                    <p><strong>Mobile Number:</strong> ${mobile}</p>
		                    <p>Thank you for submitting the form!</p>
		                `;
		
		                let popup = window.open('', 'Survey Form Data', 'width=400,height=400');
		                popup.document.write(popupContent);
		                popup.focus();
		                form.reset();
		            } else {
		                alert('Please fill out all required fields.');
		            }
		        });
		
		        document.getElementById('reset').addEventListener('click', function() {
		            let form = document.getElementById('surveyForm');
		            form.reset();
		        });
		    </script>
		</body>
		</html>



