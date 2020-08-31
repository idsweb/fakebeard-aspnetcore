# fakebeard-aspnetcore 
This repo is a memory jogger for basic ASP.NET core

1. Add a new solution
```
dotnet new sln
```
2. Create a new project
```
dotnet new webapp -o aspnetcoreapp101
dotnet sln add .\aspnetcoreapp101
cd .\aspnetcoreapp101\
dotnet dev-certs https --trust
dotnet watch run
```
