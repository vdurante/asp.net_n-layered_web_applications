# N-Layer Architecture

  A N-Layer Architecture is an architectural style.
  
  ## What is an Architectural Style?
  
  An architectural style is a set of principles. Such principles intend to improve partitioning and promote design reuse by providing solutions to frequently recurring problems. It also provides a common language that abstracts the understanding of the problem away from the implementation, facilitating a higher level conversation.
  
  A great example for the Web is the Model-View-Controller architecture. It doesn't matter the programming language of the implementation, because the principles are the same.
  
  
![MVC ](./resources/img/figure2.png)

The simple graph presented above is enough to represent the basic idea of the system's architecture, facilitating communication and understanding.

Applying the design principle of replaceability, if a company decides to switch database engine, it is just a matter of switching the Model layer, instead of rewriting the whole system. Besides, if the implementation follows the architectural guidelines, other 2 important principles come into play: principle of least knowledge and abstraction, so that the controller and view should not be highly affected by a change in the Model layer.

## Where MVC Falls Short

In Web development, MVC is the most famous and widely used architecture in the present days. It is adopted due to its simplicity and suitability, not only on the Web scenario.

However, the MVC architecture, as in ASP.NET MVC, falls short in some aspects:

* **Multipurpose controllers.** Controllers are the core of the application, dealing with multiple responsibilities. Not only it implements the business logic, it also deals with manipulation and validation of data being transfered between the model and the view. This fact conflicts with the single responsibility principle, over sizing the controller.
* **Distributed services.** If the application requires an API (implying multiple ways of presenting data), a whole new controller must be implemented, or the existing one must be extended (adding another purpose), also over sizing the controller.
* **Lack of an ORM interface.** The controller access the Model's Object-Relational Mapper directly. A change in the ORM implies a reimplementation of the controller, breaking the abstraction and least knowledge principles.
* **Background and real time services.** Require implementation inside the controller, over sizing it once again.

The points presented above don't imply that choosing MVC is a bad choice. On the contrary, it is an amazing choice. but not the best when the application increases in complexity. What is being proposed is an improvement in the current MVC architecture: the N-Layer architecture.



## The N-Layer Architecture

N-Layer data applications are data applications that are separated into multiple layers, which clearly separate processing into discrete layers. This definition seems a little bit vague, but it is vague enough to fit MVC into it. Therefore, MVC is also a N-Layer architecture.

What is being proposed here is to extend the MVC architecture, as a N-Layer architecture, to fit the requirements of the application. Thinking about the shortfalls presented above, Halil İbrahim Kalkan, author of the [ASP.NET Boilerplate](http://aspnetboilerplate.com/) (ABP) framework, suggests some changes to the default ASP.NET MVC framework, adding some extra layers to it, and modifying the purpose of the existing ones.

Originally, the MVC layers have this purpose:

* **Model.** Layer that implements the logic for the application's data domain.
* **Controller.** Layer that has components that handle user interaction, working with the model and selecting a View to be displayed.
* **View.** Layer that displays the application's user interface (UI).

What Kalkan suggests is to expand these layers into a few others, breaking the multipurpose controllers, implementing extra services and creating interfaces:

* **Presentation.** Provides an interface to the user. This is compared to the View layer, although from Kalkan's perspective, the presentation could be aimed to web, using HTML, CSS and JS, or any other option, such as Mobile applications.
* **Application.** Mediates between the Presentation and Domain Layers. It is compared to a controller, but lacks the core business logic.
* **Domain.** Also know as Core, includes the business objects of the application and its rules.
* **Infrastructure.** Provides generic technical capabilities that support higher layers, such as repositories to work with database.

From Kalkan's perspective, if a application requires a switch from Entity Framework to N-Hibernate, only the infrastructure would be affected, since this change is transparent to other layers. Or, if it requires an application to be segmented into multiple distinct platforms (such as mobile apps and a web portal), it is just a matter of implementing the Presentation layer in platform-specific ways, having the Application layer shared among them, accessed through an API.





