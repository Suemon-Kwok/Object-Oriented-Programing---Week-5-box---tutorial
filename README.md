/*
Object oriented programming Lab 5 question 1
Complete the Box class with instance variables for height, width, and depth 
1.	Declaring three private instance variables int height, int width, and int depth
2.	Writing the constructor method with input parameters for height, width and depth
3.	Writing get methods for all instance variables
4.	Write the String toString() method to return a text description of the Box in standard output formatting
5.	Write the method boolean fits(Box box)  with input for a Box object and returns true if the input Box fits in this Box. E.g. input Box has height, width and depth less than this
6.	Write the boolean fits(Box box1, Box box2) method with two Box input parameters and returns true if box1 fits in this box, and box2 fits in box1. e.g.:   this > box1 > box2.
Complete the main method by
1.	Using new to create the new Box(11,21,31) and using toString to output to console
2.	Using new to create the new Box(21,31,41) and using toString to output to console
3.	Using new to create the new Box(31,41,51) and using toString to output to console
4.	Using standard output formatting to print the results of box1.fits(box2, box3) 

For example:
Test	Result
//Checking get methods
Box box = new Box(10, 20, 30);
System.out.println(box.getHeight());
System.out.println(box.getWidth());
System.out.println(box.getDepth());	10
20
30

//Checking toString()
Box box = new Box(12, 23, 34);
System.out.println(box);	height = 12
width = 23
depth = 34

//Checking first fits method
Box box1 = new Box(10, 20, 30);
Box box2 = new Box(20, 30, 40);
System.out.println(box1.fits(box2));
System.out.println(box2.fits(box1));	false
true

//Checking second fits method
Box box1 = new Box(10, 20, 30);
Box box2 = new Box(20, 30, 40);
Box box3 = new Box(30, 40, 50);
System.out.println(box1.fits(box2, box3));
System.out.println(box3.fits(box2, box1));	false
true

Box.main(new String[]{});	height = 11
width = 21
depth = 31
height = 21
width = 31
depth = 41
height = 31
width = 41
depth = 51
fits = false


//This import is necessary for your program to run in code validator
import java.lang.reflect.Field;

public class Box 
{
    //declare instance vars here
	
	
	//declare constructor

//declare get methods 	
	
	//declare toString	
	
	
	//declare fits(Box)
	
	
	//declare fits(Box,Box)
	
	
	public static void main(String[] args) 
	{
	    //create three instances of box 
	    //use toString to print to the console 
	    //use the fits method here
        
    }
}
*/
//This import is necessary for your program to run in code validator
import java.lang.reflect.Field;

public class Box
{
    //declare instance vars here
    private int height;
    private int width;
    private int depth;
      
    //declare constructor
    public Box(int height, int width, int depth) {
        this.height = height;
        this.width = width;
        this.depth = depth;
    }
 
    //declare get methods
    public int getHeight() {
        return height;
    }
    
    public int getWidth() {
        return width;
    }
    
    public int getDepth() {
        return depth;
    }
      
    //declare toString
    public String toString() {
        return "height = " + height + "\nwidth = " + width + "\ndepth = " + depth;
    }
      
    //declare fits(Box)
    public boolean fits(Box box) {
        return this.height > box.height && 
               this.width > box.width && 
               this.depth > box.depth;
    }
      
    //declare fits(Box,Box)
    public boolean fits(Box box1, Box box2) {
        return this.fits(box1) && box1.fits(box2);
    }
      
    public static void main(String[] args) {
        //create three instances of box
        Box box1 = new Box(11, 21, 31);
        Box box2 = new Box(21, 31, 41);
        Box box3 = new Box(31, 41, 51);
        
        //use toString to print to the console
        System.out.println(box1);
        System.out.println(box2);
        System.out.println(box3);
        
        //use the fits method here
        System.out.println("fits = " + box1.fits(box2, box3));
    }
}
