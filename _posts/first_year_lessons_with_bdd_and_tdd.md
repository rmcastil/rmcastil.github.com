I used to work for a firm where we didn't have tests in place. The software I worked on was created by a team of developers and at one point had a QA department. By the time it I joined the organization I was the sole developer. It was like a time bomb. I would make changes and hope for the best that nothing would blow up. I was essentially creating features on a project where it was originally built by a team of people and had an actual QA department. Without them there was no confidence that changes being made were actually breaking the system or not.

1. Having tests allow for confidence in changes - If your test coverage is good (ie - 1:1 unit tests with sprinkled in integration tests) you'll have a level of confidence that allow you to make changes worry free

5. TDD and BDD can be a literal productivity boost (you no longer get in your own way). This is the 'driven' part in TDD or BDD

There is a more advanced lesson here and that is if you truly stick to the red, green, refactor pattern.

4. Quickly alternating between Red, Green, Refactor will lead to emergence in your code

So here I was moving along, testing and loving life. But then a pain started to creep up. My tests were taking forever, I was running something like guard or autotest to run my entire test suite and it was starting to crawl. It was like I was compiling code again (http://xkcd.com/303/).

2. Pain with testing usually tells you something is bad with your code (or tests). - http://vimeo.com/15007792 (Michael Feathers on good testing and design)

3. In the case of testing rails, tests are usually slow because rspec and cucumber load rails. You're too tightly coupled with your framework! Can show alternatives to spec helper here.

Worse yet, when I would make a change half the suite would break and I would have to spend hours getting the entire test suite green again. Was having the 'binary test suite' problem (http://pyvideo.org/video/631/fast-test-slow-test) (http://pyvideo.org/video/631/fast-test-slow-test). Too many dependencies. Far from the ideal test suite in which you make a change, one thing fails, and you get immediate feedback on what is wrong.

6. I do BDD per feature, get things red, then drill down and spend 90% of my time doing isolated unit tests (no loading of rails and doing plain old ruby objects)

7. Testing and design are highly coupled

8. when you get better at testing you get better at refactoring old code

9. You don't always have to test...


Additional Notes
----

Is TDD the best approach?

- what situations merit versus don't?
  * maybe startups don't need TDD
  * the alternative is always putting in tests when refactoring

- how can we come up with a good answer for this?

- can we explore old repo history and time between commits to see how easy changes came?

- Can we track how often a class has been changed? Frequency. How often has the corresponding test been changed?

I am personally guilty of Big design up front. I think too much and it paralizes me. That's why TDD and a short feedback loop work best for me.

---

Use git commits to find classes are touched frequently and changed. Possibly a sign that those classes should be unit tested and possibly extracted for more classes.

---

experiencing major pain now just trying to test coffeescript
