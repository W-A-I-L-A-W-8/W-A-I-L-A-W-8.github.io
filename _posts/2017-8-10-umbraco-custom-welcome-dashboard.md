---
layout: post
title: Create an Umbraco custom welcome dashboard
published: false
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

We now need a stylesheet to put our styles in.  Lets call it 'customwelcomedashboard.css'.

    .welcome-dashboard h1 {
        font-size:4em;
        color:purple;
    }
