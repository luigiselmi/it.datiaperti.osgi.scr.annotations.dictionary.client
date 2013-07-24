OSGi SCR Dictionary Client
============================================

This is an example implemetation of a OSGi bundle that provides a client for the service available in the project

[OSGi SCR Annotations Dictionary Service](https://github.com/luigiselmi/it.datiaperti.osgi.scr.annotations.dictionary.service)

To try it you have to clone the project, compile with

    mvn install

then install the bundle jar file into a OSGi container like Apache Felix. This client acts as an interface between 
the user and the service. The user sends the guess word to the client writing on the Felix shell to which the client 
is listening and then the client pass the guess word to the service. If the word is one of those known by the service 
it will send back a response message "Correct" otherwise it sends "Incorrect". A blank line stops the client in passing 
words. To restore the client it must be deactiveted and then activeted again.

This component uses Apache Service Component Runtime to configure the wiring between it and other components. The wiring 
between a component (client) that uses services provided by another component is implemeted following the Dependency Injection 
pattern (constructor injection). The service is injected in the client constructor through the OSGi environment. 
The referenced service is declared as Java Annotations in the client component source code. The same client component has been 
implemented using SCR Declarative Services in the [OSGi SCR Dictionary Client](https://github.com/luigiselmi/it.datiaperti.osgi.scr.xml.dictionary.client) 
project.
