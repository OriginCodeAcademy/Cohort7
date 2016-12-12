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

# Step by Step

## Create the backend

### New Techniques
- Entity Framework Fluent API (Configure entity relations)
- Compound keys
- Refactoring
- Performant controllers in Web API

### Step by Step
- Create a Visual Studio solution with a Web API Project
- Configure your api
	- Remove XML formatting
	- JSON Camel Case conversion
	- CORS
- Create the models we described in our ERD diagram today
	- Person
		- Student
		- Teacher
	- Class
	- Enrollment
- Create an Entity Framework data context
	- Constructor
	- IDbSet<T>
	- OnModelCreating (Code first Fluent API)
		- `Teacher` 1-* `Class` relationship
		- `Class` \*-\* `Student` relationship
			- `Class` 1-* `Enrollment` relationship
			- `Student` 1-* `Enrollment` relationship
		- Compound Key configuration for `Enrollment`
- Migrations
	- Enable-Migrations
	- Add-Migration InitialMigration
	- Update-Database
- Add Controllers
	- Create controllers for `Teacher`, `Class`, `Student`
	- Refactor the following methods for all controllers
		- GetAll - use the `.Select` LINQ extension method to shape the resulting array
		- GetSingle - create a new anonymous object containing the information needed for a single page
		- Update - fetch the entity from the db, manually update the necessary properties and save the entity.
	- Add the following custom endpoints
		- In `ClassesController.cs`
			- `POST: /api/classes/{classId}/students/{studentId}`
			- `DELETE: /api/classes/{classId}/students/{studentId}`

## Create the frontend

### New Techniques
- angular-ui-router
	- states
	- abstract states
	- ui-sref 
- ng-options
- single page applications

### Step by Step

#### Project Setup

- Create a folder for the web project
- `bower install angular angular-ui-router bootstrap`
- Build out the following app folder structure

```
|_ app (folder)
	|_ core (folder)
		|_ class.factory.js (file)
		|_ student.factory.js (file)
		|_ teacher.factory.js (file)
	|_ class (folder)
		|_ class.detail.controller.js (file)
		|_ class.detail.html (file)
		|_ class.grid.controller.js (file)
		|_ class.grid.html (file)
	|_ student (folder)
		|_ student.detail.controller.js (file)
		|_ student.detail.html (file)
		|_ student.grid.controller.js (file)
		|_ student.grid.html (file)
	|_ teacher (folder)
		|_ teacher.detail.controller.js (file)
		|_ teacher.detail.html (file)
		|_ teacher.grid.controller.js (file)
		|_ teacher.grid.html (file)
	|_ app.module.js (file)
```

#### Development
- Create an index.html file with your "shell layout" as described in todays lecture
	- Add a navbar (see bootstrap documentation or todays video)
	- Add a container for your `ui-view` attribute.
- Implement your app.module.js file as shown in todays video.
	- Add a config section
	- Add a value 
- Implement the bare minimum of your factories/controllers by using the John Papa Angular snippets
- Add `<script>` tag references for all of your factories/controllers.
- Implement your factories
	- studentFactory
	- teacherFactory
	- classFactory
- Design each of your individual modules
	- Student
		- Grid
		- Detail
	- Teacher
		- Grid
		- Detail
	- Class
		- Grid
		- Detail

## Turn in instructions
* Push your changes to GitHub 
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort7/issues/new?title=18-ClassroomManager&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20How%20many%20screens%20were%20you%20able%20to%20complete%3F%0A%0A3.%20Did%20you%20complete%20any%20of%20the%20extras%3F)
	* Include a link to your repository in the description
	* Answer the questions filled out for you in the description