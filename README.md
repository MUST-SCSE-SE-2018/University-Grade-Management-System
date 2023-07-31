# University-Grade-Management-System

### Demo

<div align=center>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/UGMS.png" width="70%" />
</div>

------

### Development Environment

| <!--> | <!--> |
|:---:|:---:|
| System | Windows 10 x64 |
| Language | Java 8 |
| IDE | Eclipse 2018-12 (4.10.0) |

------

### Usage
+ Installation
  > 1. [Download](https://github.com/KennardWang/University-Grade-Management-System/releases) **jdk 8u202** and install.
  > 2. [Download](https://github.com/KennardWang/University-Grade-Management-System/releases) **UGMS_v2.1.jar**.
  > 3. Please execute binary file by `java -jar UGMS_v2.1.jar` without any external plugins.

+ Sort
  > 1. Click the **File** and choose **Open File** option.
  > 2. Choose a ***.txt*** course file and select the sort approach.
  > 3. Click the **Display** button.
  >
  > **P.S.** Before using GPA sort, please import required files first !

+ Query
  > 1. Click the **File** and choose **Import File** option.
  > 2. Import all the ***.txt*** course files which you need and then select the query approach.
  > 3. Remember to input the corresponding query message. 
  > Here is an example :
  >    + ID : **1X09853X-X011-XXXX**
  >    + Surname : **Weng**
  >    + WildCard(surname) : **W, We, We, Weng ...** ( The first letter must be upper case )
  >    + GPA Ranging: **> 3.0**, **= 3.0**, **< 3.0**, **>= 3,0**, **<= 3.0** ( Need space between the operator and the number )
  > 4. Click the **Query** button.

------

### Design

<div align=center>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/general.png" width="70%" />
</div>

<br>

+ Student Class

<div align=center>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/Student.png" width="70%" />
</div>

+ Course Class

<div align=center>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/Course.png" width="70%" />
</div>

+ SortAlgorithms Class

<div align=center>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/Sort.png" width="70%" />
</div>

+ GUI Class

<div align=center>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/GUI.png" width="70%" />
</div>

------

### Data Structure
+ Student Class

| Variable / Function Name | Data Structure |	Description |
|:---:|:---:|:---:|
| sur/giv/id/score/Grade/GPA | Basic type (String/int/double) | The basic info of each student including surname, given name, id, score, Grade, GPA and so on |
| credit | 2-dimension array	| The student's real credit for every course. ( Parsed by Grade ) |
| takecourse | String array	| All the courses the student takes |
| courseCredit | Int array | Corresponding credit of each taken course |
| Student()	| / |	Constructor |
| getsur(), getgiv(), getid(), getscore(), getGrade(), getStuData()	| / |	Methods to read data from the source file and return corresponding value |
| Grade2Credit() | /	| Parse Grade to credit |
| Credit2Grade() | / | Parse credit to Grade |
| computeGPA() | / | Using credit/takecourse/courseCredit to calculate the total GPA |

+ Course Class

| Variable / Function Name | Data Structure |	Description |
|:---:|:---:|:---:|
| course/coName/credit/num | Basic type (String/int) | Basic info of a course|
| GraCount | Int array | Count the number of students in each Grade |
| highscore/lowscore/averscore | Int/double | Store the highest/lowest/average score of each course |
| Course() | / | Constructor |
| gerCourseData()	| /	| Read data from the source file and return the corresponding value |

+ SortAlgorithms Class

| Variable / Function Name | Data Structure |	Description |
|:---:|:---:|:---:|
| exchange() | / | Exchange two elements in an array|
| less() | / | Compare two elements ( if former < latter then return true )|
| sort() | / |	Main sort algorithm |
| sortField()	| / |	Sort data in one aspect |
| sortWay() |	Stack |	Using stack to implement descending order |

+ GUI Class

| Variable / Function Name | Data Structure |	Description |
|:---:|:---:|:---:|
| contentPane	| JPanel | The JFrame window |
| fr | JFrame | The Frame |
| ReqInput | JTextField	| The input of query |
| CourseInput |	JTextField |	The input of course name |
| Screen | JTextArea	| The main screen |
| CourseList| JTextArea|	The list of course |
| RadioButton 1 & 2	| JRadioButton | The ascending & descending button |
| lblCredit	| JLabel | The credit label |
| lblNumberOfStudents	| JLabel | The label of the student number |
| AddButton & DeleteButton | JButton | Add & Delete course |
| Choice_1 | JComboBox\<String> | Sort choice |
| MenuBar	| JMenuBar |	Menu bar |
| File |	JMenu |	Menu name |
| closeItem/openItem/importItem |	JMenuItem | Menu item |
| openDia	| FileDialog	| File dialog |
| sta	| Stack	| Store the course |
| stu	| Stack	| Store the Student element |
| index |	int	| Used to store course name |
| num	| int |	Index of choice 1 |
| num2 | int | Index of choice 2 |
| main() | / | Start of the whole program |
| myEvent()	| void | Operation of the file |
| GUI()	| / |	Constructor ( contains GUI components ) |
| IsDifferent() |	/	| Judge whether the new element is repetitive or not |
| IsDifferent(override)	| /	| Judge whether the new element is repetitive or not |
| readtxt()	| String array | Read the raw data and split it into groups |
| display()	| / |	Reveal the data |
| SortAndOutput()	| / | Execute sort and display method |
| Query()	| / |	Based on ReqInput, search for detailed data |

------

### Core Algorithms
+ Sort
> Selection Sort, the complexity is $O(N^2)$.

+ Search
> Sequential Search, search by each inputted course individually, the complexity is $O(N^2)$.

+ Analysis
> This program is based on a once-input store, which means each time you input a course, the UGMS stores data of all the students who take this course simultaneously. The number of one file data is less than 1000, so it is reasonable for a standard PC to execute for/while loop within 1 second ( Total about $10^6$, and PC can compute $10^8$ per second ).

------

### Features
1. Implement a user-friendly GUI.
2. Nice output format ( using JTable ).
3. Implement advanced query functions ( such as Surname Wild Card, GPA ranging ). 
4. Allow the user to add and delete courses according to their requirement.
5. Can execute without other plugins and environments except JRE.
6. The UGMS sometimes prompts you by showing a message window or a check box.
7. No need to worry about sort time ( < 1 sec ).

------

### License  
+ [MIT License](https://github.com/KennardWang/University-Grade-Management-System/blob/main/LICENSE)

------

### Author
+ Kennard Wang ( 2019.11.5 )
