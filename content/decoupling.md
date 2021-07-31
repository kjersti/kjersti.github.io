+++
title = "Notes on coupling"
date = 2016-04-21
+++

We all agree that too much coupling is bad, and that high cohesion is good. But what do we really mean by too much coupling?
When can we say that two elements are loosely coupled? I like this quote.

> Two elements are loosely coupled if they never show up in a diff together! (J.B.Rainsberger)

But, there are a couple of scenarious that that definition leaves out, scenarious that have bitten me a couple of times lately.
When working with a microservices architecture, it is often claimed that this brings loose coupling. However, it
is certainly possible to build highly coupled elements that do not belong in the same codebase, do not run in the
same process, even running on entirely different points in the time/space continuum! Here are a list of the kinds
of coupling that can exist between software elements (the ones I could imagine, there are probably more).

* Static coupling, or compile time coupling. This is where one element directly references another element.
* Runtime coupling. When you code to an interface, and the implementation is provided via some third party at runtime.
    This coupling is generally considered to be looser than compile time coupling, but, only if the hypothesis that
    the interface on an element changes at a different rate than the implementation of that interface holds. The
    two elements are still running in the same process.
* Protocol/contract coupling. When communicating across processes, there are no visible or explicit coupling, but
    that doesn't mean that two elements are not highly coupled. If the protocol or contract they use to communicate
    changes, they will still need to change together.

As a consequence of this, when building a microservices architecture, to prevent high coupling between your services, you
need to build your protocols in a way that is change resistent. This is the true power of REST, as defined by Fielding.
The HTTP protocol changes at a very slow rate, and if you let that represent the application state, that is, let
the protocol define how other elements are to communicate with it, you are telling clients how to use the service,
rather than assuming that they know how to talk to it.

Microservices can reduce the coupling between elements, and thus can help improve a system's maintainability, but, not unless
you take care to build protocols that can allow the service to evolve without requiring changes in the clients of
the service. The ideas given by Fielding in his dissertation can help you with that.

>  When things looks loosely coupled but in fact aren't, that is even worse! (Nat Pryce)
      