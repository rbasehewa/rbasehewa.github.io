---
author: Rangana Maddumahewa
layout: post
title: "Creating the Help Page in ASP. NET Web API"
date: 2015-11-05 21:00
comments: true
category : C#
tags:
- C#
---

 Hi Guys, 
 
	Today i'm going to share with you create a help page

- #### Introduction: 

	Before begin this tutorial i would like to talk about why you need HELP PAGE.
	
	let me give a simple example. If you are devloping mobile application (Ios or Droid) you need tough backend to that you cant handle only SQLITE integration. So that you need kind of services to call. Help page is something like that. All the service urls on top of the help page layout.

- #### Initialization: 

	First you need to create Asp .Net Web Application Project.
	
		

- #### Steps:

	- ### Install the test client package using the following procedure:

		--- Go to Tools.

		--- Choose "Library Package Manager" -> "Manage Nuget Packages" for the solution.

		--- Make sure to "Include Prerelease".

		--- Type "webapitestclient" in the search TextBox in the top-right corner.

		--- Now click on install for installing it.
   	
	![Install web Api test](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/webapitest.png?raw=true "Create and Install")

----When the Web API Test Client is installed, the following files will be added to your application----

--- Scripts\WebApiTestClient.js
--- Areas\HelpPage\TestClient.css
--- Areas\HelpPage\views\Help\Display Template\TestClientReferences.cshtml
--- Areas\HelpPage\views\Help\Display Template\TestClientDialogs.cshtml
			
		- #### Now write the Test Client on the help page.
		
			For selecting the Api.cshtml, go to the Solution Explorer and choose "Areas\HelpPage\Views\Help\Display Templates\Api.cshtml".
			
![Solution in Visual Studio](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/API_html1.png?raw=true "Solution in Visual Studio")
			
			We add the following code in the Api.cshtml file that is @Html.DisplayForModel("TestClientDialogs"). We can add this code after the <div> tag. And @HtmlDisplayForModel("TestClientReferences") we can add this code inside the scripts section.


				@using System.Web.Http
				@using MvcApplication4.Areas.HelpPage.Models
				@model HelpPageApiModel
 
				@{
    					var description = Model.ApiDescription;
    					ViewBag.Title = description.HttpMethod.Method + " " + description.RelativePath;
				}
 
					<div id="body">
    						<section class="featured">
        						<div class="content-wrapper">
            					<p>
                					@Html.ActionLink("Help Page Home", "Index")
            					</p>
        				</div>
    				</section>
    				<section class="content-wrapper main-content clear-fix">
        				@Html.DisplayFor(m => Model)
    				</section>
				</div>
					@Html.DisplayForModel("TestClientDialogs")
						@section Scripts {
    						<link type="text/css" href="~/Areas/HelpPage/HelpPage.css" rel="stylesheet" />
    						@Html.DisplayForModel("TestClientReferences")
								}

![Solution in Visual Studio](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/API_html2.png? raw=true "Solution in Visual Studio")



		- #### Now we add some JavaScript files into the TestClientReferences.cshtml that is visible in the scripts folder.

		jquery-1.8.2.js
		knockoutjs 2.1.0.js
		jquery.ui.1.10.3.js
		
		We can drag and drop these files into the TestClientreferences.cshtml file. For selecting the TestClientReferences.cshtml. Go to Solution Explorer and choose 
		"Areas\HelpPage\Views\Help\Display Templates\TestClientReferences.cshtml".

![test clint refference](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/testclintrefference.png? raw=true "test clint refference")


			The code looks like this:


				@using System.Text.RegularExpressions
				<script src="~/Scripts/jquery-1.8.2.js"></script>
				<script src="~/Scripts/knockoutjs%202.1.0.js"></script>
				<script src="~/Scripts/jquery-ui-1.10.3.js"></script>
				<link href="~/Content/themes/base/jquery.ui.all.css" rel="stylesheet" />
				<link href="~/Areas/HelpPage/TestClient.css" rel="stylesheet" />
				@* Automatically grabs the installed version of JQuery/JQueryUI/KnockoutJS *@
				@{var filePattern = @"(jquery-[0-9]+.[0-9]+.[0-9]+.js|jquery-ui-[0-9]+.[0-9]+.[0-9]+.js|knockout-[0-9]+.[0-9]+.[0-9]+.js)";}
				@foreach (var item in Directory.GetFiles(Server.MapPath(@"~/Scripts")).Where(f => Regex.IsMatch(f, filePattern)))
				{
   				 <script src="~/Scripts/@Path.GetFileName(item)"></script>
				}
				<script src="~/Scripts/WebApiTestClient.js" defer="defer"></script>

				If these files are not showing in Scripts folder then you can download these files.



		- #### After performing these steps, when we execute the application the Test API button is shown in lower-right corner. And the output looks like this:

![help page](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/helppage.png?raw=true "help page")




		- #### Now we test the Web API.

		We click on Test API button. There is the URI parameter open and one TextBox for the URI parameter.
		And fill the value in the TextBox. Click on "Add header" and enter "application/json". That gives the response in JSON.

![Test Help Page](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/testHelpPage.png?raw=true "Test Help Page")

		- #### Click on "Add header" and add the "accept text/xml" asking for XML. Click on the "Send" button.

		The response is
![JSON Format](https://github.com/rbasehewa/rbasehewa.github.io/blob/master/images/json.png?raw=true "JSON Format")

		



Cheers,
Rangana
