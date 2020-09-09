# fakebeard-aspnetcore 
This repo is a memory jogger for basic ASP.NET core

## Create an app (razor)

1. Add a new solution
```
dotnet new sln
```
2. Create a new project
```
dotnet new webapp -o aspnetcoreapp101
```
3. Add it to the solution
```
dotnet sln add .\aspnetcoreapp101
```
4. Trust the development certificate
```
cd .\aspnetcoreapp101\
dotnet dev-certs https --trust
```
5. Run the app
```
dotnet watch run
```
## Other project types
```
dotnet new mvc
dotnet new webapi