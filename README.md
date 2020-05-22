# SpilledMilkCOMTest

Test restoring the SM.Serialization package and using GitHub Actions.

1) Forked from Jamie's repo
2) Enabled Actions on the forked repo
3) `git clone` to my machine
4) `dotnet restore` *(used credentials in nuget.config)*
5) Removed credentials from the nuget.config
6) `dotnet restore` *(used credentials in global nuget.config)*

In both `restore` cases I did not see any errors.

Now it's time to check in the code to see if it triggers the action.  That triggered the action, but since I removed the credentials the Action blew up because there were no credentials...  duh, comes to mind. :laughing:

Once I added the credentials back into the nuget.config file, the Action passed.  **BOTH** tokens worked!  This is to illustrate a (super) **CLEAN** build versus running the build on your local machine where things could get cached.
