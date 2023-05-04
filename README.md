Download Link: https://assignmentchef.com/product/solved-cse-231-computer-project4
<br>
<h2>Assignment Overview</h2>

<strong> </strong>

This assignment focuses on the implementation of Python programs to read files and process data by using lists and functions.

<strong> </strong>

It is worth 85 points (8.5% of course grade) and must be completed no later than <strong>11:59 PM on Tuesday, June 9</strong>.




<h2>Assignment Deliverable</h2>




The deliverable for this assignment is the following file:




proj04.py – the source code for your Python program




Be sure to use the specified file name and to submit it for grading via the <strong>Mirmir</strong> <strong>system</strong> before the project deadline.




<h2>Assignment Background</h2>

<strong> </strong>

One commonly hears reference to “the one percent” referring to the people whose income is in the top 1% of incomes.  What is the data behind that number and where do others fall?  Using the National Average Wage Index (AWI), an index used by the Social Security Administration to gauge a individual’s earnings for the purpose of calculating their retirement benefit, we can answer such questions.




In this project, you will process AWI data. Example data for 2014 and 2015 is provided in the files year2014.txt and year2015.txt (2015 is the most recent year of complete data—the 2016

data isn’t available until October). The data is a table with the first row as the title and the second row defining the data fields; remaining rows are data.  Note that the 2014 data is nicely formatted in columns, but the 2015 data is not. The URL for the data is: <a href="https://www.ssa.gov/cgi-bin/netcomp.cgi?year=2015">https://www.ssa.gov/cgi</a><a href="https://www.ssa.gov/cgi-bin/netcomp.cgi?year=2015">bin/netcomp.cgi?year=2015</a>

<strong> </strong>

Here is the second line of data from the file followed by descriptions of the data.  Notice that some data are ints and some are floats:




5,000.00 – 9,999.99  13,848,841  36,423,281  23.02549  102,586,913,092.61  7,407.62




Column 0 is bottom of this income range.

Column 1 is the hyphen separating the bottom of the range from the top.

Column 2 is the top of this income range.

Column 3 is the number of individuals in the income range.

Column 4 is the cumulative number of individuals in this income range and all lower ranges.

Column 5 is the Column 4 value represented as a cumulative percentage of all individuals.

Column 6 is the combined income of all the individuals in this range of income.

Column 7 is the average income of individuals in this range of income.




<h2>Assignment Specifications</h2>

<strong> </strong>

<ol>

 <li>The program must provide following functions to extract some statistics. Note that the data_list parameter specified in these functions may be the same for all functions or different for different functions—that is your choice.  A skeleton file is provided on Mirmir.

  <ol>

   <li>open_file()prompts the user to enter a year number for the data file. The program will check whether the year is between 1990 and 2015 (both inclusive). If year number is valid, the program will try to open data file with file name ‘yearXXXX.txt’, where XXXX is the year. Appropriate error message should be shown if the data file cannot be opened or if the year number is invalid. This function will loop until it receives proper input and successfully opens the file.  It returns a file pointer and year.

    <ol>

     <li><strong>Hint</strong>: use string concatenation to construct the file name</li>

    </ol></li>

   <li>read_file(fp)has one parameter, a file pointer read. This function returns a list of your choosing containing data you need for other parts of this project.</li>

   <li>find_average(data_list) takes a list of data (of some organization of your choosing) and returns the average salary. The function does not print anything. <strong><em>Hints</em></strong>:

    <ol>

     <li>This is NOT (!) the average of the last column of data. It is not mathematically valid to find an average by finding the average of averages—for example, in this case there are many more in the lowest category than in the highest category.</li>

     <li>How many wage earners are considered in finding the average (denominator)? There are a couple of ways to determine this.  I think the easiest uses the “cumulative number” column (Column 4), but using Column 3 is not hard and may make more sense to some students.</li>

    </ol></li>

  </ol></li>

</ol>

<ul>

 <li>How does one find the total dollar value of income (numerator)? Notice that “Column 6 is the combined income of all the individuals in this range of income.”</li>

</ul>

<ol start="569">

 <li>For testing your function notice that for the 2014 data the average should be $44,569.20. As a check, note that that value is listed on the web page referenced above.</li>

</ol>

<ol>

 <li>find_median(data_list) takes a list of data (of some organization of your choosing) and returns the median income. The function does not print anything. Unfortunately, this file of data is not sufficient to find the true median so we need to approximate it.

  <ol>

   <li>Here is the rule we will use: <em>find the data line whose cumulative percentage (Column 5) is closest to 50% and return its average income (Column 7). </em>If both data lines are equally close, return either one.</li>

   <li><strong>Hint</strong>: Python’s abs() function (absolute value) is potentially useful here.</li>

  </ol></li>

