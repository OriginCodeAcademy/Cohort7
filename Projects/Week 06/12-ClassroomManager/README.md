# Classroom Manager

This assignment is a week long project, broken into manageable chunks throughout the week.

The goal is to build a web application that helps campus directors manage who their students are, who their teachers are, what their classes are, and which students are enrolled in which classes.

## Toolbox
You will be using everything you have learned in the last 5 weeks to complete this project. 

**Required Tools**

```
--Backend--
SQL Server
Entity Framework
ASP Web API

--Frontend--
HTML5
CSS Frameworks
Angular
Angular-UI-Router
Angular-Toastr
```

## Data Requirements

`Student`

```
StudentId
FirstName
LastName
EmailAddress
Telephone
```

`Teacher`

```
TeacherId
FirstName
LastName
EmailAddress
Telephone
```

`Class`

```
ClassId
TeacherId
Name
StartDate
EndDate
Description
```

`Enrollment`

```
StudentId  --|
ClassId    --|
					   |_ These in combination form a composite key. Refer to Monday's lecture to see how this is modelled in Entity Framework.
```

## Screenshots
**Class Grid Screen**<br />
<img src="http://i.imgur.com/oAye5m7.png" />

**Class Detail Screen**<br />
<img src="http://i.imgur.com/if7pRyU.png" />	

**Student Grid Screen**<br />
<img src="http://i.imgur.com/cJcIVaC.png" />

**Student Detail Screen**<br />
<img src="http://i.imgur.com/D63Rg1X.png" alt="">

**Teacher Grid Screen**<br />
<img src="http://i.imgur.com/7yBbOMG.png" />

**Teacher Detail Screen**<br />
<img src="http://i.imgur.com/3CCG1ge.png" />

## Extras
* Integrate with `angular-full-calendar` to build a "Dashboard" screen.	
* Integrate with the Twilio API to allow mass-texting to all students.
* Integrate with the Twilio API to allow mass-texting to all teachers.

## Turn in instructions
* Push your changes to GitHub 
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort7/issues/new?title=18-ClassroomManager&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20How%20many%20screens%20were%20you%20able%20to%20complete%3F%0A%0A3.%20Did%20you%20complete%20any%20of%20the%20extras%3F)
	* Include a link to your repository in the description
	* Answer the questions filled out for you in the description