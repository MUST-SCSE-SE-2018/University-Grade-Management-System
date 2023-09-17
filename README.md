# University-Grade-Management-System

<div align="center">

  [![description](https://img.shields.io/badge/project-Individual-1F1F1F?style=for-the-badge)](https://github.com/KennardWang/University-Grade-Management-System)
  &nbsp;
  [![stars](https://img.shields.io/github/stars/KennardWang/University-Grade-Management-System?style=for-the-badge&color=FDEE21)](https://github.com/KennardWang/University-Grade-Management-System/stargazers)
  &nbsp;
  [![forks](https://img.shields.io/github/forks/KennardWang/University-Grade-Management-System?style=for-the-badge&color=white)](https://github.com/KennardWang/University-Grade-Management-System/forks)
  &nbsp;
  [![contributors](https://img.shields.io/github/contributors/KennardWang/University-Grade-Management-System?style=for-the-badge&color=8BC0D0)](https://github.com/KennardWang/University-Grade-Management-System/graphs/contributors)
  
  <img src="https://img.shields.io/badge/windows-0078D6?logo=windows&logoColor=white&style=for-the-badge" />
  &nbsp;
  <img src="https://img.shields.io/badge/Java-ED8B00.svg?logo=java&logoColor=white&style=for-the-badge" />
  &nbsp;
  <img src="https://img.shields.io/badge/Eclipse-2C2255?logo=eclipse&logoColor=white&style=for-the-badge" />
</div>

<br>

<div align=center>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/UGMS.png" width="70%" />
</div>

<br>

It is a project of MUST course ***LP002-Data Structure***, which is a grade management system for students. After importing the students' grade data for one or multiple courses, users can browse, sort, and search the data, as well as calculate GPA (Grade Point Average).



## Table of Contents

- [Development Environment](#development-environment)
- [Install](#install)
- [Usage](#usage)
- [Highlights](#highlights)
- [Design](#design)
- [Algorithms](#algorithms)
- [Releases](#releases)
- [Maintainers](#maintainers)
- [Contributing](#contributing)
- [License](#license)



## Development Environment

| <!--> | <!--> |
|:---:|:---:|
| System | Windows 10 x64 |
| Language | Java 8 |
| IDE | Eclipse 2018-12 (4.10.0) |



## Install

1. [Download](https://github.com/KennardWang/University-Grade-Management-System/releases) **jdk 8u202** and install.
2. [Download](https://github.com/KennardWang/University-Grade-Management-System/releases) **UGMS_v2.1.jar**.
3. Execute the binary file without any external plugins.

  ```
  java -jar UGMS_v2.1.jar
  ```



## Usage

+ Sort
    1. Click the **File** and choose **Open File** option.
    2. Choose a ***.txt*** course file and select the sort approach.
    3. Click the **Display** button. (Please import the required files before using GPA sort)

+ Query
    1. Click the **File** and choose **Import File** option.
    2. Import all the ***.txt*** course files which you need and then select the query approach.
    3. Remember to input the corresponding query message.
    4. Click the **Query** button.

    <br>
    
      Query Message Example
      ----------------------------------------------------------------------------
      ID: 1X09853X-X011-XXXX
      Surname: Weng
      WildCard(surname): W, We, We, Weng ... (The first letter must be upper case)
      GPA Ranging: > 3.0, = 3.0, < 3.0, >= 3,0, <= 3.0 (Need space between the operator and the number)



## Highlights
- [x] Implement a user-friendly GUI.
- [x] Nice output format (JTable).
- [x] Implement advanced query functions such as surname wildcard and GPA ranges. 
- [x] Allow the user to add and delete courses.
- [x] Do not depend on any external plugins and environments other than JRE.
- [x] The UGMS sometimes prompts alerts via message windows or checkboxes.
- [x] No need to worry about sort time (<1 sec).



## Design

<div align=center>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/general.png" width="70%" />
  <br>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/GUI.png" height="400px" />
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/Student.png" height="400px" />
  <br>
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/Course.png" height="200px" />
  <img src="https://kennardwang.github.io/ImageSource/University-Grade-Management-System/Sort.png" height="200px" />
  
</div>

<br>

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



## Algorithms

The program adopts **Selection Sort** with the complexity of $O(N^2)$ and **Sequential Search** by each course with the complexity of $O(N^2)$. In addition, it is based on a once-input store, which means each time you input a course, the UGMS stores data of all the students who take this course simultaneously. The number of one file data is less than 1000, so it is reasonable for a standard PC to execute for/while loop within 1 second ( Total about $10^6$, and PC can compute $10^8$ per second ).



## Releases

[![badge](https://img.shields.io/badge/release-v2.1-FF7800)](https://github.com/KennardWang/University-Grade-Management-System/releases/tag/v2.1)



## Maintainers

![badge](https://img.shields.io/badge/maintenance-NO-EF2D5E) [@KennardWang](https://github.com/KennardWang)



## Contributing

Feel free to [open an issue](https://github.com/KennardWang/University-Grade-Management-System/issues) or submit [PRs](https://github.com/KennardWang/University-Grade-Management-System/pulls).



## License

[![license](https://img.shields.io/github/license/KennardWang/University-Grade-Management-System)](LICENSE) © Kennard Wang ( 2019.11.5 )