</ol>

<ul>

 <li><strong>Hint: </strong>your get_range() function should be useful here.</li>

</ul>

<ol>

 <li>For testing your function, using our rule the median income for the 2014 data is</li>

</ol>

$27,457.00

<ol>

 <li>get_range(data_list, percent) takes a list of data (of some organization of your choosing) and a percent (float) and returns the salary range as a tuple (Columns 0 and 2) for the data line whose cumulative percentage (Column 5) is greater than or equal to the percent parameter, the cumulative percentage value (Column 5) and the average income (Column 7). Stated another way: ((col_0,col_2),col_5,col_7) The function does not print anything.

  <ol>

   <li>For testing using the 2014 data and a percent value of 90 your function will return</li>

  </ol></li>

</ol>

((90000.0, 94999.99), 90.80624, 92420.5)

<ol>

 <li>get_percent(data_list, income) takes a list of data (of some organization of your choosing) and an income (float) and returns the cumulative percentage (Column 5) for the data line that the specified income is in the income range (Columns 0 and 2), and income range (Columns 0 and 2) . Stated another way: ((col_0,col_2),col_5) The function does not print anything.

  <ol>

   <li>For testing using the 2014 data and an income value of 150,000 your function will return</li>

  </ol></li>

</ol>

((150000.0, 154999.99), 96.87301)

<ol>

 <li>do_plot(x_vals,y_vals,year) provided by us takes two equal-length lists of numbers and plots them. Note that if you plot the whole file of data, the income ranges are so skewed that the result is a nearly vertical plot at the leftmost edge so close to the edge that you cannot see it in the plot—it looks like nothing was plotted. Plotting the lowest 40 income ranges results in a more easily readable plot.</li>

</ol>

<ol start="2">

 <li>main()

  <ol>

   <li>Open the data file</li>

   <li>Read the data file (using the file pointer from the opened file).</li>

   <li>Print the year, the average income, and the median income (and a header). Here is the output format that I used: “{:&lt;6d}${:&lt;14,.2f}${:&lt;14,.2f}”</li>

   <li>Prompt whether to plot the data and if “yes”, plot the data: cumulative percentage (Column 5) vs. income (Column 0) – only the lowest 40 income ranges.</li>

   <li>Loop, prompting for either “r” for range , “p” for percent, or nothing

    <ol>

     <li>r: prompt for a percent (float) and output the income that is below that percent. Print an error message, if an invalid number is entered (a percent must be between 0 and 100).</li>

    </ol></li>

  </ol></li>

</ol>

Here is the output format that I used:

“{:4.2f}% of incomes are below ${:&lt;13,.2f}.”

<ol>

 <li>p: prompt for an income (float) and output the percent that earn more. Print an error message, if an invalid income is entered (income must be positive). Here is the output format that I used:</li>

</ol>

“An income of ${:&lt;13,.2f} is in the top {:4.2f}% of incomes.” iii. if only a carriage-return is entered, halt the program.

<ol start="3">

 <li>Call main() using</li>

</ol>

if __name__ == “__main__”:              main()




<h2>Assignment Notes</h2>




<ol>

 <li>Items 1-9 of the Coding Standard will be enforced for this project.</li>

</ol>




<ol start="2">

 <li>Files for txt and year2015.txt are provided so that you can test your program. We will also test you on the year 2000 data, but are not sharing that file with you.</li>

 <li>Note that most data has commas. I wrote functions that converted a string with commas into a number without commas.  I wrote separate functions for int and float, but you may find that one combined function suits your needs.  I used a try-except statement in case the string wasn’t really a number.</li>

 <li>For output you need to insert commas. There is a format specification, e.g. if you might have formatted a floating-point value without commas as {:&lt;12.2f} you can simply insert a comma before the dot as in {:&lt;12,.2f}.</li>

 <li>There are multiple ways to handle the “and over” wording in the last line of the input files.</li>

</ol>

One way you might not have thought of uses the special value float(“inf”) which represents infinity in the sense of a value bigger than all others.

<strong> </strong>

<h2>Suggested Procedure</h2>

<strong> </strong>

<ul>

 <li><em>Solve the problem using pencil and paper first.</em> You cannot write a program until you have figured out how to solve the problem.  This first step may be done collaboratively with another student.  However, once the discussion turns to Python specifics and the subsequent writing of Python statements, you must work on your own.</li>

