# N-Layered Architecture

  A N-Layered Architecture is an architectural style.
  
  ## What is an Architectural Style?
  
  An architectural style is a set of principles. Such principles intend to improve partitioning and promote design reuse by providing solutions to frequently recurring problems. It also provides a common language that abstracts the understanding of the problem away from the implementation, facilitating a higher level conversation.
  
  A great example for the Web is the Model-View-Controller architecture. It doesn't matter the programming language of the implementation, because the principles are the same.
  
  
![MVC ](./resources/img/figure2.png)

The simple graph presented above is enough to represent the basic idea of the system's architecture, facilitating communication and understanding.

Applying the design principle of replaceability, if a company decides to switch database engine, it is just a matter of switching the Model layer, instead of rewriting the whole system. Besides, if the implementation follows the architectural guideliness, other 3 principles come into play: Principle of Least Knowledge, abstraction and 