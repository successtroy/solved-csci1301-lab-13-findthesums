Download Link: https://assignmentchef.com/product/solved-csci1301-lab-13-findthesums
<br>
<strong>Introduction</strong>

“Word Search” puzzles are popular games where players are given a 2D (two dimensional) array of letters and the goal is to find words that are spelled horizontally, vertically, and diagonally. In this lab, we will do something similar, but we will use integers and sums instead of letters and words. We’ll find horizontal and vertical sums in a 2D input array of integers that equal some input integer value (i.e. find all horizontal sums in a 2D array that equal 20). We won’t be finding diagonal sums in this lab, but feel free to challenge yourself with diagonal sums after you’ve submitted your lab. This lab will sharpen your problem solving skills and give you hands-on experience programming with 2D arrays. It is important to note that when you are working with 2D arrays, you’ll need to use nested loops to iterate through the values in their rows and columns.




For this lab, you’ll be working with 2D input arrays of integers that have <strong>m</strong> rows and <strong>n</strong> columns, where <strong>m</strong> &gt; 0 and <strong>n</strong> &gt; 0, and the input arrays contain only integers ranging from 1 to 9 (inclusive). The goals of this lab are to write a method that convert a 2D array to a neatly printable String and to write two additional methods that find the horizontal and vertical sums for a 2D input array and an input integer called <strong>sumToFind</strong>. For example, if <strong>sumToFind</strong> is 20, then your horizontal sum method would find all horizontally adjacent values in the input array that equal 20 and put them into a new output array, and values that aren’t in a horizontal sum equal to 20 would be set to zero in the output array. Similarly, vertical sums will be found the same way except their sums will be vertical. Study the examples in Figure 1. Please note that sums may overlap as shown in the highlighted example in Figure 1.




Figure 1

<table width="638">

 <tbody>

  <tr>

   <td colspan="3" width="213">Horizontal Sums sumToFind = 20</td>

   <td width="213">Input Array</td>

   <td width="213">Vertical Sums sumToFind = 20</td>

  </tr>

  <tr>

   <td colspan="3" width="213">0 0 0 0 0 0 0 0 0 00 1 6 1 8 4 0 0 0 0 0 2 4 8 6 1 1 0 0 0 3 6 8 3 0 0 0 0 0 00 7 7 6 3 5 6 4 2 06 4 5 5 0 0 0 0 0 00 0 5 4 3 7 1 0 0 06 8 6 0 8 6 2 4 6 20 0 0 0 0 8 2 2 8 0 0 7 7 6 0 2 9 9 0 0</td>

   <td width="213">7  3 8 5 6 7 4 1 9 58  1 6 1 8 4 6 9 9 69  2 4 8 6 1 1 3 6 23 6 8 3 1 9 2 7 9 6 5 7 7 6 3 5 6 4 2 16 4 5 5 7 6 8 1 9 78 4 5 4 3 7 1 2 1 86   8 6 7 8 6 2 4 6 27   8 6 8 3 8 2 2 8 5 8 7 7 6 6 2 9 9 5 8</td>

   <td width="213">0 0 0 0 6 0 0 1 0 58  1 0 0 8 0 0 9 0 69  2 0 0 6 0 1 3 0 23 6 8 0 1 9 2 7 9 60 7 7 0 3 5 6 4 2 16 4 5 0 7 6 8 1 9 08 4 0 0 3 0 1 2 1 0 6 8 0 0 8 0 2 4 6 00 8 0 0 3 0 0 2 8 0 0 0 0 0 6 0 0 0 5 0</td>

  </tr>

  <tr>

   <td width="68">Note:</td>

   <td width="62">8 6 2 4 6 2</td>

   <td colspan="3" width="508"> contains two overlapping sums that equal 20:  8 + 6 + 2 + 4 and 6 + 2 + 4 + 6 + 2</td>

  </tr>

  <tr>

   <td width="68"></td>

   <td width="62"></td>

   <td width="83"></td>

   <td width="213"></td>

   <td width="213"></td>

  </tr>

 </tbody>

</table>







In this lab, you will create a class called <strong>FindTheSums</strong> that has the following public static methods:  <strong>arrayToString</strong>, <strong>horizontalSums</strong>, and<strong> verticalSums</strong>.

<strong>Lab Objectives </strong>

By the end of the lab, you should have gained experience working with 2D arrays, nested loops, nested statements, static methods, writing pseudocode, and problem decomposition.

<strong>Prerequisites </strong>

The main concepts in this lab are from Chapter 7.  Concepts from Chapters 4, 5, and 6 are also in this lab.

<strong>What to Submit </strong>

The <strong>FindTheSums.java</strong> file should be submitted to eLC-new for grading.

<strong>Instructions </strong>

