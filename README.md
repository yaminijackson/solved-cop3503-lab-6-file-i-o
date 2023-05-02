Download Link: https://assignmentchef.com/product/solved-cop3503-lab-6-file-i-o
<br>
<span class="kksr-muted">Rate this product</span>

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

For this assignment, you are going to load a series of files containing data and search the loaded data for specific criteria. That might sound a bit dry, but the files contain information about LEGO sets, and everyone loves LEGO! The structure of this assignment is a bit open-ended; you can solve this problem in any way that you see fit.

Description

First things first, the files: There are 3 main data files that you will be loading in this assignment:

 lego1.csv  lego2.csv  lego3.csv

The data that you will be loading is information about a LEGO set:

<ol>

 <li>Its set number (really a string, something like: 10195-1)</li>

 <li>The theme it comes from (City, Technic, Star Wars, etc.)</li>

 <li>The name of the set</li>

 <li>How many parts and mini-figures it contains (if any)</li>

 <li>Its price in US dollars</li>

</ol>

Your goal is to read this from 1 of or more of these files, store the data, and then search it based on a few different criteria.

Main.cpp is the only file required for this assignment, but you are free to write any class/functions that you see fit to assist you solve this problem. Main.cpp has some structure to it already to help you get started. Take some time to think about the problem, and how you might go about this before diving in.

Searches

The different searches you will perform will be based on a menu that might look like this:

<ol>

 <li>Most expensive</li>

 <li>Largest piece count</li>

 <li>Search for set name containing…</li>

 <li>Search themes…</li>

 <li>Part count information</li>

 <li>Price information</li>

 <li>Minifigure information</li>

 <li>If you bought one of everything…</li>

</ol>

Most Expensive

From the sets that were loaded, which is the most expensive?

The most expensive set is: Name: Super Awesome Building Set

Number: 99923 Theme: City Price: $21.99 Minifigures: 4 Piece count: 286

COP3503 – Programming Fundamentals 2 1

<table>

 <tbody>

  <tr>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

Largest piece count

From the sets that were loaded, which has the most parts?

The set with the highest parts count:

Name: Really Big Set Number: 22231 Theme: Technic Price: $249.99 Minifigures: 0

Piece count: 5211

Search for set names containing…

Get a string as input from the user. Then search all sets and their names to see if they contain the search term.

There could be a lot of sets matching the search term, so show them in a more concise, list format with the set ID, name, and price. If no sets are found, report that as well.

Sets matching “Fire Station”:

49281 Fire Station $19.99 9381 Big Fire Station $49.99

-OR-

No sets found matching that search term

Search for set themes containing…

Ditto1, but for the theme of the set instead

Sets matching “City”:

1234 Police Station $29.9949281 Fire Station $19.99// And TONS more… LEGO City is huge!

Part count information

Show the average parts for all the loaded sets

Average part count for 601 sets: 492

Price information

Show the average, minimum and maximum prices.

Average price information for 601 sets: $500

Set with the minimum price: [Set data goes here]

Set with the maximum price: [Set data goes here]

Mini-figure information

Show the average number of minifigures, and the set information for the set with the most minifigures

Average number of minifigures: 8 Set with the most minifigures: Name: PG2 LectureNumber: COP3503

Theme: Education Price: $299.99 Minifigures: 310 Piece count: 938

If you bought one of everything…

How much would it costs? How many parts and mini-figures would you have?

If you bought one of everything…

It would cost: $9999.99You would have 200207 pieces in your collection You would have an army of 3000 mini-figures!

1 A similar thing; a duplicateCOP3503 – Programming Fundamentals 2 2

Reading Mixed Data From Files

When reading a text file, oftentimes the data initially gets read in as a string. If the final storage variable isn’t a string (such as a person’s age, or the price of something), you must convert it before storing/using it in its numeric form. In the &lt;string&gt; header file, there are a number of functions to help you convert. These function converts a STRING_TO_SOMETHING, and are named like stoi (string to integer), stof (string to float), etc.

Example:

The implementation of some of these functions may throw an exception of type “invalid_argument” if the conversion process fails, so you may want to encapsulate these operations in try/catch blocks, and use a default value if you catch an exception—if the number can’t be converted, (in this case) it’s because a value wasn’t there, so what would be a good value to use in the absence of anything else? Refer back to the section on Exceptions in your textbook if you need to.

Tips

<ol>

 <li>Choices you make at the start of a program can have a big impact on how the rest of the program gets developed. Think about how you want to store the information retrieved from the file, and how you could easily pass that data to various functions you might write.</li>

 <li>If you have a process for easily loading and accessing the data, the rest of the functionality should be a lot easier to write. Make sure the loading process is all taken care of before worrying about anything else.</li>

 <li>The code to load 1 file containing 1 piece of data (no matter how complex that data is) should not be much different than loading 100 files, each containing 100 elements. Start by thinking about just 1 element from the file first. Do the values you read match the values in the file? What about 2 entries, does everything add up? Then 3, 4, etc.</li>

 <li>When passing containers of data, make sure you pass them by REFERENCE, not by value. Creating copies of massive data sets is generally a bad, bad thing… unless you specifically need to duplicate the data. If not? Then pass by reference (in C++ that means either by pointer or the reference data type)</li>

 <li>There may be a fair amount of repetition in a program like this. Think about where you can create helper functions to reduce the number of times you write the exact same (or just slightly different) code.</li>

</ol>

<pre>ifstream someFile("Example.txt");string someString;someFile &gt;&gt; someString;</pre>

// We COULD just read directly into the int… but sometimes data doesn’t start out that way. // If you read a lot of data (say an entire line from a file), then you may break// that one string into many smaller strings, and convert as necessary.int convertToInt = stoi(someString);

COP3503 – Programming Fundamentals 2 3

Sample Outputs