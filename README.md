# Localization-lang-asp-mvc

In Localization of ASP MVC app
There are two things to note, one is the Global Resources which can be used all over the application to change text depending on preference, either custom name, or language preference

Creating a GlobalResources.
First you need to Go to Project Add ASP.NET folder-> App_GlobalResources

Then you can define your strings with respective value.
But there in hand, sometimes most of your string generated are internal, with that you will need to change those to be public by going through the properties of your resx file and change the Custom Tool to -> PublicResXFileCodeGenerator and also change Build to Action to Embedded Resources.

Build project.

With that you will have resources ready to be used either on the model or on the view on your own preference
i.e shown on the ResoucesFile repo here on git


Creating LocalResources
Local resources are good if you want to change text depending on different browser language.
To create LocalResources first you will need to go to the view that you want to localize, and then go to project select add ASP.NET folder choose App_LocalResources.

Add view of different localization, i.e About.sw.resx, About.da.resx

With the file created and saved you need to go to their properties and change some of the settings also so as they can be accessible
First you need to change Custom Tool -> PublicResXFileCodeGenerator, Build to Action to Embedded Resources and Custom Too Namespace to the namespaceofyoursolution.Resources i.e in this case LocalizationASPMVC.Resources

Then build project.

After here you are ready to go and consume your translation on the main About.cshtml

i.e

@{
    ViewBag.Title = "About";
}

<h2>About</h2>
<p>@LocalizationASPMVC.Resources.About.String1</p>
