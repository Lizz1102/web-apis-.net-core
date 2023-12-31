# WebAPIs: .NET Core(.Net6, .NET7)
- Building Web API projects with C# and exploring new features and incoming changes of .NET 6, .NET 7, and .NET 8.
- How to upgrade .NET Core 5 APIs to later versions of .NET.
- Revisiting some advanced and fundamental concepts of .NET Core Web APIs.
- API Design - patterns, best practices, and standards.
- This repo is my personal reference and notes for building and designing performant and scalable APIs.


## Pagination


![image](https://github.com/Lizz1102/WebAPIsWith.NetCore/assets/15815335/c72d6cd1-e0b8-4524-a89d-ba4f87dec9b5)


## Filtering Items Based on Minimum and/or Maximum Price


![image](https://github.com/Lizz1102/WebAPIsWith.NetCore/assets/15815335/528cf6f6-9843-4872-b0bb-58cd67188a5c)
 

## API Design: Guidelines and Best Practices 


**Architecture/Design Documents**
- [Microsoft REST API Guidelines](https://github.com/Microsoft/api-guidelines/blob/master/Guidelines.md)
- [RESTful web API design](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design)
- [Web API implementation](https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-implementation)


  **API Reference**
  - [Stripe](https://stripe.com/docs/api)
  - [Twitter](https://developer.twitter.com/en/docs/api-reference-index)
  - [Swagger Petstore Demo](https://petstore.swagger.io/)
## Notes 


Keeping the notes/resources for myself, or anyone who wants to revisit/delve into related concepts.


<details>
  <summary>HTTP</summary>
  <p>
    &emsp;&emsp;- <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Status" target="_blank">HTTP response status codes</a>
  </p>

  <p>
    &emsp;&emsp;- <a href="https://www.debugbear.com/blog/http3-quic-protocol-guide" target="_blank">A Comprehensive Guide To HTTP/3 and QUIC + HTTP/1.1 vs HTTP/2 vs HTTP/3</a>
  </p>

  <p>
    &emsp;&emsp;- <a href="https://datatracker.ietf.org/doc/html/rfc2616" target="_blank">HTTP/1.1 Original Specification</a>
  </p>
</details>


<details>
  <summary>REST</summary>

  <p>&emsp;&emsp;- REST is a design concept.</p>
  
  <p>&emsp;&emsp;- Rest builds on the foundation of HTTP, utilizing its methods, URIs, status codes, and other features to create a scalable and standardized architecture for building web APIs. The principles of REST are designed to align with the capabilities and characteristics of the HTTP protocol.</p>

   <p>&emsp;&emsp;- Uses URIs to access resources.</p>

   <p>&emsp;&emsp;- Uses HTTP verbs for operations.</p>
   <p>
    &emsp;&emsp;- <a href="https://restfulapi.net/rest-architectural-constraints/">REST Architectural Constraints</a>
  </p>
</details>


<details>
<summary>Verbs</summary>

<p>&emsp;&emsp;- HTTP methods, also known as verbs, define the actions that can be performed on resources.</p>
<p>&emsp;&emsp;- <strong>GET:</strong> Uses URIs to retrieve a resource or a collection of resources.</p>
<p>&emsp;&emsp;- <strong>POST:</strong> Uses URIs to create a new resource.</p>
<p>&emsp;&emsp;- <strong>PUT or PATCH:</strong> Uses URIs to update an existing resource.</p>
<p>&emsp;&emsp;- <strong>DELETE:</strong> Uses URIs to remove a resource.</p>
<p>&emsp;&emsp;- These verbs align with the CRUD (Create, Read, Update, Delete) operations commonly associated with data manipulation.</p>

</details>


<details>
<summary>Nouns</summary>

<p>&emsp;&emsp;- In RESTful design, nouns typically represent resources. Resources are the entities or objects that your API exposes.</p>
<p>&emsp;&emsp;- For example, in a blog application, we might have resources such as "posts," "users," or "comments."</p>
<p>&emsp;&emsp;- Resources are identified by URLs (Uniform Resource Locators), and they are the primary entities that the API deals with.</p>

</details>


<details>
      <summary>Model Binding</summary>
      <p>
           TODO: Add Content 1 Content 1 Content 1 Content 1 Content 1
      </p>
</details>


<details>
      <summary>Model Validation</summary>
      <p>
           TODO: Add Content Add notes
      </p>
</details>


<details>
  <summary>Advanced Data Retrieval</summary>
  
  Features implemented:
  
  - **Pagination**
  - **Filtering**
  - **Searching items**
  - **Sorting Items**
  - **Advanced Search**  
</details>


  
## Observations: Incoming Changes in .NET 6


There are no radical changes in .NET 6 structurally, most changes are focused on the simplicity and speed of building the code.
However, knowing the incoming changes can be beneficial if we need to upgrade .NET 5 Core projects to .NET 6.


- [Migrate from ASP.NET Core 5.0 to 6.0](https://learn.microsoft.com/en-us/aspnet/core/migration/50-to-60?view=aspnetcore-7.0&tabs=visual-studio)
- [Why .NET 6 promotes better programming practices](https://www.youtube.com/watch?v=aSNqqZqYTk4&ab_channel=IAmTimCorey)


Incoming changes I noticed during this project are: 

<details>
      <summary>No Startup.cs</summary>
      <p>
      &emsp;&emsp;- In .NET 6, Microsoft has unified Startup.cs and Program.cs into one Program.cs. Now registering middleware, services and adding DbContext etc can be done in the Program.cs file. 
      </p>
      <p>
      &emsp;&emsp;- <a href="https://andrewlock.net/exploring-dotnet-6-part-12-upgrading-a-dotnet-5-startup-based-app-to-dotnet-6/">Upgrading a .NET 5 "Startup-based" app to .NET 6</a>
      </p>
      <p>
      &emsp;&emsp;- <a href="https://www.youtube.com/watch?v=vdhFw1VSowg&ab_channel=IAmTimCorey">Handling Program.cs Without Startup.cs</a>
      </p>
      
</details>


<details>
      <summary>HTTP/3 Support</summary>
      <p>
      &emsp;&emsp;- .NET 6 includes preview support for HTTP/3. HTTP/3 solves some existing functional and performance challenges by using a new underlying connection protocol called QUIC.QUIC establishes connections more quickly, and connections are independent of the IP address, allowing mobile clients to roam between Wi-fi and cellular networks. 
      </p>
</details>


<details>
  <summary>Minimal APIs</summary>
  <p>
    &emsp;&emsp;- ASP.NET 6 introduces Minimal APIs, offering a lightweight approach to building APIs with reduced boilerplate code. Unlike the traditional ASP.NET Core Web API template, if the <strong>Use controllers</strong> checkbox is unchecked during project creation, no controllers are generated. This feature caters to developers aiming to minimize unnecessary components.
  </p>
  
  <p>
    &emsp;&emsp;- Minimal APIs simplify the process of developing smaller, faster microservices. In scenarios where a microservices or serverless architecture demands small, focused APIs, minimal APIs eliminate unnecessary overhead. They are particularly suitable for APIs with a single, well-defined purpose, providing an efficient way to define such APIs.
  </p>

  <p>
    &emsp;&emsp;- Consider leveraging minimal APIs for quick prototyping, testing, or the creation of temporary APIs to validate ideas. Their lightweight nature makes them well-suited for scenarios where a rapid development cycle and minimal setup are essential.
  </p>
</details>


<details>
      <summary>Title</summary>
      <p>
           Content 1 Content 1 Content 1 Content 1 Content 1
      </p>
</details>



## .NET 8 


- [What's new in .NET 8](https://learn.microsoft.com/en-us/dotnet/core/whats-new/dotnet-8) 
- Things we should look out for when upgrading - [.NET 8 and C# 12 Launch - What is New, What is Improved, and What is Supported](https://www.youtube.com/watch?v=mT70wtkE7DI&ab_channel=IAmTimCorey)
  


## Future Improvements: Improvements + Tools and Concepts I Need to Know More


This section contains information about future improvements, additional tools, and concepts I need to explore further.


Note to self: Avoid analysis paralysis. Choose one architecture and create rapidly. However, many times you'll start working in a team and need to understand their standards, practices, and architecture and work from there. 


In summary, continually enhance your skills by exploring various architectures and tools through small projects. This approach ensures that when working with a team, you can swiftly adapt to their standards and practices, facilitating quick decision-making for your new projects. Remember to avoid analysis paralysis, choose an architecture, and iterate rapidly.


- Dapper
- R&D and decide - [Clean Architecture + CQRS + DDD](https://github.com/kgrzybek/sample-dotnet-core-cqrs-api)
- [TDD vs BDD vs DDD: Which One Should You Choose?](https://mobilelive.medium.com/tdd-vs-bdd-vs-ddd-which-one-should-you-choose-e562e313f955#:~:text=Here%20are%20the%20key%20differences,uses%20a%20domain%2Dspecific%20language.)
- [CQRS with non-generic Repositories and Units of Work](https://radekmaziarka.pl/2017/08/19/cqrs-first-step-split-to-commands-and-queries/)
- Repository pattern(Abstract EF DbContext with Repository) 
- API Controller -> Service -> Repository
- Clean/onion architecture - [Reference project 1](https://github.com/iammukeshm/CleanArchitecture.WebApi) [Reference project 2](https://github.com/juldhais/CleanArchitecture) [Reference project 3](https://github.com/ardalis/CleanArchitecture) [Reference project 4](https://github.com/jasontaylordev/CleanArchitecture)
- https://abp.io/- 
- REST and small Onion, with a thin controller
- Thin controllers are the way to go. You want as little code in the controller as possible. It makes it easier to have tests that cover all your code
- DTO - In a monolithic setup to learn minimum best practices I would set up the presentation layer, domain layer, and data access layer, using DTO to avoid hard coupling between the presentation layer and data access layer

  
## TODOs


- [ ] Advanced data retrieval
- [ ] Versioning APIs(Built-in support in Core)
- [ ] Securing APIs(Enforcing HTTPS, token-based Authorization/Authentication)
- [ ] ASP.NET Core Security
- [ ] API Design(Clean Architecture, REST+ Small Onion etc) 
- [ ] Refactor to implement loose coupling and maintainability(SOLID, DRY, IoC, Extract interfaces, etc)
- [ ] Scalability
- [ ] Add Endpoint Specifications  
- [ ] Add screenshots/demos of projects
- [ ] Make Testable
- [ ] Make Scalable
- [ ] Deploy?
- [ ] Replace in-memory database with RDBMS
- [ ] Present project - agenda? target audience?
- [x] Add Future Improvements Section - [Link to Future Improvements Section](#future-improvements-improvements--tools-and-concepts-i-need-to-know-more) 


## Credits


- [Christian Wenz: Advanced Web APIs with ASP.NET Core in .NET 6](https://www.linkedin.com/learning/advanced-web-apis-with-asp-dot-net-core-in-dot-net-6/filtering-items?contextUrn=urn%3Ali%3AlearningCollection%3A7127800062000201728)
- [Christian Wenz: Building Web APIs with ASP.NET Core in .NET](https://www.linkedin.com/learning/building-web-apis-with-asp-dot-net-core-in-dot-net/hello-world-api-style-19429584?contextUrn=urn%3Ali%3AlearningCollection%3A7127800062000201728)
- [Create web APIs with ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/web-api/?view=aspnetcore-7.0)https://learn.microsoft.com/en-us/aspnet/core/web-api/?view=aspnetcore-7.0)
- [APIs with ASP.NET Core](https://dotnet.microsoft.com/en-us/apps/aspnet/apis)
