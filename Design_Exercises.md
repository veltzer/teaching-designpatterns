What pattern best meets each of these situations below?
Explain how two design principles apply to each design.

The model stores a collection of blocks. Blocks can be medal or wood; can be painted, sanded, or chrome plated; and can sometimes be radioactive or magnetized. What design pattern would allow the system to easily add new types of blocks without changing existing code?

The model for a game stores robot. The robot navigates a maze that has obstacles. While playing the game, the robot can be upgraded with new parts that change its abilities like speed, weapons, and shields. Which design principle allows the robot object to change its behaviour at runtime in flexible ways.

The model stores a phone number, and the UI (a keypad) allows the user to enter digits one at a time. A different part of the UI wants to respond to each key being entered; however a) the two parts of the UI should be decoupled, and b) the model should be decoupled from the UI (model knows nothing about the UI). Which pattern would allow this?

A library supports recursively searching a directory for files. It allows the client code to provide it an object to filter the results. For each file which the library finds, it will ask the filter object if that file should be accepted or rejected. (See Java's FileFilter)
