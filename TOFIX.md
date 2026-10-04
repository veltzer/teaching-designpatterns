# TOFIX

Findings from a code scan on 2026-10-04.

## High

- `design-patterns-exercises/src/com/dsl/design/pattern/singleton/MySingletonClass.java:12` - the reference Singleton is not a singleton: the holder field and `getInstance()` are instance members and the class has an implicit public constructor, so `SingletonPatternDemo.java:12` has to `new MySingletonClass()` first and every such object returns a different "instance". Make the field `private static`, `getInstance()` `public static`, and add a `private` constructor (and the demo should call `MySingletonClass.getInstance()`).
- `README.md:9` - says `DesignPatternsExercise.zip` packages `design-patterns-exercises/`, but the zip holds a different project: the `cmpt377.designpat` bakery/telephone/websearch starter code (plus `.idea/` workspace files and a 200 KB `data/Hamlet.txt`) that `Implementation.md:3` refers to as "the starter project". Fix the README to describe the zip as the starter project for `Implementation.md`.

## Medium

- `design-patterns-exercises/src/com/dsl/design/pattern/adapter/Adaptor.java:8` - the Adapter example adapts nothing: `Adaptor` implements `Converter` and forwards to another `Converter`, so source and target interfaces are the same (that is plain delegation/decorator). Likewise `strategy/StrategyPatternDemo.java:9` has a single `IStock` implementation and no context that swaps strategies. As reference solutions these teach the wrong shape; give the adapter an incompatible adaptee interface and the strategy example at least two interchangeable strategies selected at run time.
- `design-patterns-exercises/src/com/dsl/design/pattern/singleton/MySingletonClass.java:2` - every Java file carries "Author Steven Yeoh / Copyright (c) 2019. All rights reserved.", while the repo is published under MIT with Mark Veltzer as copyright holder (`LICENSE:3`). Either obtain/record permission and the upstream licence (credit in `design-patterns-exercises/README.md`), or replace the third-party code.
- No `rsconstruct.toml` or `.github/workflows/` is tracked, so nothing compiles the Java sources or lints the four markdown files (the broken links below would be caught by a markdown/link check). Add the standard fleet build config (javac/checkstyle for `design-patterns-exercises/src`, rumdl for the `.md` files).
- `iml/solutions.md:11` - `StringBuilder.append` is listed under "Abstract Factory"; it is a Builder and appears again correctly as Builder on line 12. Remove the line-11 entry.
- `iml/solutions.md:41` - the link `.../java/io/InputStream.htmlDecorator` is broken (stray "Decorator" pasted onto the URL); and line 55 links `.../wiki/Behavioral_patternProxy` (stray "Proxy"). Fix both URLs.

## Low

- `iml/solutions.md:1` - the answer key for `Identify_the_patterns.md` lives in a directory named `iml/` and is not mentioned in `README.md`; rename the directory (e.g. `solutions/`) and list it in the README.
- `design-patterns-exercises/design-pattern.iml:7` - declares a `test` source folder and a JUnit 5.4 library, but there is no `test/` directory; drop the stale entries or add the tests.
- `Identify_the_patterns.md:1` - typos in the student-facing text: "exapmles" (line 1), "stardard" (line 3), "classess" (line 5).
