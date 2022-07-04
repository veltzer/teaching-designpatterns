# Telephone
The telephone package in the starter project contains partial code for making some parts of a (pretend!) telephone.

Change the code so that it uses the Observer Design Pattern as follows:

In the model, define an interface for the observers.
Have the model notify the observers whenever a new digit is entered for the phone number.
Have the UI (the Screen class) create two observers:
The first observer prints the newest digit out to the screen
The second observer prints "Now dialing 12345678901..." out to the screen (where the number is the number the model has).

Sample output
```txt
Sample output from `telephone` package's Main

Pressing: 2
2
Pressing: 5
5
Pressing: 5
5
Pressing: 4
4
Pressing: 8
8
Pressing: 1
1
Pressing: 7
7
Pressing: 0
0
Pressing: 9
9
Pressing: 2
2
Now dialing 2554817092...
```

## Constraints
* Only the UI can print to the screen
* The model must be decoupled from the UI (model must not know about the UI).


# Web Search
The websearch package in the starter project contains partial code for a pretend web search engine. It will read a data file and "pretend" that each line is a query someone sent to a search engine. Our goal is to extract, on the fly, "interesting" queries meeting certain conditions.

Note that the code already uses the Observer Pattern to notify the Snooper of each query. The Snooper then prints everything out.

Change the code so that it uses the Strategy Design Pattern as follows:

In the model, create a new interface which describes the interface for a policy object that will define a query filter.
A query filter policy object will have one method which will be passed a string (the query) and return true if the model should notify the observer about this query; returns false if the observer is not interested in this string (the query). For inspiration, see the Java FileFilter class.
Change the model so when an observer is registered, the registration method to also accept a query filter policy object.
Change the model to, for each query (string from the file), check if an observer is interested in the query before notifying it.
## Change the client (Snooper.java) to create two query observers:
* One prints out "Oh yes! <query>" whenever the query contains the word 'friend' (case insensitive).
* One prints out "So long....! <query>" whenever the query is more than 60 characters long

