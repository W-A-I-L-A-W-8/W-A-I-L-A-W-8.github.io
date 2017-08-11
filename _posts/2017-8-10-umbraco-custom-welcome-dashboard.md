---
layout: post
title: Create an Umbraco custom welcome dashboard
published: true
---

For a more personal experience for your editors why not create a custom welcome dashboard on your Umbraco website. This can be achieved in a few simple steps from Visual Studio. I had to do it recently for a client site and my main source of reference for this was an article published on the Umbraco site.

## Step 1 | Set up a plugin
In Solution Explorer under '/App_plugins' folder, add a new folder and name it something like 'CustomWelcomeDashboard'

## Step 2 | Create a dashboard view
Add a HTML file inside the folder above and call it 'WelcomeDashboard.html' and some markup in it like so.

    <div class="welcome-dashboard">
        <h1>Welcome to Umbraco</h1>
        <p>We hope you find the experience of editing your content with Umbraco enjoyable and delightful. If you discover any problems with the site please report them to the support team at <a href="mailto:">support@popularumbracopartner.com</a></p>
        <p>You can put anything here...</p>
    </div>

## Step 3 | Lets configure the dashboard to appear
In the dashboard.config file (You will find this in the /config folder of your site) add the following section:

    <section alias="Custom Welcome Dashboard">
        <access>
          <deny>translator</deny>
        </access>
        <areas>
          <area>content</area>
        </areas>
        <tab caption="Welcome">
          <control>
            /app_plugins/CustomWelcomeDashboard/WelcomeDashboard.html
          </control>
        </tab>
    </section>

## Step 4 | Start your website
Fire up your Umbraco site and you should see a new tab labelled 'Welcome' and the content from your view in the body.

## Take it a bit further with some style
As with any web page you can style it with CSS.  First, we will need to create a file called package.manifest in our CustomWelcomeDashboard folder. This file allows Umbraco to load other resources to use with the HTML view.

      {
        "javascript": [
        /*list of javascript files appear here*/
        ],
        "css": [
        /*List of stylesheets appear here:*/
        "~/app_plugins/CustomWelcomeDashboard/customwelcomedashboard.css"
        ]
      }

We now need a stylesheet to put our styles in. Lets call it 'customwelcomedashboard.css'.

      .welcome-dashboard h1 {
          font-size:4em;
          color:purple;
      }

## Add some functionality
We can build some functionality to the dashboard by using an AngularJS controller with the view. Add another file to the CustomWelcomeDashboard folder called 'customwelcomedashboard.controller.js'.  Update the package.manifest to load this file.

      {
        "javascript": [
        /*list of javascript files appear here*/

        ],
        "css": [
        /*List of stylesheets appear here:*/
        "~/app_plugins/CustomWelcomeDashboard/customwelcomedashboard.css"
        ]
      }

## Umbraco Angular Services and Directives
Umbraco has a bunch these for use in your own custom property editors and dashboards. For a recent dashboard I customised it to make it welcome the editor by name by using the userService.  We register the AngularJS controller to the Umbraco Angular module and inject the userService.

      angular.module("umbraco").controller("CustomWelcomeDashboardController", function ($scope, userService, logResource, entityResource) {
      var vm = this;
      vm.UserName = 'guest';

and then we can use the userService's promise based getCurrentUser() method to get the details of the current logged in user:

      var user = userService.getCurrentUser().then(function (user) {
              console.log(user);
              vm.UserName = user.name;
          });

Last thing to do, update the view as follows:

      <h1>Welcome <span>{{vm.UserName}}</span> to your beautiful Umbraco dashboard!</h1>

Here's what my final dashboard looks like. As you can see I have also included a little illustration and some buttons to take the editor quickly to specific sections. I will tell you more about this shortly.

![Custom Welcome Dashboard](/images/post/customumbracodash.jpg)

My buttons were added by updating the HTML view:

      <div class="topmargin-lg">
          <h2>What would you like to do today?</h2>
              <a class="btn btn-primary btn-large" href="/umbraco/#/content/content/edit/1117"><i class="icon-edit"></i> Edit a Tour</a> <a class="btn btn-default btn-large" href="/umbraco/#/media">Update Media</a>
      </div>

## Your dashboard is your oyster
This is just a very small part of what you can do to customise your Umbraco dashboard. Perhaps you might want to display previous articles edited, use it as a tool to search specific content.  Whatever you do, make it personal!
