Download Link: https://assignmentchef.com/product/solved-ccu-oop-homework-3-date
<br>
<h1>HW #3 (Date)</h1>

<ul>

 <li>For this homework, you will write a class called <strong>Date</strong>, using C++, or Java if you prefer, for creating and using objects that will store valid dates of the year.</li>

 <li>An object of type Date should represent a calendar date in terms of month, day, and year, as on a 12-month A.D. calendar. The valid months are January through December, a valid day must correspond to a valid day for the given month, and the year must be a positive number.</li>

 <li>Your object should also store a format setting, to be used for display of dates to the screen. There will be more than one possible format. The class features (public interface) should work exactly as specified, regardless of what program might be using Date objects.</li>

 <li>For purposes of easy input (from keyboard or into functions), date values will be specified with integers. Month values will be 1 for January, 2 for February, etc… on to 12 for December. A valid day value will be an integer between 1 and the number of days in the month.</li>

</ul>

Valid year values are positive numbers.

<h1>HW #3</h1>

<ul>

 <li>Your Date class must provide the following services (i.e., member functions) in its public section. These functions will make up the interface of the Date class. Make sure you use function prototypes as specified here. (You may write any other private functions you feel necessary, but the public interface must include all the functionality described here.)</li>

 <li><strong>the constructor(s): </strong>The Date class should have a constructor that allows the user to specify the values for the month, day, and year, using integer values, when the object is declared. If any of the values would result in an invalid date, the constructor should throw out the erroneous information and initialize the object to represent 1/1/2000 (January 1, 2000) instead. Also, you should allow a Date object to be declared without specified values, in which case it should initialize to 1/1/2000 also.</li>

</ul>

<h1>HW #3 (5)</h1>

<ul>

 <li><strong>Examples</strong>: These declarations should be legal, and the comment gives the initialized date.</li>

</ul>

Date d1; // initializes to Jan 1, 2000

Date d2 (3, 4, 1992); // initializes to March 4, 1992

Date d3 (13, 30, 1990); // invalid month, initializes to Jan 1, 2000

<ul>

 <li><strong>void Input()</strong>: This function should prompt the user to enter a date, and then allow the user to input a date from the keyboard. User input is expected to be in the format <em>month/day/year</em>, where month, day, and year are integer values. Whenever the user attempts to enter an invalid date, the Input function should display an appropriate error message (like “Invalid date. Try again: “) and make the user re-enter the whole date. A few example of some good and bad inputs:</li>

</ul>

Legal: 1/4/2000, 2/28/1996, 12/31/1845

Illegal: 13/12/1985, 11/31/2002, 8/30/-2000




<h2>(7)</h2>

<ul>

 <li>You may assume that the user entry will always be of the form: <strong>M/D/Y </strong>where M, D, and Y are integers, and the slash characters are always present.</li>

 <li><strong>void Show()</strong>: This function should simply output the date to the screen. There will be more than one possible format for this output, however, and your class will need to store a format setting. The Show function should use the format setting to determine the output. (There will be a member function that allows the setting to be changed.) When a Date object is created, the format setting should start out at the “Default” setting.</li>

 <li>The possible formats are shown in the following table:</li>

</ul>

<h1>HW #3 (9)</h1>

<ul>

 <li><strong>bool Set(int m, int d, int y)</strong>: This function should set the date to the specified values (the first parameter represents the month, the second represents the day, and the third represents the year). If the resulting date is an invalid date, the operation should abort (i.e., the existing stored date should not be changed). This function should return <em>true </em>for success and <em>false </em>for failure (i.e., invalid date sent in).</li>

</ul>




<ul>

 <li><strong>int GetMonth()</strong></li>

 <li><strong>int GetDay()</strong></li>

 <li><strong>int GetYear()</strong>: These are “accessor” functions, and they should return the month, day, and year, respectively, to the caller.</li>

 <li><strong>bool SetFormat(char f)</strong>: This function allows the caller to change the format setting. The setting should be adjusted inside the object based on the character code passed in. This means that future uses of the Show function will display in this given format until the format is changed.</li>

 <li>The valid setting codes that can be passed in are:</li>

</ul>

‘D’ = Default format

‘T’ = Two-Digit format

‘L’ = Long format

<ul>

 <li>If an invalid setting code is passed in, do not alter the current format setting. This function should return <em>true </em>for successful format change, and <em>false </em>for failure (invalid setting given).</li>

 <li><strong>void Increment(int numDays = 1)</strong>: This function should move the date forward by the number of calendar days given in the argument. Default value on the parameter is 1 day. Examples:</li>

</ul>

Date d1(10, 31, 1998); // Oct 31, 1998 Date d2(6, 29, 1950); // June 29, 1950 d1.Increment(); // d1 is now Nov 1, 1998 d2.Increment(5); // d2 is now July 4, 1950

<ul>

 <li><strong>int Compare(const Date&amp; d)</strong>: This function should compare two Date objects (the calling object and the parameter), and should return: -1 if the calling object comes first chronologically, 0 if the objects are the same date, and 1 if the parameter object comes first chronologically. The function should not change either object. Examples:</li>

</ul>

Date d1(12, 25, 2003); // Dec 25, 2003 Date d2(5, 18, 2002); // May 18, 2002 d1.Compare(d2); // return 1 (since d2 comes first) d2.Compare(d1); // return -1 (calling object is d2, comes first)

<ul>

 <li>The <strong>const </strong>qualifier should be used on any member functions where it is appropriate.</li>

 <li>You are not required to handled leap years in this class. You may make the general assumption that a year always has 365 days.</li>

 <li>Following is a sample test program starter for Date class.</li>

</ul>




<strong>#include &lt;iostream&gt; #include “date.h“</strong>

<strong>using namespace std; int main()</strong>

<strong>{</strong>

<strong>Date d1; // should default to 1/1/2000</strong>

<strong>Date d2(4,10,1992); // should init to 4/10/1992</strong>

<strong>// display dates to the screen cout &lt;&lt; “
Date d1 is: “; d1.Show(); cout &lt;&lt; “
Date d2 is: “; d2.Show();</strong>

<strong>d1.Input(); // Allow user to enter a date for d1 cout &lt;&lt; “
Date d1 is: “; d1.Show();</strong>

<strong>d1.SetFormat(‘L’); // change format of d1 to “Long” format cout &lt;&lt; “
Date d1 is: “; d1.Show(); // print d1 — should show now in long format</strong>

<strong>// and so on. Add your own tests to fully test the class‘ // functionality.</strong>

<strong>} </strong>