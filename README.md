This is an example project showing how to quickly get started w/ .NET core 1.1, EF Core 1.1, npgsql, and Google authentication.

This project started as the template project produced by VS 2015 Update 3 when creating a new .NET Core 1.0 ASP.NET project. The following modifications have been made:

* Update framework to .Net Core 1.1 (must install this separately from .NET Core 1.0 VS 2015 tools).
* Update all relevant .NET Core 1.0 dependencies to their 1.1 counterparts, including EntityFrameworkCore.
* Drop dependency for SqlServer.
* Add npgsql and its EntityFrameworkCore connector.
* Add Google authentication support
* Modify AccountController to link Google logins with an existing login if e-mail matches.

To build this project you need to download and install the .NET core 1.1 SDK. At time of writing this can be found on the [.NET downloads page under .NET Core, current version](https://www.microsoft.com/net/download/core#/current).

To create database, modify the database connection string in `appsettings.json`, then on the command line navigate to `src/ExampleProject` and run `dotnet ef update`.

To enable Google Authentication support, generate Google+ API server-side credentials, and add them to the user-secrets store by running `dotnet user-secrets set Authentication:Google:ClientId <yourId>`, followed by `user-secret set Authentication:Google:ClientSecret <yourSecret>`. More information on this can be found in this [article](http://ruimourato.com/2016/02/12/using-google-auth-middleware-aspnetcore.html), however be advised that the `user-secret`, `dnvm`, and `dnu` commands are now deprecated in favour of their `dotnet` counterparts.

If you run into other issues getting this running on your machine, please raise an issue and I'll update the project or this readme accordingly.
