Download Link: https://assignmentchef.com/product/solved-csci3110-lab4-inheritance
<br>
<strong>Objective</strong>: To be familiar with ordered STL list, inheritance and abstract base classes.

<strong>Description</strong>: In this assignment, you will build an interactive program for a video store that sells DVD and books. When the program starts, it loads inventory from an external file inventory.txt. Each line in the inventory.txt file contains the information of one DVD/Book in one of the following formats:

<ul>

 <li><em>|Movie|barcode|movie name|director(s) of the movie|movie price|number of copies currently in stock|number of DVD’s to be ordered|</em></li>

 <li><em>|Book|barcode|title of the book|author(s) of the book|publish date|book price|number of copies currently in stock|number of books to be ordered|</em></li>

</ul>

Each item in the line is separated by “|”.

The inventory should be maintained in alphabetical order by barcode instead of title. The program should provide the following commands:

<strong>‘M’</strong>–Inquire about a specific movie by title and display inventory information for the specified movie. The user should be asked to input a movie title and your program should print out all information related to that movie.

<strong>‘B’</strong>–Inquire about a specific book by author and display inventory information for the specified book. The user should be asked to input (partial) name of an author and your program should print out all information of the book written by that author. You may need to use code similar to the following to allow the user to input only portions of the author’s name.

string str1( “Alpha Beta Gamma Delta” ); string::size_type loc = str1.find( “Omega”, 0 );

if( loc != string::npos )

<a href="https://www.opengroup.org/onlinepubs/009695399/functions/cout.html">cout</a> &lt;&lt; “Found Omega at ” &lt;&lt; loc &lt;&lt; endl;

else     <a href="https://www.opengroup.org/onlinepubs/009695399/functions/cout.html">cout</a> &lt;&lt; “Didn’t find Omega” &lt;&lt; endl;

<strong>‘R’</strong>–Return a movie/book to the inventory. The user should be asked to input the bar code. If the movie/book is in the inventory, the number of copies of the item should be increased by 1 if the number of copies to be ordered is 0, or decrease the number of copies to be ordered by 1 if it is greater than 0.

<strong>‘L’</strong>— List the entire inventory in alphabetical order by barcode <strong>‘C’</strong>–Check out a movie/book. The user should be asked to input a barcode. If the item is in the inventory and the number of copies of the item is &gt;0, your program should decrease the number of copies on hand by one. If the item is in the inventory but there are no copies available, the number of copies to be ordered should be increased by 1. If the item is not in the inventory, an error message should be printed.

<strong>‘Q’</strong>— Quit the program. No need to save the inventory information.

<strong>Design: </strong>This assignment contains several classes: StoreItem, <em>Movie</em>, and Book.

<ul>

 <li><em>StoreItem</em>: This is the base class of the classes Movie and Book. A store item can have barcode, price for the item, number of copies of the item in the inventory and number of copies to be ordered. The declaration of StoreItem class is provided by the instructor.</li>

 <li><em>Movie</em>: Represents DVD information. It is a derived class of StoreItem.</li>

 <li><em>Book</em>: Represents Book information. It is a derived class of StoreItem.</li>

</ul>

The file ola4.cpp should provide the program’s user interface: read user’s input and execute appropriate commands. The inventory must be represented as a list of StoreItem pointers (i.e. <strong>list&lt;StoreItem *&gt;</strong>) in order to explore the benefits of polymorphism.

<strong>Requirements &amp; hints:</strong>

<ul>

 <li>You must have a separate header and implementation files for the above classes.</li>

 <li>A sample inventory.txt file is available.</li>

 <li>The movies/books should be stored in the list in alphabetical order by barcode.</li>

 <li>Be sure to check for errors: Returning an item that is not supported by the store, checking out an item that is not supported by the store, inquiring about an item that is not supported by the store, etc.</li>

 <li>In this program, you may need to use the function <em>typeid</em> to obtain the runtime type of variables/pointers. The following is a sample code of using <em>typeid</em>.</li>

</ul>

<strong>#include &lt;typeinfo&gt; </strong>void print(StoreItem *item)

{

Movie     defaultMovie; // a movie object Book     defaultBook; // a book object

if ( typeid(*item) == typeid(defaultMovie) )

{

cout &lt;&lt; “item is a movie pointer” &lt;&lt; endl; cout &lt;&lt; “The director of the movie is “

&lt;&lt; ((Movie *)item)-&gt;getDirector() &lt;&lt; endl;

}

else if ( typeid(*item) == typeid(defaultBook) )

{ cout &lt;&lt; “item is a book pointer” &lt;&lt; endl; cout &lt;&lt; “The author of the book is “

&lt;&lt; ((Book *)item)-&gt;getAuthor() &lt;&lt; endl;

}

}

<ul>

 <li>In this program, you may need to use the stringstream to implement the function <em>createFromString </em>in classes Book and</li>

</ul>

Movie. To user string stream, you need to include the header file <em>sstream</em>. The following statement creates a string stream from an string object. The usage of stringstream is similar to a cin.

#include &lt;sstream&gt;

stringstream ss(aStringVariable); ss &gt;&gt; aVariable;

getline(ss, stringVariable2HoldValue, ‘|’);

<strong>How to download assignment files:</strong>

Go to the URL: <a href="http://www.cs.mtsu.edu/~zdong/3110/public/OLA/OLA2.zip">http://www.cs.mtsu.edu/~zdong/3110/public/OLA/</a> and download the file OLA4.zip, which contains the following files:

Ola4Description.doc: this file

inventory.txt: a sample inventory file

OLA4Rubric.doc: a rubric used to grade this assignment

OLA4.exe: an executable solution provided by the instructor.

StoreItem.h: declaration of the class StoreItem. Movie.h: declaration of the class Movie


