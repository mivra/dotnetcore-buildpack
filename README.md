# Heroku .NET Core Buildpack

## Overview
A basic .NET Core Buildpack that serves up a .NET Core application from behind a lightweight Go HTTP proxy.

It relies on there being a `Startup.cs` file alongside a `{PROJECT}.csproj` file to compile and will only search 5 directories deep. An example folder structure:
```
- Project.Website
  - Controllers
  - Properties
  - Views
  - wwwroot
  - appsettings.json
  - bower.json
  - bundleconfig.json
  - Program.cs
  - Project.Website.csproj
  - Startup.cs
- Project.Framework
  - Data
  - Business
  - Services
```

N.B. The csproj file for the Website must be named the same as it's parent folder, e.g. A folder of `Project.Website` with a csproj file of `project.website.csproj` would fail.

## Usage
For Heroku-16 stack use:
```
heroku buildpacks:set https://github.com/benmj87/dotnetcore-buildpack
```
