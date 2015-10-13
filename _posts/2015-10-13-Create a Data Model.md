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

Hi guys, 
	In this tutorial you can learn create and update model classes use in c#.
	may be you are knowing or not knowing :D 

- #### Create a Table mssql: 


![Create Student Table](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/image1.png?raw=true "Create Student Table")

then open your .net project folder and in solution explorer add another new project folder name DataModel. In that folder you can add 2 folders.
today I intended to cover for Model folder only. next tutorial I will cover on ModelFactories folder.

- #### Create a class in your project folder: 

1. Add class name as StudentModel.
2. Then update your entity model. (edmx file must update / hope you know to do it. if you got any exception error feel free to shout me.)
3. if it is done next thing you must to do open your studentModel class and add Create and Update model classes like this.
   
   public class studentModel
    {
        public class CreateStudentModel
        {       
            public int studentId { get; set; }
            public string studentName { get; set; }
            public Nullable<int> Age { get; set; }
            public string description { get; set; }
        }

        public class UpdateStudentModel
        {
            public int studentId { get; set; }
            public string studentName { get; set; }
            public Nullable<int> Age { get; set; }
            public string description { get; set; }
        }
    }
	
![Create and update model class](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/image2.png?raw=true "Create and Update")




Cheers,
Rangana
