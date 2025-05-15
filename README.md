2)
<!DOCTYPE html>
<head>
    <title>
        String Manipulation
    </title>
    <script>
        function isPalindrome(str){
            let cleanstr=str.replace(/[^A-Za-z0-9]/g,'').toLowerCase();
            return cleanstr===cleanstr.split('').reverse().join('');
        }
        let userinput=prompt("enter a string");
        let lengthOfString=userinput.length;
        let extractedword=userinput.includes("javascript")? userinput.substring(userinput.indexOf("javascript"),
    userinput.indexOf("javascript")+"javascript".length):"javascript not found";
    let newstring=userinput.replace("javascript","typescript");
    let palindromecheck=isPalindrome(userinput);
    console.log(`new string ${newstring}`)
    alert(`length= ${lengthOfString}\n extracted: ${extractedword} \m paindrome ${palindromecheck}\n  new string${newstring}`)
    </script>
</head>
</html>

3)
<!DOCTYPE html>
<head>
<title>Dynamic Student Object</title>
<script>
function createStudent()
{
let student =
{
name: prompt("Enter the student's name:"),
grade: parseFloat(prompt("Enter the student's grade:")),
subjects: prompt("Enter the student's subjects separated bycommas:").split(',').map(subject => subject.trim()),
passed: function()
{
return this.grade >= 50;
}
};
return student;
}
function displayInfo(student)
{
console.log("Student Details:");
for (let key in student)
{
if (typeof student[key] !== 'function')
{
    console.log(`${key}: ${student[key]}`);
}
}
console.log("Passed:", student.passed() ? "Yes" : "No");
console.log(" ");
}

let numStudents = parseInt(prompt("How many students' details wouldyou like to enter?"));
for (let i = 0; i < numStudents; i++)
{
console.log(`Enter details for student #${i + 1}:`);
let student = createStudent(); 
displayInfo(student);
}
</script>
</head>
</html>

4)
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Event Listeners Experiment</title>
</head>
<body>
  <button id="b">Click Me</button>
  <img
    id="image"
    src="https://www.w3schools.com/html/img_chania.jpg"
    alt="Experiment Image"
    width="200"
  >
  <script>
    document.getElementById('b').addEventListener('click', function() {
      console.log("Button clicked!");
    });
    document.getElementById('image').addEventListener('mouseover', function() {
      this.style.border = '5px solid red';
    });
    document.getElementById('image').addEventListener('mouseout', function() {
      this.style.border = 'none';
    });
    document.addEventListener('keydown', function(event) {
      console.log("Key pressed: " + event.key);
    });
  </script>
</body>
</html>

5)
import React from 'react';
const issues = [
{ id: 1, title: 'Bug in Login', description: 'Error 404 on login',
status: 'Open' },
{ id: 2, title: 'UI Issue on Dashboard', description: 'Misaligned elements', status: 'Closed' },
{ id: 3, title: 'API Timeout', description: 'Delayed response fromserver', status: 'Open' },
];
function IssueList() { 
return (
<div>
<h1>Issue Tracker</h1>
<ul>
{issues.map(issue => (
<li key={issue.id}> 
<h2>{issue.title}</h2> 
<p>{issue.description}</p> 
<p>Status: {issue.status}</p> 
</li>
))}
</ul>
</div>
);
}
export default IssueList;

6)
import React, { useState, useEffect } from 'react';
const Counter = () => {
const [count, setCount] = useState(0);
useEffect(() => {
setTimeout(() => {
setCount(0);
}, 2000);
}, []);
return (
<div>
<h1>Counter: {count}</h1>
<button onClick={() => setCount(count +1)}>Increment</button>
<button onClick={() => setCount(count -1)}>Decrement</button>
<button onClick={() => setCount(count * 2)}>Double</button>
<button onClick={() => setCount(0)}>Reset</button>
</div>
);
};
export default Counter;
