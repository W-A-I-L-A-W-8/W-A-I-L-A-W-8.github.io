---
layout: post
title: Umbraco, enable the text-color picker on the rich text editor and add custom colours
published: true
categories: [Umbraco, CMS]
---

I was recently asked to add our company's corporate colours to the text-colour picker in the Umbraco rich text editor (RTE) so I wanted to share my experience of doing this.

## Quick Overview of the task
Enable the text-colour picker, configure it and add custom colours to the picker.

## Step 1 | Configure TinyMCE
Umbraco ships with the TinyMCE plugin but it doesn't come configured with the text colour picker. For this feature we needed to do this and to establish predefined colours for the picker that were inline with the brand.

Open the solution in Visual Studio and look in the /Config folder for the 'tinyMceConfig.config'. Put the following snippet before the closing </commands> tab.

    <command>
      <umbracoAlias>mceForeColor</umbracoAlias>
      <icon>images/editor/forecolor.gif</icon>
      <tinyMceCommand value="" userInterface="true" frontendCommand="forecolor">forecolor</tinyMceCommand>
      <priority>76</priority>
    </command>

## Step 2 | Ask Umbraco to load the text-colour picker
In the 'tinyMceConfig.config' file scroll down to the plugins section and adding the following inside the <plugins> node.

    <plugin loadOnFrontend="true">textcolor</plugin>

## Step 3 | Add custom colours
Inside the <customConfig> node configure your custom colours with the config key. These are the colours I used for our brand.

    <config key="textcolor_map">
      [
      "01395c", "Corp blue",
      "ea981a", "Corp Orange",
      "553772", "Purple",
      "1693a5", "CTA Teal",
      "f78902", "CTA Orange",
      "6ea514", "Green",
      "ff0505", "CTA Red"
      ]
    </config>

## Step 4 | Touch the 'web.config'
Make a minor change to the 'web.config' file and save it. This will recycle the app pool.

## Step 5 | Richtext Editor Umbraco data type
In the Umbraco back-office find the 'Richtext editor' in 'Datatypes' and check the 'mceforecolor' checkbox.

![mceForeColor](/images/post/mceforecolor.png)

You should now see the text colour picker as a tool within your RTE on content pages.

![mceForeColor](/images/post/textcolourpicker.png)

## Empower your editors
It's a pretty straight forward task to complete but it empowers your editors to do just that little bit more with their content. Remember, "less is more" so don't over do it on the features.
