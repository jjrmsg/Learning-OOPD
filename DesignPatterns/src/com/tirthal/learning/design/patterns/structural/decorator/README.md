Decorator Pattern
==================

Purpose / Definition
------------------
* Extending an object's functionality can be done statically (at compile time) by using inheritance, however it might be necessary to extend an object's functionality dynamically (at runtime) as an object is used. Decorator pattern allows for the dynamic wrapping of objects in order to modify their existing responsibilities and behaviors.
* The decorator is used to extend or alter the functionality of objects at runtime by wrapping them in an object of decorator class. This provides flexible alternative to using inheritance to modify behavior.

Sample Code Snippet
-------------------
* Prepare beverage by adding choice of condiments in it and calculate total cost at runtime, for example if customer wants "Red Tea" with Milk, Sugar and Tea Masala. Also the design is flexible to allow you introduce more types of beverages as well as condiments in future.
* Run [AppTestDrive.java](https://github.com/tirthalpatel/Learning-OOPD/blob/master/DesignPatterns/src/com/tirthal/learning/design/patterns/structural/decorator/AppTestDrive.java) and refer the corresponding code flow.
	* RedTea.java extends Beverage.java - Red tea is concrete implementation for beverage type. 
	* TeaMasala.java, Sugar.java, Milk.java extends CondimentDecorator.java extends Beverage.java - Tea Masala, Sugar and Milk are concrete decorators implementations; which can be used to decorate (wrap) any beverage type. 

Use when
--------
* There is a need to dynamically add as well as remove responsibilities to a class, and when subclassing would be impossible due to the large number of subclasses that could result.

Important Points
----------------
* Decoration is more convenient for adding functionalities to objects instead of entire classes at runtime.
* Decorators have the same supertype as the objects they decorate.
* You can use one or more decorators to wrap an object.
* Given that decorator has the same supertype as the object it decorates, we can pass around a decorated object in place of the original (wrapped) object.
* The decorator adds its own behavior either before and/or after delegating to the object it decorates to do the rest of the job.
* Objects can be decorated at any time, so we can decorate objects dynamically at runtime with as many decorators as we like.

Hot Spot
--------
* Decoration adds functionality to objects at runtime which would make debugging system functionality harder.

More Relevant Examples
----------------------
* [java.io.InputStream](http://docs.oracle.com/javase/7/docs/api/java/io/InputStream.html), [java.io.OutputStream](http://docs.oracle.com/javase/7/docs/api/java/io/OutputStream.html), [java.io.Reader](http://docs.oracle.com/javase/7/docs/api/java/io/Reader.html) and [java.io.Writer](http://docs.oracle.com/javase/7/docs/api/java/io/Writer.html) - sub classes have a constructor taking an instance of the same type.
* [javax.servlet.http.HttpServletRequestWrapper](http://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequestWrapper.html) and [javax.servlet.http.HttpServletResponseWrapper](http://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletResponseWrapper.html)
* Setup mail systems in the company to decorate messages when it goes to an external address, for example decorate the original message with copyright and confidentiality information. This allows the message itself to remain unchanged until a runtime decision is made to wrap the message with additional information.
