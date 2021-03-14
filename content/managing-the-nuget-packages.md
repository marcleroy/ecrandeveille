---
title: 'Managing the NuGet packages'
date: Fri, 24 Jan 2020 21:23:22 +0000
draft: false
tags: ['Cleaning', 'Dev machine']
---

From Managing the global packages, cache, and temp folders [here](https://docs.microsoft.com/fr-fr/nuget/consume-packages/managing-the-global-packages-and-cache-folders)

### Viewing folder locations

You can view locations using the [nuget locals command](https://docs.microsoft.com/fr-fr/nuget/reference/cli-reference/cli-ref-locals):

```
# Display locals for all folders: global-packages, http cache, temp and plugins cache
nuget locals all -list
```

You can also view folder locations using the dotnet nuget locals command:

```
dotnet nuget locals all --list
```

### Clearing local folders

If you encounter package installation problems or otherwise want to ensure that you're installing packages from a remote gallery, use the `locals --clear` option (dotnet.exe) or `locals -clear` (nuget.exe), specifying the folder to clear, or `all` to clear all folders:

```
# Clear the 3.x+ cache (use either command)
dotnet nuget locals http-cache --clear
nuget locals http-cache -clear

# Clear the 2.x cache (NuGet CLI 3.5 and earlier only)
nuget locals packages-cache -clear

# Clear the global packages folder (use either command)
dotnet nuget locals global-packages --clear
nuget locals global-packages -clear

# Clear the temporary cache (use either command)
dotnet nuget locals temp --clear
nuget locals temp -clear

# Clear the plugins cache (use either command)
dotnet nuget locals plugins-cache --clear
nuget locals plugins-cache -clear

# Clear all caches (use either command)
dotnet nuget locals all --clear
nuget locals all -clear
```