Sample Output:
```txt
Sample output from `websearch` package's Main.java

Oh Yes!     Friends to this ground.
So long....     Enter KING CLAUDIUS, QUEEN GERTRUDE, HAMLET, POLONIUS, LAERTES, VOLTIMAND, CORNELIUS, Lords, and Attendants
Oh Yes!     And let thine eye look like a friend on Denmark.
Oh Yes!     Sir, my good friend; I'll change that name with you:
Oh Yes!     Those friends thou hast, and their adoption tried,
Oh Yes!     For loan oft loses both itself and friend,
Oh Yes!     O'ermaster 't as you may. And now, good friends,
Oh Yes!     As you are friends, scholars and soldiers,
Oh Yes!     A worthy pioner! Once more remove, good friends.
So long....     Or 'If we list to speak,' or 'There be, an if they might,'
Oh Yes!     May do, to express his love and friending to you,
Oh Yes!     As thus, 'I know his father and his friends,
So long....     That's not my meaning: but breathe his faults so quaintly
So long....     As 'twere a thing a little soil'd i' the working, Mark you,
Oh Yes!     'Good sir,' or so, or 'friend,' or 'gentleman,'
Oh Yes!     At 'closes in the consequence,' at 'friend or so,'
So long....     Enter KING CLAUDIUS, QUEEN GERTRUDE, ROSENCRANTZ, GUILDENSTERN, and Attendants
Oh Yes!     Welcome, my good friends!
Oh Yes!     Friend, look to 't.
Oh Yes!     My excellent good friends! How dost thou,
So long....     Guildenstern? Ah, Rosencrantz! Good lads, how do ye both?
Oh Yes!     my good friends, deserved at the hands of fortune,
So long....     substance of the ambitious is merely the shadow of a dream.
Oh Yes!     beaten way of friendship, what make you at Elsinore?
Oh Yes!     thank you: and sure, dear friends, my thanks are
So long....     Why did you laugh then, when I said 'man delights not me'?
Oh Yes!     to see thee well. Welcome, good friends. O, my old
Oh Yes!     friend! thy face is valenced since I saw thee last:
Oh Yes!     Follow him, friends: we'll hear a play to-morrow.
Oh Yes!     Dost thou hear me, old friend; can you play the
Oh Yes!     My good friends, I'll leave you till night: you are
So long....     Enter KING CLAUDIUS, QUEEN GERTRUDE, POLONIUS, OPHELIA, ROSENCRANTZ, and GUILDENSTERN
So long....     The courtier's, soldier's, scholar's, eye, tongue, sword;
So long....     How now, my lord! I will the king hear this piece of work?
So long....     To feed and clothe thee? Why should the poor be flatter'd?
So long....     Danish march. A flourish. Enter KING CLAUDIUS, QUEEN GERTRUDE, POLONIUS, OPHELIA, ROSENCRANTZ, GUILDENSTERN, and others
So long....     Enter a King and a Queen very lovingly; the Queen embracing him, and he her. She kneels, and makes show of protestation unto him. He takes her up, and declines his head upon her neck: lays him down upon a bank of flowers: she, seeing him asleep, leaves him. Anon comes in a fellow, takes off his crown, kisses it, and pours poison in the King's ears, and exit. The Queen returns; finds the King dead, and makes passionate action. The Poisoner, with some two or three Mutes, comes in again, seeming to lament with her. The dead body is carried away. The Poisoner wooes the Queen with gifts: she seems loath and unwilling awhile, but in the end accepts his love
So long....     ashamed to show, he'll not shame to tell you what it means.
Oh Yes!     The poor advanced makes friends of enemies.
Oh Yes!     For who not needs shall never lack a friend,
Oh Yes!     And who in want a hollow friend doth try,
Oh Yes!     you deny your griefs to your friend.
So long....     Do you see yonder cloud that's almost in shape of a camel?
Oh Yes!     Leave me, friends.
So long....     Enter KING CLAUDIUS, QUEEN GERTRUDE, ROSENCRANTZ, and GUILDENSTERN
Oh Yes!     Friends both, go join you with some further aid:
Oh Yes!     Come, Gertrude, we'll call up our wisest friends;
So long....     and wife is one flesh; and so, my mother. Come, for England!
So long....     There's tricks i' the world; and hems, and beats her heart;
Oh Yes!     That, swoopstake, you will draw both friend and foe,
Oh Yes!     To his good friends thus wide I'll ope my arms;
So long....     love, remember: and there is pansies. that's for thoughts.
Oh Yes!     Make choice of whom your wisest friends you will.
Oh Yes!     And you must put me in your heart for friend,
So long....     that is not guilty of his own death shortens not his own life.
So long....     such-a-one's horse, when he meant to beg it; might it not?
So long....     but to play at loggats with 'em? mine ache to think on't.
So long....     this box; and must the inheritor himself have no more, ha?
So long....     yours: for my part, I do not lie in't, and yet it is mine.
So long....     'tis for the dead, not for the quick; therefore thou liest.
So long....     One that was a woman, sir; but, rest her soul, she's dead.
So long....     A whoreson mad fellow's it was: whose do you think it was?
So long....     Enter Priest, & c. in procession; the Corpse of OPHELIA, LAERTES and Mourners following; KING CLAUDIUS, QUEEN GERTRUDE, their trains, & c
So long....     spirit. Put your bonnet to his right use; 'tis for the head.
So long....     His purse is empty already; all's golden words are spent.
So long....     I knew you must be edified by the margent ere you had done.
So long....     against the Danish. Why is this 'imponed,' as you call it?
So long....     if not, I will gain nothing but my shame and the odd hits.
So long....     To this effect, sir; after what flourish your nature will.
So long....     Enter KING CLAUDIUS, QUEEN GERTRUDE, LAERTES, Lords, OSRIC, and Attendants with foils, & c
So long....     LAERTES wounds HAMLET; then in scuffling, they change rapiers, and HAMLET wounds LAERTES
Oh Yes!     O, yet defend me, friends; I am but hurt.
So long....     A dead march. Exeunt, bearing off the dead bodies; after which a peal of ordnance is shot off
```

## Constraints
* The model should not know anything about the implementation of the query filter policy objects, other than they implement the required interface.



# Bakery
The bakery package in the starter project contains partial code for a bakery. The bakery makes two types of cakes: vanilla and chocolate. They now want to make more complex cakes such as a "Multi-layered Vanilla cake with sprinkles that says 'Hello World!'"

Change the code so that an order can contain such complex cakes using the Decorator Pattern:

Create the necessary decorator classes:
For multi-layered cakes, add $5 and print "Multi-layered" out at the front of the name.
For sprinkles, add $2 and print "with sprinkles" at the end of the name.
For a cake with the saying X, add nothing to the cost, and print "with saying 'X'" at the end of the name.
Add the new type of cake: strawberry cake, which costs twice as much as a Cake.
Change the client to add the following to an Order, and print the Order:
Chocolate cake
Vanilla cake with saying "PLAIN!"
Vanilla cake with sprinkles with saying "FANCY"
Multi-layered Strawberry cake with double sprinkles and two sayings "One of" and "EVERYTHING"
Suggested output is: Multi-layered Strawberry cake with sprinkles with sprinkles with saying "One of" with saying "EVERYTHING"

Sample output
```txt
Sample output from `bakery` package's Main.java


   10  Chocolate cake
   10  Vanilla cake with saying "PLAIN!"
   12  Vanilla cake with sprinkles with saying "FANCY!"
   29  Multi-layered Strawberry cake with sprinkles with sprinkles with saying "One of" with saying "EVERYTHING"
```

## Constraints
* Adding a new type of cake does not change any existing code (except to instantiate it)
* Adding a new way to decorate or style the cake (such as multi-layer, or with sprinkles) does not change any existing code (except to instantiate it)
