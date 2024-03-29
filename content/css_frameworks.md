+++
title = "What's that about CSS frameworks?"
date = 2016-03-04
+++

I have been building stuff for the web for more than ten years, but being mostly a backend developer, there are still loads to learn when getting to grips with all the stuff happening frontend. My current mission is to learn all I can about current practices in CSS, HTML and javascript technologies. And, because I have a great need for structure, and I like analysis, and am currently working on an application built on a death march, I am very interested in learning more about how to keep your CSS from turning into an overgrown jungle. So, the topic of the day: CSS frameworks/architectures.


Why could this be useful? To help people get up and running more quickly, and to preserve consistency across a project with multiple developers, across time and space.

## SMACSS

 [SMACSS](https://smacss.com/book/) is a collection of guidelines for structuring and naming your CSS rules. There are five kinds of rules: base rules, layout rules, module rules, state rules and theme rules. They are identified using a what reminds me of hungarian notation, with a prefix to indicate which kind of rule it is. The base rules will normally use tag selectors, possibly in combination with pseudo selectors, the layout rules can use id selectors, or class selectors prefixed with l_. The module rules are meant to be your most common type of rule. Module rules should only use class selectors, unlike the base and layout rules. The classes does not use any prefix. Using child selectors in addition to the classes is fine, if the child elements are semantic, whatever that means, certainly not span or div. The state rules are meant to be variations on module elements, indicating things like is-error, is-active, etc. The is-prefix is suggested. It is perfectly fine to use these classes as CSS rule selectors as well as JS hooks.The theme rules seems to apply only for sites where you need the possibility of giving a single site multiple themes. Theme rules should be defined in a separate file, to make it easy to switch colors, fonts, and the like.

## BEM

  [BEM](https://en.bem.info/) stands for block, element, modifier, and represents the basis for how syle rules are named according to this framework. The BEM framework contains lots of stuff I haven't looked into, I have merely looked at the CSS style guide part of it. It is intended for sites that are built as compositions of modules. The idea is that naming of styles rules should be so flexible that modules can be moved around freely, and still behave nicely. This means that there are only class selectors used. The classes are named by BLOCK__ELEMENT_MODIFIER.

## Mix and match?

  As for most things, I don't think there is one perfect framework to use. I do think that having a shared style guide for CSS in a team of developers is very useful. I like the approach of using classes extensively, rather than coupling the HTML structure to the CSS, since they are both semantic, but not necessarily the same semantic. Considering non-standard browsers, like screen readers for instance, it is more apparent to me that the semantic HTML is about the content, but the semantic CSS is about presentation. Not the same at all, necessarily. Secondly, I like having separate classes for JS hooks. All of this does make for lots of classes in your HTML, but I am fine with that. Although, it does make sense to share the state rules from SMACSS between JS and CSS. So, I am of two minds here it seems.


  I like the simplicity of the BEM model, where the same rules for specifying selectors apply across all parts of your CSS. Although the structure of base rules, layout rules and module rules makes sense. Having your base rules using element selector seems very sensible, I can't imagine that defining all of those baseline properties using BEM naming scheeme adds value. Also, keeping the majority of your styling, other than the base rules, on the same CSS specificity seems to be a good idea, just because it seems easier to reason about, and to debug.


  All of my opinions here are of course based on little experience building CSS myself, I have usually been presented with an existing CSS framework, either Bootstrap, or some other framework designed by someone else. So, I will likely change my mind after gaining some actual experience.

## CSS preprocessors?

  Can CSS preprocessors help us out? And if so, for what? This will have to be my next topic.

> Anyone can rearrange pre-built “lego blocks”; it turns out that no one can perform CSS-alchemy.

## Things I read while writing this

* [http://nicolasgallagher.com/about-html-semantics-front-end-architecture](http://nicolasgallagher.com/about-html-semantics-front-end-architecture/)
* [https://www.smashingmagazine.com/2008/05/improving-code-readability-with-css-styleguides](https://www.smashingmagazine.com/2008/05/improving-code-readability-with-css-styleguides/)    
* [https://smacss.com/book](https://smacss.com/book)
* [https://en.bem.info](https://en.bem.info/)


  And then there is [this.](https://css-tricks.com/the-debate-around-do-we-even-need-css-anymore/)


