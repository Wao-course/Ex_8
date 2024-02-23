# Exercises

## Exercise 1
Start out by following [Tutorial: Create a gRPC client and server in ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/tutorials/grpc/grpc-start) that will take you through the steps of creating a gRPC server and client application in .NET. If you get stuck, you can check out the complete codebase in the offical ASP.NET docs repository @ [GitHub](https://github.com/dotnet/AspNetCore.Docs/tree/main/aspnetcore/tutorials/grpc/grpc-start/sample6)

> following the tutorial we been able to create a server and a client with the posibility to ping/pong an echo message.  Run the projects by running Ctrl+F5 in Visual Studio or by running the following commands in the terminal: 
>   - `dotnet run -p GreeterServer`
>   - `dotnet run -p GreeterClient`

When everything is up and running, go ahead and see if you can get the .NET projects to speak with the node.js code from `Exercise 2`, consider the following:
## Exercise 2
Start by spinning up the code from `Lecture 08 - Remote procedure calls (gRPC)/exercises/node`. 

When everything is up and running, go ahead and see if you can get the node.js projects to speak with the .NET code from `Exercise 1`, consider the following:
- Is it possible to use the same `proto` file to generate code for various programming languages (in our case: C# and JavaScript)?

## Exercise 3
Follow [Basics tutorial | Node | gRPC](https://grpc.io/docs/languages/node/basics/) and consider the following:
- What is the difference (and pros and cons) between static and dynamic generation of Protocol Buffer code?

## Exercise 4 (**Optional**)
Create a Node or .NET app that should act as a gRPC server. Create a protobuf file, with the following two remote procedure calls
- add(AddRequest): AddResponse
- subtract(SubtractRequest): SubtractResponse)

Create the needed message types and implement simple + and - functionality

Create a Node or .NET gRPC clint application (don't choose same as above) than uses the same protebuf file. And sends add/subtract requests to your server - either through a web ui or console application.