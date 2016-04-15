# ASP.NET Boilerplate Architecture

What Kalkan suggests is to expand these layers into a few others, breaking the multipurpose controllers, implementing extra services and creating interfaces:

* **Presentation.** Provides an interface to the user. This is compared to the View layer, although from Kalkan's perspective, the presentation could be aimed to web, using HTML, CSS and JS, or any other option, such as Mobile applications.
* **Application.** Mediates between the Presentation and Domain Layers. It is compared to a controller, but lacks the core business logic.
* **Domain.** Also know as Core, includes the business objects of the application and its rules.
* **Infrastructure.** Provides generic technical capabilities that support higher layers, such as repositories to work with database.

From Kalkan's perspective, if a application requires a switch from Entity Framework to N-Hibernate, only the infrastructure would be affected, since this change is transparent to other layers. Or, if it requires an application to be segmented into multiple distinct platforms (such as mobile apps and a web portal), it is just a matter of implementing the Presentation layer in platform-specific ways, having the Application layer shared among them, accessed through an API.