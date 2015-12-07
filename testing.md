If your tests are painful, your code is probably bad.
However, your code is what it is, even if you don't have tests telling you so.
Thus painful tests are a blessing, because they are telling you what is wrong.

If bad code is a brain tumor, then test pain is the headache telling you to fix the problem now,
before you start bleeding out of your ears (disclaimer: my imagination exceeds my medical credentials)

Introduce abstractions in your test suite. Most test suites should be DRYer.

If your test does any of these things, it is not a unit test: uses randomness, talks to a filesystem/database/other processes, needs an internet connection.

Fixtures, factories, mocks, and stubs are all aspirin. In the world of code, headaches are less common than brain tumors. Are you sure aspirin is the solution?

Stubs are the worst form of aspirin.

All code that operates on arguments it does not receive is malignant.

The code you know you hate is good code in that it is upfront about its flaws.
Imagine that same code, refactored to conceal its issues.
It dons a disarming smile and blames you every time it burns you.

Starting a project with unit tests is like buying a house when you're born.
You don't have a fucking goddam clue what's going to happen by the time you're old enough to live there...
if you even live that long.

Don't pay debts you don't yet owe.

"Léon: The rifle is the first weapon you learn how to use, because it lets you keep your distance from the client.
The closer you get to being a pro, the closer you can get to the client. The knife, for example, is the last thing you learn."
The Rifle is a high-level test, the knife is a unit test.

The higher your test is, the blacker its box should be.

In RSpec, let blocks are rigid, because they do not take arguments.

Before/after, and setup/teardown methods are aspirin.

Design works best as a response to unit tests.

The first test should assert the reason your product exists.
The second test should illuminate the most threatening unknown.
These tests are your blackest boxes.

If you don't know what you're goal is, you should not be writing tests.

If you like your spike, then test it so you can keep it.

Never write a test for code that is not already being used.

Good test names can be recited during conversation without the other party knowing.

Do not specify behaviour that you do not know is correct
(ie do not make decisions because your tests identify unconsidered edge cases --
you can turn a 20 minute task into a 2 day task with little effort,
but all of that work will have to be undone when you identify the real requirements)

Do not refactor while your tests are failing.

The more confident you are / the more stable your code is, the more unit-level your tests should be.
The less confident / less stable, the more end-to-end / black-box your tests should be.

If you want to refactor your code to do the same thing,
but in a different way, and this breaks your tests, then your tests are too low.

Do not test presentation code.

Assert however many times as you feel are appropriate to prove what the test says is true.

A test that cannot be uniquely named can be consolidated into the test whose name it wants to use.

You should be able to duplicate a test within the same scope (method/block).
If you cannot, then your tests are coupled to their setup.

If your given/when/then portions are always the same, then extract them into a helper method.

Test bad data at the boundary of your system, asserting that it is not allowed to enter the system.

The solution to test pain is almost always to remove the painful thing by pushing it earlier in the callstack.

Read that last one again.

If you cannot test a nuance to your code without building another world, then you are testing too high.

Hand-rolled mocks are better than dynamic mocks. With or without mock verification.

Your mocks are not fake implementations, they are the specification of an interface,
and thus you should have tests that verify the adherence of the implementation
(what you might have otherwise called the "real code").
Yes, static type systems give you this for free. Hey, you're the one who's using mocks,
chemotherapy might remit cancer, but it also kills your white blood cells and makes your hair fall out.

If your code is similar to another piece of code, then copy/paste/modify it.

When you write tests after you write code,
make them fail so that you can have confidence in their assertions.

When you know what you want, then you should write the names of all your tests before you implement any of them.
This knowledge is low-hanging fruit, don't incur the cost of jumping between levels of abstraction until you've harvested it.

You do not need 100% *unit* test coverage.
You do need 100% test coverage.
This may be asymptotically unreachable... that, however, is not an excuse to not try.

The earlier code is in the callstack,
the less likely it is be gain value from being unit tested.

The earlier code appears in the callstack,
the more volatile it is, and thus the more high-level (end-to-end test) its tests should be.

Do not test implementation details.

Do not test private methods.

Do not test instance variables.

Classes in which every method needs its own set of tests are usually signs of multiple classes coupled into one.
The classes are masquerading as methods.

Abstractions should be extracted from other code based on which pieces change together as requirements are introduced.
To create the class immediately is to invest in premonitions.
Do not delude yourself, you are not clairvoyant.

A test's name is a specification, its body is an attempt to show that its name is a statement of truth.
When they are unaligned, the body should be subject to the name.

There is little value in a test name that doesn't tell you what you need to know about the object.
With RSpec, you can list the object's specification with the flag `--format documentation`.
With minitest, try this shell command `find test -type f | xargs ruby -ne 'print if /^ *(class.*Minitest|def test_|it\b)/'`

A test's name may describe its body if it is testing edge cases.
So names like "when called with a string" and "when called with an integer"
are simply about thoroughness and should be consolidated in an effort to minimize spam.

Triangulation is spam.

The number of tests you have is independent of the value of your test suite.
When people brag about how many tests they write, they are advocating spam (regardless of the value/quality of their tests).

Code which cannot be tested is bad code.
Sometimes bad code is good code.
This is not one of those times.

Do not test your programming language, your programming language works.
Ignore this if you do not know how your programming language works --
you can test it when you are actually testing your understanding of Ruby.
Extend this to the libraries you use.

Your code has bugs, regardless of whether you test it.

Edge cases are a code smell, relegate them to the boundaries of the system and assume correctness within the system.

You don't know what you're doing and you don't know where you're going.
Test at a level which is congruent with this fact.

When starting a project, assume you're going to completely rewrite/refactor your code three times before it begins to stabilize.
Now, do you *really* want to write this test?
If the answer is "no", but the test still has value, then write its name but not its body.

