
      The kinds of coupling: - compile time coupling - run time coupling, in the same process - build time coupling - contract/protocol
      coupling - shared libraries (is this coupling?) If changes to a library forces you to change the component, then yes.
      Specifically, I have been thinking about this in terms of microservices. Because I get a bit tired of hearing people
      throwing around microservices like a silver bullet to automatically make things loosely coupled. It seems to me that
      they are missing the point about coupling. What does it even mean that a system is highly coupled? A definition that
      makes sense to me is that somethings are highly coupled if they change together. If, to add a feature, you need to
      change this piece over here, and that other piece over there, then those pieces are highly coupled, for that change.
      This means that you cannot put a simple metric on the coupledness of a system, because it depends on what kinds of
      changes are going to happen to it. Or, maybe you can, if it is possible to determine that any change would require
      changes to all the other pieces, but I have trouble imagining such a system. So, to reduce The other day, Kent Beck
      posted this 
      
      https://www.quora.com/Is-it-true-that-whenever-I-increase-cohesion-of-design-coupling-in-the-design-would-automatically-decrease/answer/Kent-Beck?prompt_topic_bio=1
      
      where he argues that increasing cohesion, might reduce coupling, but not always, and that it will never increase coupling,
      ergo, increasing cohesion is often times a good choice. High cohesion - easier to find where to change, low coupling
      - safer to do change. (Corey Hanes) The most difficult coupling is the coupling that is implicit, and not specific
      in ant place in the code. (Nat Pryce) High coupling and hich cohesion is perfectly fine, at a certain level. Like for
      one class, the methods in that class are highly coupled, and that is part of what makes it cohesive. But, not just
      that. You can have highly coupled methods, but if they are doing very differently, than that is not highly cohesive.
      Highly coupled systems -> to change something / a feature, forces me to also make a change somewhere else. Coupling
      can happen without direct references! (Jim Weirich) The coupling can sometimes be only in the heads of people, you
      have to remember that the connections are there. Like an API used by someone, that you might not know of. Coupling
      are most often necessary, but, how do we do coupling? Is it explicit, is there a protocol, an agreed contract, that
      is written down somewhere. This is why REST, actual REST, is powerful. Force all coupling to justify itself! (J.B.Rainsberger)
      But, what does loose coupling mean? "two elements are loosely coupled if they never show up in the same diff!" Strength,
      locality, degree. Because the problem with coupling is when there is a need to change. If we know that something will
      not change, maybe we can increase coupling. Loose coupling - runtime better than static. Late binding. "When things
      looks loosely coupled but in fact aren't, that is even worse'" 
      
      (JBR) Visualising: When a file is created, and when
      it was last edited. Visualize this. Michael feathers done it. Dependency injecting is a specific form of decoupling.
      Because you can change the implementation of the dependency without changing the dependant component. Note, this does
      not mean NO coupling, but loose(r) coupling.
