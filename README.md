# Technology-Watch-Assignation
![](https://img.shields.io/badge/javaScript-gray?logo=javaScript)
![](https://img.shields.io/badge/HTML-gray?logo=HTML5)
![](https://img.shields.io/badge/Bootstrap_vue-gray?logo=Bootstrap).


The aim of this project is to be able to create a list of students in one hand, and in the other hand be able to randomly assign a chosen Topic to a Student who wasn't assigned yet to a Technology Watch. A single page in which we can add both students and Technology Watch.

## content
* [App](#app)
* [Screenshots](#screenshots)
* [JScode](#JScode)
<br><br>
## Screenshots
![Test Image 4](https://github.com/mowafag-omer/Technology-Watch-Assignation/blob/master/Capture.PNG)
<br><br>
## JScode
- Show students and Assassinated Technologies lists once the page has loaded
```js
window.onload = () => {
  students = JSON.parse(localStorage.getItem('student')) 
  techs = JSON.parse(localStorage.getItem('tech')) 
  
  students.forEach((i) => studentsName.push(i))
  techs.forEach((i) => technologie.push(i) )

  list[0].innerHTML = studentsName.map(i => "<li>" + i + "</li>").join('') 
  list[1].innerHTML = technologie.map(i => `<li> ${i[0]} - ${i[1]}</li>`).join('') 
}
```
- add student and store data in the localStorage
```js
form[0].addEventListener('submit', (event) => {
  event.preventDefault()
  studentsName.push(studentInput.value)
  localStorage.setItem("student", JSON.stringify(studentsName))
  list[0].innerHTML += "<li>" + studentInput.value + "</li>"
  form[0].reset()  
})
```
- randomly assign a chosen Topic to a Student who wasn't assigned yet to a Technology Watch
```js
form[1].addEventListener('submit', (event) => {
  event.preventDefault()
  random = [Math.floor(Math.random() * studentsName.length)]
  technologie.push([techInput.value, studentsName[random]])
  localStorage.setItem("tech", JSON.stringify(technologie))
  list[1].innerHTML += "<li>" + techInput.value + ' - ' + studentsName[random] + "</li>"
  form[1].reset()
})

```
