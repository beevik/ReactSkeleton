# Web App Skeleton

This project contains a skeleton for a web application that uses:
  * [ASP.NET Core 2.1](https://docs.microsoft.com/en-us/aspnet/core/?view=aspnetcore-2.1) for the back-end
  * [React](https://reactjs.org) for the front-end UI
  * [Material-UI](https://material-ui.com/) for the React components
  * [Typescript](https://typescriptlang.org) as the front-end language

The rest of this document describes the steps I used to create the skeleton.
You can view the results of each step by viewing this repository's [commit
history](https://github.com/beevik/ReactSkeleton/commits/master).

## Create the ASP&#46;NET Core app

Use the .NET core command line utility to create the back-end app template.

```
dotnet new webapi --name App
```


## Create the react client app

In the .NET core app's root directory, create a Typescript-based React
application client template.

```
cd App
npx create-react-app client --typescript
rmdir wwwroot
mv client ClientApp
```


## Install Material-UI

Install the Material-UI package into the React application.

```
cd ClientApp
yarn add @material-ui/core
yarn add @types/material-ui
```

If you don't use [yarn](https://yarnpkg.com/), you can type `npm install`
instead of `yarn add`.


## Modify the ASP&#46;NET Core app's startup

Modify the ASP&#46;NET Core app's `Startup.cs` file to configure it as a
single-page application and to locate the React client files.

I did this by copying and slightly modifying code generated by `dotnet new
react` in another directory.


## Include Material-UI fonts

Add the following to the `<head>` section to include the Material-UI
Roboto font:

```
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto:300,400,500" />
```

Also, remove all the boilerplate comments from `index.html`.


## Remove boilerplate crud

* Modify `App.tsx` and `App.css` to remove the React logo and boilerplate.
* Delete `logo.svg`.