<ol>

 <li>Create a class called <strong>FindTheSums</strong>. Include the standard header comment stating your name, the date, program purpose, and containing the statement of academic honesty. When writing, you must also abide by the Java formatting and style conventions.</li>

 <li>Study the examples in Figure 1 to understand how horizontal and vertical sums are found. This lab requires more time thinking about how to solve the problems than previous labs. Experienced programmers spend more time thinking about how to solve a problem than implementing its solution. To start, use your fingers to slowly trace through the values in the input array in Figure 1 one-by-one from left to right and top to bottom to find the horizontal and vertical sums that equal 20. As you do this, ask yourself how many loops and variables are needed and what strategies would allow you to find all of the horizontal and vertical sums without missing any of them. These strategies are what you’ll be implementing in Java with two methods: a method to find the horizontal sums and another method to find the vertical sums. Write out the logic of your methods in pseudocode on a piece of paper (you may find it useful to look at the method definitions in the next step when writing your pseudocode). This will help you decompose the problems into simpler parts that will make writing the methods in the next step easier.</li>

 <li>In the class, you should implement the methods below, and what these methods return should match the examples at end of this lab.

  <ol>

   <li><strong>public static String arrayToString(int[][] a)</strong></li>

  </ol></li>

</ol>

This method will return a String that is a neat representation of the values in <strong>a</strong>. By neat, we mean that values in each column of <strong>a</strong> have a single space between them and the rows have a single newline character between them. There should not be a space before the first value in a column or after the last value in a column. Also, there should not be a newline before the first row or after the last row.

<ol>

 <li><strong>public static int[][] horizontalSums(int[][] a, int sumToFind) </strong></li>

</ol>

This method will create a new output array called <strong>b</strong> that has the same dimensions as <strong>a</strong>. For each <strong>a</strong>[i][j], where i and j are valid indices in <strong>a</strong>, if <strong>a</strong>[i][j] is part of a horizontal sum in <strong>a</strong> that equals <strong>sumToFind</strong>, then <strong>b</strong>[i][j] = <strong>a</strong>[i][j]; otherwise, <strong>b</strong>[i][j] = 0. The method should return <strong>b</strong>.

<ol>

 <li><strong>public static int[][] verticalSums(int[][] a, int sumToFind) </strong></li>

</ol>

This method will create a new output array called <strong>b</strong> that has the same dimensions as <strong>a</strong>. For each <strong>a</strong>[i][j], where i and j are valid indices in <strong>a</strong>, if <strong>a</strong>[i][j] is part of a vertical sum in <strong>a</strong> that equals <strong>sumToFind</strong>, then <strong>b</strong>[i][j] = <strong>a</strong>[i][j]; otherwise, <strong>b</strong>[i][j] = 0. The method should return <strong>b</strong>.

<ol start="4">

 <li>Download the <strong>java</strong> file, and place it in the same directory as your class. Your class must compile correctly with <strong>FindTheSumsTester.java</strong>. Run <strong>FindTheSumsTester</strong> to test your methods, and verify that your output matches the output at the end of this lab. If the output differs, then you have bugs that must be fixed. You should also create additional tests in <strong>FindTheSumsTester</strong> to further test your methods. Your methods must work for any valid inputs.</li>

</ol>




<strong><u>In your code, you are not allowed to use any java.util.Arrays methods or the java stream</u></strong><strong> <u>API (if you are familiar with either of these).  Using the java.util.Arrays class or Java</u> <u>stream in any way will result in a grade of zero on this assignment.</u></strong>




<strong>Additional Requirements</strong>

These are things that make the graders lives easier, and ultimately, you will see in the real world as well. Remember the teaching staff does not want to touch your code after they gave you requirements; they want to see the perfect results they asked for! Here is a checklist of things you can<strong> lose points</strong> for:




<ul>

 <li>(-10 points) If the source file(s)/class(es) are named incorrectly (case matters!)</li>

 <li>(-10 points) If your source file(s) have a package declaration at the top</li>

 <li>(-10 points) If any source file you submit is missing your Statement of Academic Honesty at the top of the source file. All submitted source code files must contain your Statement of Academic Honesty at the top of each file.</li>

 <li>(-10 points) If you have more than one instance of Scanner in your program.</li>

 <li>(-15 points) Inconsistent I/O (input/output) that does not match our instructions or examples exactly (unless otherwise stated in an assignment’s instructions). Your program’s I/O (order, wording, formatting, etc.) must match our examples and instructions.</li>

 <li>(-100 points) If the source file(s) are not submitted before the specified deadline or if they do not compile. Late submissions will not be accepted for this lab since it is the last lab of the semester, per the course syllabus.</li>

 <li>If your (-10 points) comments or (-10 points) variables are “lacking”</li>

 <li>Here, “lacking” means that you or a TA can find <strong>any</strong> lines of code or variables that take more than 10 seconds to understand, and there is no comment, or the variable name does not make sense (variable names like <strong>b</strong>, <strong>bb</strong>, <strong>bbb</strong>, etc. <strong>will</strong> <strong>almost never be acceptable) </strong></li>

 <li>(-10 points) Indentation is not consistent throughout your source code</li>

 <li>Refresh your memory of indentation patterns in chapter 2 in the course textbook</li>

 <li>Be careful of a combination of tabs and spaces in your files (use one or the other)!</li>

 <li>(-100 points) If you use a non-standard Java library or class (StringBuilder class, Arrays class, any class in java.util.stream) or other code specifically disallowed by the lab/project.</li>

</ul>

