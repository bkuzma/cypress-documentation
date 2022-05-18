---
title: Who are you testing for?
---

When testing components, you should first realize that you have TWO kinds users:
End Users and Developers.

A good component test covers End User concerns (finding and interacting with
elements based on accessible queries and human-readable text) as well as
Developer concerns (What is the component's signature? Does it have any "output"
when used in conjunction with other components?).

### Developer concerns

Developers care about the API of the component. They want to make sure that if
they exercise the component in a particular way, with certain props, that it'll
behave the way they expect it to. A test written for a developer provides
coverage over the component's usage and signature.

Component testing written with developers in mind heavily covers props, events
(Vue), and children/slots (React + Vue).

### End-user concerns

Users think the way a non-technical product owner might.

They use their eyes or, more accessibly, assistive devices such as screen
readers.

Is the component supposed to tell you what's in your cart? Should you be able to
enter a text value into a numerical `Stepper` component like it was an input? Is
that `Stepper` component supposed to increment and decrement when you click the
correct buttons?

People are often more comfortable putting on their End-user hat when writing
End-to-end tests because they're not able to access any application internals.
We encourage you to carry over that kind of thinking when writing your component
tests.

By doing so, you'll gain the same kind of coverage and benefits as you would in
an end-to-end test, without the penalties of speed, setup, and complexity.

### Your test has an audience

People often assign labels like "integration testing" or "unit testing" when
testing components in order to try and describe differences in detail and
concern that a test may have.

<!-- Meh: For example, should I test to make sure that calling `setProps` twice triggers a particular component's lifecycle event? (Answer: Not unless you have a very good reason. That's an implementation detail.) -->

It may be easier, instead, to think about the audience of the test, their goals,
and their motivations.

Always remember, a test exists to prove (to someone) that code works "as
expected". Different user types will have different expectations.