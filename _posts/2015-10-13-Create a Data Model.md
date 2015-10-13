---
author: Rangana Maddumahewa
layout: post
title: "Create a sample date model"
date: 2015-10-13 21:00
comments: true
category : .Net, C#
tags:
- .Net
- C#
- MsSql
---

 Hi Guys, 
 
	In this tutorial you can learn create and update model classes use in c#.
	may be you are knowing or not knowing :D 

- #### Create a Table mssql: 


![Create Student Table](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/image1.png?raw=true "Create Student Table")

		Then open your .net project folder in solution explorer and add another new project folder name DataModel.
		In that folder you can add folder name "DataModel".
		Today I intended to cover for Model folder only. next tutorial I will cover on ModelFactories folder.

- #### Create a class in your project folder: 

		1. Add class name as StudentModel.
		2. Then update your entity model. (edmx file must update / hope you know to do it. if you got any exception error feel free to shout me)
		3. if it is done next thing you must to do open your studentModel class and add Create and Update model classes like this.
   	
![Create and update model class](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/image2.png?raw=true "Create and Update")

- #### Purpose:

		- ### When you adding these crate and update models you can pass straightly to your web method.
		- ### you don't need to send all data. 
			- ## As an example let's think of user login example.
			
			you can remove password field on your Createmodel. when it is passing, you don't required your whole bunch of data. 
			just need what is necessary data only.
			
			
			
			I will continue on this next tutorial.



Cheers,
Rangana