Do not test that a piece of your code works when your code does not work.
This is to say that on your first test, everything you do should be to get you closer to passing,
and after that first test, you are incrementing on a working solution.

Files and streams are worse than strings.
Objects that generate values are worse than the values they generate.
Callbacks are worse than the callstack (aside: JavaScript, you need coroutines).
Mixing in Enumerable is worse than returning an array. Guerilla patches are worse than private methods.

It does not matter what test tool you use.

Sometimes manual tests are the right tests. This isn't one of those times.

Use `pry` while testing.

You have pushed broken code into production.

Unit tests are the most immediate feedback tool for design.

I tend to have around 2.5 times more lines of test than lines of code.
This is an observation, not a prescription.

Write your own assertion methods.
Happy to argue this one, write your own assertion methods.

Curse code that adds methods to the toplevel of your tests.
Such methods should be namespaced within objects.
(eg in Rails, you probably have a `visit` and `get` method,
which do the same thing, but differently,
and are shat into the toplevel of your tests for no good reason --
Capybara should namespace its methods under the `page` object...
or, even better, let you define your own alias for a `Capybara::Session`, and )

There are only two relevant levels of tests low-level, which I call unit tests,
and high-level, which are best when described as acceptance tests, but have many names.

Acceptance tests are about the "why".

Integration tests are shitty acceptance tests.

BDD != TDD. They are mechanically similar, but their purpose is completely different. BDD is about purpose, TDD is about design.

Regression safety is a byproduct of testing. If it was the only value, it would still be value, but it is not the motivation.

Testing the same thing at multiple levels is a straight jacket.
It wastes your time, and it adds inertia to the current expectations, which are wrong.
When you go to change your things, every level of duplication is an additional level of change.

Extracting code does not necessitate the movement of tests,
often it just means your "unit" is a little larger than it used to be.

Ignore "realism" in unit tests. It's cost without value.

You are supposed to feel test pain.

In RSpec, use `--fail-fast`

When you're fixing a failing test, run only that test.

Model tests are shitty.

Validation tests do not require database saves.

To test an if-statement in a view, you must parse HTML.
You should not need to parse HTML to test an if statement.

If you respond to test pain, then your real code can look as trivial as the toy TDD examples you started with.

In Rails, begin with the assumption that testing routes, controllers, views, models, and helpers is wrong.
Your acceptance tests (Capybara, presumably) cover all of these.

You do not need fancy fucking test helpers.
Rails' controller methods `get/post/etc` blind you to the simple reality of what you are doing.
You can write your own with minimal effort.

The solution to test pain is to push the integration of painful dependencies to the caller.

The solution to test pain is to push the integration of painful dependencies to the caller.

Seriously. Stop and read this again. The solution to test pain is to push the integration of painful dependencies to the caller.

DHH doesn't know shit about design and Martin Fowler and Kent Beck
shouldn't have let him get away with that.

DHH was right in criticizing the cult of TDD.
I dislike him, but he's right so I'll quote him:
"An unrealistic, ineffective morality campaign for self-loathing and shaming."
Exactly, and thank you, DHH for saying it. Fuck shame.

The majority of True Believers™ in TDD are like majority of True Believers™ in any religion:
Their belief is a cavern of thoughtlessness. Emotion without Rationality.
Their priority is conformance to the conclusion. Listen to their arguments but be wary as their worldview is compromised.

Do you want to understand TDD's merits, limitations, boundaries, domain, purpose, strengths, etc?
Then break all the rules and break them with conviction.
Use only acceptance tests on your next project.
Use only unit-level tests on the one after that.
Don't test at all on the one after that.
Or, fuck, IDK, don't do any of this shit, stay an advanced beginner forever,
vacuously parroting the rhetoric your idols told you to with nothing but
the burning of belief in your chest to back you up.
Certainty is the posturing of a fragile epistemology.

If you want to follow the London School of TDD in Ruby,
be prepared to fake a type system or live each day in fear (I've done both).
This isn't specifically intended as a criticism, the concept is powerful,
Searls' rebranding as "discovery testing" is relevant
(because the language that is available to you dictates the thoughts that are available to you).

Don't get too caught up in the language of testing, there's like 5 vernaculars and they are not congruent.

If your tests do not give you confidence, they are probably worthless.
Worse than this, they are probably cost without benefit.

The cost of your tests is exponentially proportional to the time it takes them to run.

If you can't run the currently relevant tests in under a second (as measured by the `time` program),
then you've already incurred enough cost to more than double the time to completion.
Worse, you're dissuaded from investing in improvements that reduce the future cost for all other developers of this code.
That slope is slippery.

Searls might be joking about the 10x developer in http://blog.testdouble.com/posts/2015-11-16-how-to-stop-hating-your-tests.html,
I can't tell, but joke or not, he's right. 10x developers (Joe, we only superficially disagree)
don't put up with slow feedback loops. This is a massive massive massive difference.
I said it 3x now... that's on purpose... fkn seriously stop and *really* consider the implications.
There's a reason I make my students practice typing, keybindings, all of their tools,
and require them to daily demonstrate their acquisition of skill,
live, in front of me. This shit matters so much more than you realize.

"Still too slow? Implement features outside your app, and integrate later." -- Searls (http://blog.testdouble.com/posts/2015-11-16-how-to-stop-hating-your-tests.html) fkn brilliant.

Factories > Fixtures, because they are more flexible and more explicit. Avoid fixtures. Avoid factories.

Factories and fixtures hide dependencies. Dependencies are caner.

If you're in the novice / advanced beginner category, err on the side of high-level tests, because despite all their drawbacks, they're harder to fuck up.

If you have a reasonable idea of what's going on, err on the side of unit tests, because the cost will be lower.