</ul>




<ul>

 <li>Construct the program one function at a time—testing before moving on.</li>

</ul>




<ul>

 <li>Use the <strong>Mirmir</strong> <strong>system</strong> to turn in the first version of your solution. Cycle through the steps to incrementally develop your program:</li>

</ul>




<ul>

 <li>Edit your program to add new capabilities. o Run the program and fix any errors.</li>

 <li>Use the <strong>Mirmir</strong> <strong>system</strong> to submit the current version of your solution.</li>

</ul>




<ul>

 <li>Be sure to log out when you leave the room, if you’re working in a public lab.</li>

</ul>




<h2>Tests</h2>

<strong> </strong>

<strong>There are unit tests for functions: </strong>find_average, find_median, get_range, and get_percent.  The tests all call your read_file function to get your data structure to pass to those functions.  The file read for these unit tests is the 2014 data.

<strong> </strong>

<h2>Test 1</h2>




Enter a year where 1990 &lt;= year &lt;= 2015: 2014




Year  Mean           Median

2014  $44,569.20     $27,457.00

Do you want to plot values (yes/no)? no

Enter a choice to get (r)ange, (p)ercent, or nothing to stop:

<h2>Test 2</h2>




Enter a year where 1990 &lt;= year &lt;= 2015: 2014




Year  Mean           Median

2014  $44,569.20     $27,457.00

Do you want to plot values (yes/no)? no

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: r

Enter a percent: 90




90.00% of incomes are below $90,000.00    .

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: p

Enter an income: 100000




An income of $100,000.00    is in the top 92.57% of incomes. Enter a choice to get (r)ange, (p)ercent, or nothing to stop:

<h2>Test 3</h2>




Enter a year where 1990 &lt;= year &lt;= 2015: xxxx

Error in year. Please try again.

Enter a year where 1990 &lt;= year &lt;= 2015: 1900

Error in year. Please try again.

Enter a year where 1990 &lt;= year &lt;= 2015: 1999

Error in file name: year1999.txt  Please try again.

Enter a year where 1990 &lt;= year &lt;= 2015: 2015




Year  Mean           Median

2015  $46,119.78     $27,459.59

Do you want to plot values (yes/no)? no

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: x

Error in selection.

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: r

Enter a percent: 104

Error in percent. Please try again

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: r Enter a percent: -2

Error in percent. Please try again

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: r

Enter a percent: 90




90.00% of incomes are below $90,000.00    .

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: p

Enter an income: -20

Error: income must be positive

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: p

Enter an income: 100000




An income of $100,000.00    is in the top 92.03% of incomes. Enter a choice to get (r)ange, (p)ercent, or nothing to stop:

<h2>Test 4</h2>




Enter a year where 1990 &lt;= year &lt;= 2015: 2000




Year  Mean           Median

2000  $30,846.09     $17,471.75

Do you want to plot values (yes/no)? no

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: r

Enter a percent: 40




40.00% of incomes are below $15,000.00    .

Enter a choice to get (r)ange, (p)ercent, or nothing to stop: p

Enter an income: 20000




An income of $20,000.00     is in the top 56.96% of incomes. Enter a choice to get (r)ange, (p)ercent, or nothing to stop:







<strong>Test 5  </strong>

<h2>(not on Mirmir because this tests the plot – TAs will run this test.)</h2>

<strong> </strong>

Enter a year where 1990 &lt;= year &lt;= 2015: 2015




Year  Mean           Median

2015  $46,119.78     $27,459.59

Do you want to plot values (yes/no)? yes










Enter a choice to get (r)ange, (p)ercent, or nothing to stop:

<h2>Grading Rubric</h2>




Computer Project #4 Scoring Summary







General Requirements




__0__   ( 5 pts) Coding standard







Program Implementation




__0__   ( 5 pts) Function (no Mirmir test): open_file




__0__   ( 5 pts) Function (no Mirmir test): read_file




__0__   ( 5 pts) Function Test 3: find_average




__0__   ( 5 pts) Function Test 4: find_median    __0__   ( 5 pts) Function Test 5: get_range




__0__   ( 5 pts) Function Test 6: get_percent




__0__   (10 pts) Test 1




__0__   (10 pts) Test 2




__0__   (10 pts) Test 3




__0__   (10 pts) Test 4




__0__   (10 pts) Plotting (Test 5 – no Mirmir test)

<strong> </strong>


