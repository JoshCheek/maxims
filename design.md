Comments are where you acknowledge your failures.

Documentation is the crutch of the complacent.

Bad Procedural code is better than bad Object Oriented code.

There is nothing inherently wrong with a 200 line method.

"Microservies" are objects whose stack frames are HTTP requests.
This cocks my eyebrow, but maybe I'm missing something.

Refactoring problematic code to conceal its problems is vanity and denial.

It does not matter if you use parens on method names. It does not matter if you use RSpec or Minitest.
It does not matter if you use let blocks or instance variables. It does not matter if you use map or collect.
It does not matter if your strings are single quoted or double quoted.
These are bikesheds, no permutation of them will matter when your nuclear reactor melts down.

Develop an aversion to mixing your nouns and verbs.

The flaw of object orientation is that it couples nouns and verbs -- data and behaviour.
This is often fine, but if you've ever seen a 5k line class, you know that some data
has many behaviours, and some behaviours do not operate on isolated data.
DCI seems like it could be the solution here, but I've not yet seen it done compellingly.
Perhaps this is where Ruby's refinements will finally find a home.

Long methods are fine.

The boundaries you expect your code to have are not the boundaries your code will have.

Write code that can be altered to accommodate many probable futures,
"altered" is an important concept, keep your options open and your commitment low.

Do not write code to support features you do not need.

A noun (eg anything that could be persisted in a database) should be segregated from its verbs.

A deeply coupled 200 line method is better in a controller than a model,
because you know that no-one is calling the controller method, but any code anywhere could be calling the model method.

A large model is really a small model with several other objects hiding under its bed.

A class with independent paths through its code is several classes masquerading as one.

Code that changes in tandem should be extracted into a separate object.

Decoupled code is composable. It has a large number of short callstacks, not a small number of deep callstacks.

When you don't know what the right design is, choose the wrong design and then pay attention.

Good code is ignorant to the context it is used in.

The need for design patterns is rare.

Context based if-statement with two branches are better than polymorphism.
Three branches is iffy ;)
Refactor your code before you introduce the fourth branch.

Mapping your callstack should reveal a tree, not a graph.

The earlier you are in a project, the truer it is that "bad code" is actually "good code".

Constants that store state are global variables.

Don't let anything you love talk to state that is stored in global variables.

Many verbs are better modeled as objects than as methods.

When considering whether to write `MyClass.new.my_method(my_argument)` or
`MyClass.new(my_argument).my_method`, choose the latter.
The former should immediately elicit fear.

When a class is a verb, it should have one public method, and that method should be named
`call` (eg `SignUserUp.new(data).call`). If a verb class needs more than one public method,
this implies you have a more than one class, one of them probably calls the other.

Between `SomeClass.call(data)` and `SomeClass.new(data).call`, the former is better,
because it goes through fewer objects. Eg you can stub it without needing a mock.

Lifecycle callbacks are usually used to couple context.
Pretend they are not in your toolbox.

All abstraction is a lie that should be used only as long as it is useful,
and ripped out as soon as the harm of the lie exceeds the value of the abstraction.

Distrust abstraction.

Every name is an abstraction.

Every collection whose elements can be named can be represented as a hash
whose keys are the names and values are the elements.
If its elements cannot be named, it can be represented as an array.

There are many things in Ruby which are not objects.

