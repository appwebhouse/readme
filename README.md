## Code style/performance
Your code should comply with [Ruby style guide](https://github.com/bbatsov/ruby-style-guide).
Before committing your code you should always check it, at least, with [Rubocop](https://github.com/bbatsov/rubocop). It's always a good idea to look for vulnerabilities and possible ways to get your queries a bit faster. Check your code with [Brakeman](https://github.com/presidentbeef/brakeman), [Bullet](https://github.com/flyerhzm/bullet) and [lol_dba](https://github.com/plentz/lol_dba). If you have the time, check with [Fasterer](https://github.com/DamirSvrtan/fasterer), maybe your code can get a bit faster.

If needed use [Overcommit](https://github.com/brigade/overcommit), [Hound](https://houndci.com/) or [Pronto](https://github.com/mmozuras/pronto).

All stage(production, development, test) specific information should go to a dedicated .env file.

## General guides

1. Your code should be readable. If you don't know what the code does after reading it, it's a bad sign.
1. Always write tests. Tests are a great help when developing and **needed** in refactoring. **Never** push your code to the repository without tests because "it's such a minor change".
1. Comment your code - writing an additional couple of lines is not a big cost but can be a real help to other developers (and maybe even future you). [http://yardoc.org/](http://yardoc.org/)
1. Boy scout rule. "Always leave the campground cleaner than you found it.". When you modifying something, try to clean up a bit.
1. When you find a bug (not if :wink:) always create an issue and inform your supervisor. Emails or conversations can get lost, issues are always there. Knowing there's a piece of faulty code and not reporting it will eventually bite you in the ass.
1. As a developer, it's **your** responsibility (not your supervisor's) to take care of your code. If you believe that a piece of code needs refactoring, make your supervisor understand it and make time for it. Technical debt always comes back.
1. Help each other. Everybody eventually has a problem or gets "writer's block". Taking the time to listen to your fellow developer can, itself, be of great help to them ([rubber duck debugging](https://en.wikipedia.org/wiki/Rubber_duck_debugging)).
1. Talking about your implementation within a team, especially, if your facing a hard task, can spawn new ideas and ways to tackle the issue.
1. If the procedure you're implementing is hard to understand, don't hesitate to write additional documentation.
1. Remember the principles of software development: [DRY](https://en.wikipedia.org/wiki/Don't_repeat_yourself), [KISS](https://en.wikipedia.org/wiki/KISS_principle), [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) and [YAGNI](https://en.wikipedia.org/wiki/You_aren't_gonna_need_it).
1. [Ballmer Peak](https://xkcd.com/323/)
1. Learn how to say "no". Don't take a task or your supervisor's word for granted. Maybe the feature that somebody's trying to push is not needed or even stupid.
1. Learn how to say "yes".
1. If you believe that a change to the workflow can be beneficial, speak up!
1. You are human - you make mistakes. Get over it. When you make a mistake, try to get the best of it and learn something.
1. Spread your knowledge. Write a blog post, create a howto or even conduct a workshop.
1. "Measure twice, cut once."
  It's always better to think (or write down) things before doing actual development.
1. Writing an API? Comply with [json:api](http://jsonapi.org/)
1. Don't change a task's acceptance criteria that you're working on, and don't let the Product Owner (supervisor) change it - new or more things to do should go into a new task.
1. Keep up to date! New versions of your favorite framework and language bring new features!
1. When creating public facing API, write documentation - nobody will use an API that's not documented.

## Testing guide

1. Write unit tests

     Treat unit tests as a form of most basic documentation. A developer that is joining your code base, should understand how your classes and methods work.

1. Write integration tests

      Your tests should check not only if the the objects themselves work, it should check if the business rules that apply to your code are met.

1. [Kill the mutants](https://troessner.svbtle.com/kill-all-the-mutants-a-deep-dive-into-mutation-testing-and-how-the-mutant-gem-works) if you have the time.

## Code review

Remember that code review is not considered QA. Code review should be understood as way to spread the knowledge throughout the team and a chance for people to discuss implementation, maybe you'll have a better idea or another approach.

#### General guidelines

1. **You are not your code**.

     Believe it or not but you are really not your code. A lot of people get defensive when someone pin points mistakes or disagrees about implementation. The crazy idea is, that you really shouldn't because it's not you somebody's commenting on but your code.Heated discussions that can spawn during a code review will give you profit (new ways to look at the issue, other implementation ideas).

1. Try to keep the code for code reviews under 500 lines, if you exceed this, try to split it.
1. Don't focus on the bugs - finding bugs should be a byproduct of code review

#### Checklist ('todos' for code reviews)

  1. Check if the code does, what it was supposed to do. If the code doesn't work according to the acceptance criteria in the task, why bother and look for typos?

  1. Check the code itself. Even though it works fine from the outside it could be a real mess code-wise. Check, maybe you could suggest improvements.

      * Check for principles of software development - are they used or can you suggest using more?
      * Does the new code work well with the old one?
      * Is it over-engineered?
      * Do variables, constants, methods represent what their names are?
      * Are the exception message understandable and helpful?
      * Does the change impacts performance? If yes, why?
      * Is there logging/exception handling?

  1. Run and read the tests. Check if the tests cover all the additions. Avoid tests that don't really test (assert true). Read carefully and think of edge cases.

  1. Look for security flaws. Start off with [brakeman](https://github.com/presidentbeef/brakeman) or take a look at [Rails security checklist](https://github.com/brunofacca/zen-rails-security-checklist)

  1. Look for possible performance improvements

  1. If the feature is complicated and/or could use some sort of documentation, ask the reviewee to add it

#### Reading suggestions

  * [Code reviewing as a mindset](https://everydayrails.com/2017/01/16/code-review-mindset.html)
  * [Code Review: The art of writing code for others](https://www.eventbrite.com/engineering/code-review-the-art-of-writing-code-for-others/)
  * [What to Look for in a Code Review](https://leanpub.com/whattolookforinacodereview) by [Trisha Gee](https://twitter.com/trisha_gee)
  * [Egoless programming](https://blog.codinghorror.com/egoless-programming-you-are-not-your-job)
  * [You are not your code](http://www.hanselman.com/blog/YouAreNotYourCode.aspx)
  * [Implementing a Strong Code-Review Culture](https://www.youtube.com/watch?v=PJjmw9TRB7s)
  * [Preproduction Security Checklist for a Rails App](https://blog.codeship.com/preproduction-checklist-for-a-rails-app/)
  * [Ruby on Rails Security Project](https://rorsecurity.info/)


## Additional

1. Use your IDE/editor to your advantage. Most editors support linters and have a lot of useful features to make your life as a developer easier.
1. Never be afraid to ask. If you don't know something or are not sure, for the love of god, **ASK**.
1. Be a professional. Things like "we'll see" and "hopefully" are not in your dictionary.

    Sometimes you can be uncertain of things or simply don't know - it's better to check something and be sure. Being a professional means, that you know when to say "yes", "no" or even "I don't know, I have to check".

1. Make your life easier. If you know that something can be automated - do it.


## Epilogue

The ideas behind what you've read above are not written in stone and are not a final.

Building a good workplace is hard and it takes time. We are very open to new ideas and suggestions. So if you want to build our workplace with us don't hold out - talk :wink:

This document probably doesn't cover all possible aspects of your coding life and that's good - we need creativity

## General Reading suggestions

1. [Clean code](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) by [Robert C. Martin](https://en.wikipedia.org/wiki/Robert_Cecil_Martin)
1. [Clean coder](https://www.amazon.com/Clean-Coder-Conduct-Professional-Programmers/dp/0137081073) by [Robert C. Martin](https://en.wikipedia.org/wiki/Robert_Cecil_Martin)
1. [Practical Object-Oriented Design in Ruby: An Agile Primer](https://www.amazon.com/Practical-Object-Oriented-Design-Ruby-Addison-Wesley-ebook/dp/B0096BYG7C) by [Sandi Metz](https://en.wikipedia.org/wiki/Sandi_Metz)
1. [Eloquent Ruby](https://www.amazon.com/Eloquent-Ruby-Addison-Wesley-Professional-ebook/dp/B004MMEJ36) by [Russ Olsen](http://russolsen.com/pages/about/)

