1. The term **game object** refers to anything in the game world that updates, draws, or both updates and draws.

2. A common type of game object is one that's both updated every frame during the "update game world" phase of the loop and drawn every frame during the "generate outputs" phase.

3. The term **static object** is for game objects that draw but don't update. These objects are visible to the player but never need to update.

4. **Trigger** is the game object that updates but doesn't draw to the screen.

5. **Game Object Models**

   1. Game Objects as a Class Hierarchy:

      Declare game objects in a standard object-oriented class hierarchy, which is sometimes called a **monolithic class hierarchy** because all game objects inherit from one base class.

      Problem:

      redundant codes that some objects don't need.

      It may cause **Diamond Inheritance** which can cause issues (the subclass might inherit multiple versions of a virtual function).

   2. Game Objects with Components:

      In component-based game object model, there is a game object class, but there are no subclasses of the game object. Instead, the game object class has-a collection of component objects that implement needed functionality.

      One advantage is that it's easier to add functionality only to the specific game objects that require it.

      One disadvantage of pure component systems is that dependencies between components in the same game object are not clear. Depending on the implementation, the querying can become a noticeable performance bottleneck.

   3. Game Objects as a Hierarchy with Components

       It is a hybrid of the monolithic hierarchy and the component object models. There is a base Actor class with a handful of virtual functions, but each actor also has a vector of components.
   
      Actor class needs access to the *Game* class for several reasons, including to create additional actor. One approach is to make the game object a **singleton**. But sometimes game needs multiple instances of the class. So instead of using singleton, we use an approach called **dependency injection**. In this approach, the actor constructor receives a pointer to the Game class.
   
   4. Other Approaches
   
      Use interface classes to declare the different possible functionalities.
   
      Extend the component model a step further and eliminate the containing game object entirely.
   
      Define Objects by their properties.
   
      ...
   
6. 