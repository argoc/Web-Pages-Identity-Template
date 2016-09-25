# Web-Pages-Identity-Template

Starter Site for Web Pages with Identity rather than Membership (for use in Visual Studio 2015)

V1.0 Published in VS Gallery, at https://visualstudiogallery.msdn.microsoft.com/f3ce48ce-a059-40b8-9284-b8b63386a6a4. You can access this template directly within Visual Studio, search online for "Identity,razor".

This is v1.1
Visual Studio 2015 Web Pages with Identity Starter Site Release Notes v1.1
24 Sept 2016

## To Install
Download the .zip from this github repo. Remove the top-level directory it adds (so all the files and directories in it are now at the top level) and place it in your Visual Studio 2015\Templates\ProjectTemplates\ folder *as a zip file*.

It will show up under the C# templates, not the Web ones (it takes VSIX/VS Gallery to get it to move into a subcategory), as
ASP.NET Web Pages with Identity (v1.1).


## Troubleshooting

If you get an error asking you to contact the site administrator when trying to register a user or login,
try stopping and deleting the MS SQL Server daemon. In a cmd window:

    cd "C:\Program Files\Microsoft SQL Server\110\Tools\Binn"
    sqllocaldb.exe stop mssqllocaldb
    sqllocaldb.exe delete mssqllocaldb

If the error persists, check that you have an App_Data directory in your project and it is not read-only.

If the error _still_ persists, you will need to set a breakpoint in Account\Register.cshtml or Account\Login.cshtml
in the catch block found in its code and see what the actual exception is when it occurs (the error message is masking the exception).

If you are having IIS duplicate port issues, right-click the project in VS Solution Explorer,
go to its Web screen, and create a new virtual directory with a different port #.

If your project is automatically injected with Application Insights and you want to remove it:
http://stackoverflow.com/questions/23228704/remove-application-insight-from-application-on-visual-studio-2013

Have to do VSIX again? see http://rehansaeed.com/custom-visual-studio-project-templates/
Fix the URL in .csproj by erasing both port # items (<IISUrl> and <DevelopmentServerPort>)
Copy all the Content and Script files (make csproj match packages.config)
Copy the ico over.
Get PD license file and this (README) file
Most of all, good luck!