If any of the above do not make sense to you, then talk to a TA or your lab instructor.




<strong>eLC Submission and Grading </strong>

After you have completed and thoroughly tested your program, upload <strong>FindTheSums.java</strong> to <strong><em>eLC</em></strong> to receive credit.  Always double check that your submission was successful on <strong><em>eLC</em></strong>!  All instructions and requirements must be followed; otherwise, points maybe deducted.




The lab will be graded according to the following guidelines.




<ul>

 <li>A score between 0 and 100 will be assigned.</li>

 <li>If the source file(s) are not submitted before the specified deadline, or if they do not compile then a grade of 0 will be assigned.</li>

 <li>Your submitted program will be evaluated using a separate testing file that will call your methods with various valid inputs.</li>

 <li>Penalties maybe deducted as aforementioned.</li>

</ul>

<strong>Examples</strong>




<em><u>Output from FindTheSumsTester for a correctly implemented FindTheSums class:</u></em>




Testing arrayToString method: arrayToString(array1) test passed arrayToString(array2) test passed




Testing horizontalSums method:

array1:

3 2 1 1

2 5 6 2

1 2 9 8 horizontalSums(array1, 7):

3 2 1 1

2 5 0 0 0 0 0 0 array2:

<ul>

 <li>3 8 5 6 7 4 1 9 5</li>

 <li>1 6 1 8 4 6 9 9 6</li>

 <li>2 4 8 6 1 1 3 6 2</li>

</ul>

3 6 8 3 1 9 2 7 9 6

<a href="#_Toc7627">5 7 7 6 3 5 6 4 2                                                                                                                                                                              1 </a>

<a href="#_Toc7628">8 4 5 4 3 7 1 2 1 8 6 8 6 7 8 6 2 4 6                                                                                                                                          2 </a>

<a href="#_Toc7629">7 8 6 8 3 8 2 2 8                                                                                                                                                                              5 </a>




6 4 5 5 7 6 8 1 9 7

8 7 7 6 6 2 9 9 5 8 horizontalSums(array2, 20):

0 0 0 0 0 0 0 0 0 0

0 1 6 1 8 4 0 0 0 0

0 2 4 8 6 1 1 0 0 0

3 6 8 3 0 0 0 0 0 0

0 7 7 6 3 5 6 4 2 0

6 4 5 5 0 0 0 0 0 0

0 0 5 4 3 7 1 0 0 0

6 8 6 0 8 6 2 4 6 2

0 0 0 0 0 8 2 2 8 0 0 7 7 6 0 2 9 9 0 0 horizontalSums(array2, 25):

0 0 0 0 0 0 0 0 0 0

0 0 6 1 8 4 6 0 0 0

0 2 4 8 6 1 1 3 6 0

0 0 0 0 0 0 0 0 0 0

5 7 7 6 0 0 0 0 0 0

0 0 0 0 0 0 8 1 9 7

0 0 0 0 0 0 0 0 0 0

0 0 0 0 0 0 0 0 0 0

0 8 6 8 3 8 2 2 8 5

0 0 0 0 0 2 9 9 5 0




Testing verticalSums method: array1: 3 2 1 1

2 5 6 2

1 2 9 8

verticalSums(array1, 22):

0 0 0 0

0 0 0 0 0 0 0 0 array2:

<ul>

 <li>3 8 5 6 7 4 1 9 5</li>

 <li>1 6 1 8 4 6 9 9 6</li>

 <li>2 4 8 6 1 1 3 6 2</li>

</ul>

3 6 8 3 1 9 2 7 9 6

<h1><a name="_Toc7627"></a>5 7 7 6 3 5 6 4 2 1</h1>

6 4 5 5 7 6 8 1 9 7

<h1><a name="_Toc7628"></a>8 4 5 4 3 7 1 2 1 8</h1>

6 8 6 7 8 6 2 4 6 2

<h1><a name="_Toc7629"></a>7 8 6 8 3 8 2 2 8 5</h1>

8 7 7 6 6 2 9 9 5 8

verticalSums(array2, 14): 0 0 8 5 6 0 0 0 0 0

0 0 6 1 8 4 0 0 0 6

0 0 0 8 6 1 0 3 0 2

3 0 0 3 1 9 0 7 0 6

<ul>

 <li>0 0 6 3 5 6 4 0 1</li>

 <li>0 0 5 7 0 8 1 0 7</li>

</ul>

8 0 0 0 3 0 1 2 0 0

6 0 0 0 8 6 2 0 6 0

0 0 0 8 3 8 2 0 8 0 0 0 0 6 0 0 9 0 0 0 verticalSums(array2, 33): 0 0 8 0 0 0 0 1 9 0

0 0 6 0 0 0 0 9 9 0

0 0 4 8 0 0 0 3 6 0

0 0 8 3 0 9 0 7 9 0

0 0 7 6 0 5 0 4 2 0

0 0 0 5 0 6 0 1 9 0




0 0 0 4 0 7 0 2 1 0

0 0 0 7 0 6 0 4 6 0

0 0 0 8 0 0 0 2 0 0

0 0 0 0 0 0 0 0 0 0