There are primarily three relevant constructs in Ruby:
objects, classes, and bindings (I'm lumping stack frames in with closures)

Anything which can cause your code to break is a dependency. Minimize dependencies.

Do not use a gem where you can write (or copy/paste/modify) 20 lines of code.

If you type out reference code to avoid copy/pasting it,
then you are following the letter of the law,
and you do not understand the spirit of the law.

If you keep referencing another piece of code,
copy/paste/comment-it-out until you no longer need to reference it.

I can copy and paste quicker and more accurately than you can type.

Mutability is gateway cancer.

A good algorithm is less important than good design.

The quality of code is indirectly proportional to the number of items that appear later than it in the callstack.

When class names are nouns, they are an abstraction of data,
when verbs, they are an abstraction of behaviour.
A method's name is an abstraction of its body.
A local variable's name is an abstraction of it's value.

When a name does not help you think about the thing it abstracts, it is a lie.
When this occurs, resort to your understanding of the mechanics of the language to reason about it.

A name that says "fuck, I don't know", such as a parameter named `x`, is better than a name that lies.

The only merit of metaprogramming is the reduction of tedium.

Good code looks easy.

More code is worse than less code.

Prefer primitives (Strings/Arrays/Hashes/Numerics/objects whose data is not stored in instance variables/objects with a literal representation)
over objects. You do not need a `Title` class when a `String` will do, this only introduces more code, and more code is worse code.

More abstractions are worse than fewer abstractions.

Abstraction is the most powerful tool you have.

Abstraction is a weapon that can be weilde against code or against humans.
Handled carelessly, you wield it against yourself.

A method that cannot be understood without reading the methods it calls
is indicative of lying abstractions. If they are only called by the this method, then inline them.
Otherwise, rename them so they don't lie, or so they blatantly state their failure as an abstraction.

A verbose name is better than a false name.

Everything implicit is a hidden dependency.

Do not use an instance variable where a local variable will do.
Do not use class variables.
Do not reference a global variable or state stored on a constant, except from `main`.

Parameters with default values hide dependencies, avoid them.

In JavaScript, callbacks exist to compensate for the lack of coroutines.
This is a failure of the language.

Don't say "block" to people who write JavaScript. It technically means the same thing,
but its implications are inverted, so you won't be able to communicate.

1 is not true. '1' is not true. 't' is not true.
0 is not false. '0' is not false. 'f' is not false.
These should be converted upon entry to the system.
And, if possible, before entering the system.

The calling code is responsible for the normalization of arguments.
To let the called code normalize them is a cyclical dependency,
the dependency being the knowledge of the calling contexts.

Every file should require all the code it depends on, and only the code it depends on.

Require farms are icebergs.

The language you use shapes the way that you think.

`puts` and `gets` should be removed from Ruby except in the presence of the `-e` / `-n` / `-p` flags.
Class variables should be removed from Ruby.
The behaviour of `require` poisons how you think.

Simple Made Easy has a good message, but the opacity of language causes many to assume it advocates what it admonishes.

"Complect" is an annoying word.

DSLs should be built on top of code that can be used without the DSL.
DSLs should not be built.

Do not trust Ruby.

Do not think in syntax.

Do not trust magic.

Do not fear code.

Do not trust names.

Do not disbelieve names unless that's the most reasonable explanation.

Do not tolerate painful tests.

Do not tolerate painful code.

Do not trust rules.

Do not follow rules unless you are a novice or advanced beginner (https://en.wikipedia.org/wiki/Dreyfus_model_of_skill_acquisition)

Do not tolerate test failures.

Do not tolerate slow tests.

Do not merge untested code.

Be apprehensive towards mixing in modules.

Namespace your code. Both within Ruby and on the file system.

The best code is idempotent.

Do not optimize in anticipation.

Take pleasure in deleting code. Take pleasure in deleting tests. Take pleasure in removing requirements.

Code that appears early in the callstack should be wiring.

Sometimes to refactor, you must defactor.

Procedural code is fine.

Functional code is fine.

Object oriented code is fine.
But the probability that you'll write good object oriented code is low,
so be apprehensive of object oriented code.

Do not add an if-statement to account for caller context.

Abstract code as soon as it is less work than leaving it unfactored.

Unfactored code is better than code factored in expectation of the future.

Most code is bad.

The grass is not greener on the other side.

Inheritance makes your code worse. Module mixins are inheritance.

Type systems only save you from writing certain tests.
If those tests are the ones that you keep wishing you had,
then either your attention is imbalanced,
or your code has bigger issues, or you need to have a
"Come to Jesus" meeting with some colleagues.

`NameError` and `NoMethodError` are type errors.

Do not accept anyone's assertions that cannot be argued compellingly.
Help them out by trying to understand their argument.

Do not favour an opinion because you or someone you like introduced it.

Take pleasure in the statements "I am wrong", "I fucked up", and "I don't know".
When they are true, these statements free you from the disparity between reality and perception.
If you cannot say them, you must advocate something you know is worse.
It unduly inflates your ego at the expense of your codebase and everyone who works on it.
Thus, an avoidance of these phrases is narcissism and deceit.

Generated code is debt.

Fuck Spring.

A fat controller is better than a fat model: A fat model implies many objects masquerading as one,
while a fat controller is up-front about its flaws.
A fat model inflicts pain when you try to extract its methods into a class,
because you have to check the entire app to make sure nothing is calling that method.
A fat controller's dependencies are apparent, because no one calls the controller
(even instantiating a controller is punishment).
Thus a shitty controller is orders of magnitude more refactorable than a shitty model.

For the same reasons that only `main` should talk to `ARGV`,
only your controller should call `save`

Push database writes as early in the callstack as you can get them.

In the same way that strong params was pulled out of the model,
validations should be pulled out of the model. But they haven't been yet,
so don't fight it until you have to.

All code in a class with shitty dependencies has shitty dependencies.
You can make a method `def sum(n1, n2) n1 + n2 end`, which is delightfully simple,
but if you put it in an `ActiveRecord::Base` subclass,
then it depends on ActiveRecord and ActiveSupport and probably a database and a table and a schema migration, etc, etc, etc.

Rails is wrong to not namespace the code in app.

The routing DSL is a lie, `rake routes` is the real routing DSL.
You can write your routes to look like the output of `rake routes`.

Rails is a context. Specifically, it is a context of providing an HTTP interface to your app.

In Rack based apps such as Rails, `env` is god.

Rack dependencies should be injected in middleware.
I never see anyone do this, my guess is that it's a failure of imagination.

The "Rails Way" is usually the wrong way, but don't fight it too hard.

The more you love something, the harder you should segregate it from Rails.
Rails is just the framework I use, this applies to all invasive dependencies.

Every line of code you write, in a production app is a line of code that will have to be maintained.
Are you sure you want to write that code?
