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
> we need to change the port of the client in the greeter_client.js file. then we need to adjust the package imported from the protos file.
- Is it possible to use the same `proto` file to generate code for various programming languages (in our case: C# and JavaScript)?
> Yes, it is possible to use the same .proto file to generate code for various programming languages, including C# and JavaScript.

## Exercise 3
Follow [Basics tutorial | Node | gRPC](https://grpc.io/docs/languages/node/basics/) and consider the following:
after following the tutorial we been able to create a server and a client with the posibility to ping/pong an echo message.  Run the projects by running the we recieve the following output:
```bash
Visiting point 41.2950425, -74.1077389
Visiting point 40.8031728, -74.8645385
Visiting point 41.21278, -74.0173578
Visiting point 41.8858923, -74.615679
Visiting point 41.7951888, -74.8484944
Visiting point 41.9018117, -74.9142781
Visiting point 40.8122808, -74.3999179
Visiting point 41.0395868, -74.4972325
Visiting point 41.8811433, -74.1718005
Visiting point 40.5957808, -74.3255336
Finished trip with 10 points
Passed 7 features
Travelled 688936 meters
It took 10 seconds
Sending message "First message" at 0, 0
Sending message "Second message" at 0, 1
Sending message "Third message" at 1, 0
Sending message "Fourth message" at 0,
```

- What is the difference (and pros and cons) between static and dynamic generation of Protocol Buffer code?
### Static Generation:
#### Pros:
Generated code is precompiled during the build process, leading to better performance.
Provides compile-time type safety and validation, catching errors early in the development process.
Integration with IDEs and development tools for auto-completion, syntax highlighting, and refactoring support.
#### Cons:
Requires regeneration of code whenever the .proto file is modified, which can slow down development iteration.
Increases the size of the compiled binary due to inclusion of generated code.
May result in longer build times, especially for large projects with extensive Protocol Buffer definitions.
### Dynamic Generation:
#### Pros:
Code is generated at runtime, allowing for flexibility and adaptation to changes in the .proto file without the need to recompile.
Reduced build times during development, as code generation is deferred until runtime.
Well-suited for scenarios where the Protocol Buffer schema is dynamic or frequently changing.
#### Cons:
Performance overhead due to dynamic code generation and interpretation at runtime.
Lack of compile-time type safety and validation, potentially leading to runtime errors if the .proto file is modified incorrectly.
Limited support for IDE features such as auto-completion and syntax checking, as the code is generated dynamically.

## Exercise 4 (**Optional**)
Create a Node or .NET app that should act as a gRPC server. Create a protobuf file, with the following two remote procedure calls
- add(AddRequest): AddResponse
- subtract(SubtractRequest): SubtractResponse)

Create the needed message types and implement simple + and - functionality

Create a Node or .NET gRPC clint application (don't choose same as above) than uses the same protebuf file. And sends add/subtract requests to your server - either through a web ui or console application.


## Questions 

- What is the differences between gRPC and REST?
    gRPC uses HTTP/2 for transport, whereas REST typically uses HTTP/1.1.
    gRPC uses protocol buffers for serialization, while REST commonly uses JSON.
    gRPC supports bidirectional streaming, while REST typically follows a request-response model.
    gRPC generates client libraries automatically, while REST relies on manually crafted clients.
- How is protobuf used to serialize data in gRPC services?
    Protocol Buffers (protobuf) are used in gRPC to serialize structured data efficiently. Protobuf defines a language-agnostic interface for serializing data, which helps in communication between different systems in a compact and efficient manner.
- What are the pros and cons of using gRPC?
    Pros:
        Efficient binary serialization with protobuf.
        Support for bidirectional streaming.
        Automatic generation of client libraries.
    Cons:
        Requires HTTP/2 support, which might not be available in all environments.
        Can be more complex to set up compared to REST.
        Limited browser support due to HTTP/2 requirements.
- Consider how to handle changes in the gRPC protocol?
    Use protocol buffer versioning to maintain backward compatibility.
    Consider using gRPC's support for evolving APIs through backward-compatible changes.
    Communicate changes effectively and provide migration guides when updating the API.
- Where would you prefer using gRPC over Rest or GraphQL?
    Need high-performance, low-latency communication.
    Working in a microservices architecture.
    Require bidirectional streaming or efficient binary serialization.
- What dependecies are needed when implementing a gRPC service in ASP.NET Core?
    Grpc.AspNetCore for gRPC server implementation.
    Google.Protobuf for Protocol Buffers support.
    Optionally, Grpc.Tools for code generation.
- What dependencies are needed when implementing a gRPC client i ASP.NET Core?
    $Grpc.Net.Client$ for gRPC client implementation.
    $Google.Protobuf$ for Protocol Buffers support.
    Optionally, $Grpc.Tools$ for code generation.
