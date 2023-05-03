Download Link: https://assignmentchef.com/product/solved-cpsc355-computing-machinery-i-assignment-4
<br>
Structures and Subroutines

Create an ARMv8 assembly language program that implements the following program:

#define FALSE  0

#define TRUE   1

struct point {   int x, y;

};

struct dimension {   int width, height;

};  struct box {   struct point origin;   struct dimension size;   int area;

};




struct box newBox()

{

struct box b;




b.origin.x = 0;

b.origin.y = 0;

b.size.width = 1;

b.size.height = 1;

b.area = b.size.width * b.size.height;    return b;

}




void move(struct box *b, int deltaX, int deltaY)

{

b-&gt;origin.x += deltaX;   b-&gt;origin.y += deltaY;

}




void expand(struct box *b, int factor)

{

b-&gt;size.width *= factor;   b-&gt;size.height *= factor;

b-&gt;area = b-&gt;size.width * b-&gt;size.height;

}




void printBox(char *name, struct box *b)

{

printf(“Box %s origin = (%d, %d)  width = %d  height = %d  area = %d
”,

name, b-&gt;origin.x, b-&gt;origin.y, b-&gt;size.width, b-&gt;size.height,     b-&gt;area);

}




int equal(struct box *b1, struct box *b2)

{

int result = FALSE;




if (b1-&gt;origin.x == b2-&gt;origin.x) {     if (b1-&gt;origin.y == b2-&gt;origin.y) {       if (b1-&gt;size.width == b2-&gt;size.width) {         if (b1-&gt;size.height == b2-&gt;size.height) {           result = TRUE;

}

}

}

}

return result;

}

int main() {

struct box first, second;




first = newBox();   second = newBox();




printf(“Initial box values:
”);   printBox(“first”, &amp;first);   printBox(“second”, &amp;second);




if (equal(&amp;first, &amp;second)) {     move(&amp;first, -5, 7);     expand(&amp;second, 3);

}

printf(“
Changed box values:
”);   printBox(“first”, &amp;first);   printBox(“second”, &amp;second);

}

Implement all the subroutines above as unoptimized closed subroutines, using stack variables to store all local variables. Note that the function newBox () must have a local variable (called b) which is returned by value to main(), where it is assigned to the local variables first and second. In other words, create code similar to what the C compiler produces, even if it seems inefficient. Name the program

assign4.asm.

Also run the program in gdb, displaying the values of first and second after they have been set by function calls. You should show that the functions are working as expected. Capture the gdb session using the script UNIX command, and name the output file script.txt.

Other Requirements

Make sure your code is readable and fully documented, including identifying information at the top of each file. You must comment each line of assembly code. Your code should also be well designed:  make sure it is well organized, clear, and concise.

New Skills Needed for this Assignment:




<ul>

 <li>Implementation of structs and nested structs</li>

 <li>Implementation of subroutines in assembly</li>

 <li>Returning structs by value from functions</li>

 <li>Use of pointers as arguments to subroutines</li>

</ul>




Submit the following:




<ol>

 <li>Your assembly source code file for the program, and your script output file. Use the Assignment 4 Dropbox Folder in D2L to submit electronically. The TA will assemble and run your program to test it. Be sure to name your program and script file as described above.</li>

</ol>


