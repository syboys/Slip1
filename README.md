# Slip1
this is slip no 1 questions

Q1) Write a Java Program to implement I/O Decorator for converting uppercase letters to
lower case letters.
Q2) Write a Python program to prepare Scatter Plot for Iris Dataset
Q3) Create an HTML form that contain the Student Registration details and write a
JavaScript to validate Student first and last name as it should not contain other than
alphabets and age should be between 18 to 50.





1)Write a Java Program to implement I/O Decorator for converting uppercase letters to lower case letters.
:
import java.io.*;
 import java.util.*; 
class LowerCaseInputStream extends FilterInputStream
 { 
public LowerCaseInputStream(InputStream in) { 
super(in); 
}
 public int read() throws IOException { 
int c = super.read();
 return (c == -1 ? c : Character.toLowerCase((char)c));
 } 
public int read(byte[] b, int offset, int len) throws IOException {
 int result = super.read(b, offset, len);
 for (int i = offset; i < offset+result; i++) 
b[i] = (byte)Character.toLowerCase((char)b[i]); 
}
 return result; 
}
 }
 public class Main { 
public static void main(String[] args) throws IOException {
 int c;
 try { 
InputStream in =
 new LowerCaseInputStream( 
new BufferedInputStream(
 new FileInputStream("test.txt")));
 while((c = in.read()) >= 0) { 
System.out.print((char)c); 
} 
in.close();
 } catch (IOException e) { 
e.printStackTrace(); 
}
 } 
}


2)Write a Python program to prepare Scatter Plot for Iris Dataset
:
import seaborn as sns
import matplotlib.pyplot as plt
from pandas.plotting import parallel_coordinates
import pandas as pd
# Parallel Coordinates
# Load the data set
iris = sns.load_dataset("iris")
parallel_coordinates(iris, 'species', color=('#556270', '#4ECDC4', '#C7F464'))
plt.show()
from pandas.plotting import andrews_curves
# Andrew Curves
a_c = andrews_curves(iris, 'species')
a_c.plot()
plt.show()
from seaborn import pairplot
# Pair Plot
pairplot(iris, hue='species')
plt.show()


from plotly.express import scatter_3d
# Plotting in 3D by plotly.express that would show the plot with capability of zooming,
# changing the orientation, and rotating
scatter_3d(iris, x='sepal_length', y='sepal_width', z='petal_length', size="petal_width",
                   color="species", color_discrete_map={"Joly": "blue", "Bergeron": "violet", "Coderre": "pink"})\
            .show()

3) Create an HTML form that contain the Student Registration details and write a JavaScript to validate Student first and last name as it should not contain other than alphabets and age should be between 18 to 50.
:
<html lang="en">
<head>
 <title>Employee Registration Form</title>
 <script>
 function Submit()
 {
 var fname = document.getElementById("s1").value;
 var patt = /[A-Za-z]+$/;
 if(!fname.match(patt))
 {
 alert("First name should be alaphabatic");
 return false;
 }
 else
 {
 alert("First name Entered");
 }

 var lname = document.getElementById("s2").value;
 var patt2 = /[A-Za-z]+$/;
 if(!lname.match(patt2))
 {
alert("Last name should be alphabatic");
 return false;
 }
 else
 {
 alert("Last name Entered");
 }
 var age = document.getElementById("s3").value;
 if(age<18||age>50)
 {
 alert("Enter valid age");
 return false;
 }
 else
 {
 alert("Age Entered");
 }
 }
 </script>
</head>
<body>
 <form action="">
 Enter Student First name <input type="text" id="s1">
 Enter Student Last name <input type="text" id="s2">
 Enter Student Age<input type="text" id="s3">
<button onclick="Submit()">SUBMIT</button>
 </form>
</body>
</html>
