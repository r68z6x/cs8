java cAssignment 1
Learning Outcomes  Materials
This assignment is intended to develop and assess the following unit learning outcomes:
LO1. Iteratively apply object-oriented design principles to design small to medium-size software systems, using 
standard software engineering notations, namely UML class diagrams and UML interaction diagrams.
LO2. Describe the quality of object-oriented software designs, both in terms of meeting user requirements and 
the eﬀective application of object-oriented design concepts and principles.
LO3. Apply object-oriented programming constructs, such as abstraction, information hiding, inheritance, and 
polymorphism, to implement object-oriented designs using a programming language (namely, Java).
LO5. Apply principles of software engineering practice to create object-oriented systems with peers using tools 
including integrated development environments (IDEs), UML drawing tools, and version control systems.
To demonstrate your ability, you will be expected to:
read and understand UML design documentation for an existing Java system
propose a design for additional functionality for this system
create UML class diagrams to document your design using a UML drawing tool such as 
diagrams.net, UMLet or plantuml – you are free to choose which one
write a design rationale evaluating your proposed design and outlining some alternatives
implement the features of the system that you designed
use an integrated development environment to do so
use git to manage your team's ﬁles and documents
The marking scheme for this assignment will reﬂect these expectations
Learning Materials
The base code will be automatically available in your group's repository (Gitlab).
Repeat this mantra: Design, write code, test, ﬁx design, ﬁx code, repeat   
Note: You must NOT follow demo apps' design decisions; they only show how to use the engine, NOT how to 
design a proper system with object-oriented principles.Introduction
For the rest of the semester, you will be working on a relatively large software project. You will design 
and implement new functionalities to an existing system that we will provide to you.
IMPORTANT: A document explaining the FIT2099 Assignment Rules (a module above Assignment 1). Please 
read it and make sure you understand BEFORE you begin the project for your own beneﬁts (i.e., get good 
grades and better learning experience).
In this assignment (Assignment 1), you will be working individually to implement the ﬁrst few 
features of the game. We highly recommend starting by extracting all of the game features. Then, 
proceed with designing, testing, and repeating the process as needed. This iterative design-thinking 
approach will help ensure a well-developed and reﬁned system.
Getting Started
The initial codebase will be available in a repository that will be created for you on 
git.infotech.monash.edu. In the meantime, please go through the assignment support modules on Ed 
Lesson to familiarise yourself with the game engine that you will use during the assignment. 
You do not need to submit an interaction diagram (e.g. sequence diagram or communication diagram) in 
assignment 1. However, you will need to submit these documents for Assignment 2 and Assignment 3. For 
assignment 1, you may still create these documents if you ﬁnd them useful for designing the system.
General background
You will be working on a text-based “rogue-like” game. Rogue-like games are named after the ﬁrst 
such program: a fantasy game named Rogue. They were very popular in the days before home 
computers were capable of elaborate graphics and still have a small but dedicated following. 
If you would like more information about rogue-like games, a good site is http://www.roguebasin.com/. The 
initial codebase will be available in the repository mentioned above. It includes a folder containing design 
documents for the system. ELDEN THING: SHADOW OF THE INHERITREE
In this assignment, we will develop the “ELDEN THING: SHADOW OF THE INHERITREE” game, inspired 
by the recently released downloadable content for the game Elden Ring: "ELDEN RING Shadow of the 
Erdtree". We may use several similar names (characters, items, locations) and concepts. The purpose 
of using an actual game’s concepts is to help you visualise the required features, such as watching the 
video gameplay from the actual game to illustrate features that you may ﬁnd challenging to 
comprehend. We also believe using actual game references may bring fun while working on the 
assignments. 
All linked game contents, videos, and images belong to the respective owners and are 
subject to copyright. We mainly use the concepts for educational purposes and provide 
credit to the original creators accordingly. We may also add, alter, and reduce the 
original content and features to make them more suitable to the game engine, unit 
outcomes, and assignments’ time frame. 
What’s next?
Below are four slides (REQ1-REQ4) describing the requirements you need to complete. Each 
requirement includes game features that include background stories, entity descriptions (actors, 
items, or ground), relationships between entities, and actions between them. We suggest extracting 
these features into a list and discussing it with the TAs to ensure all features are included (this 
discussion is not assessed, but highly recommended).
Following these requirement slides, we will outline the deliverables necessary for the Assignment 1 
assessment.Meet Alexander, the Pot Friend
Expand
Alexander, the Pot Friend
Image: Alexander, Warrior Jar (source: https://eldenring.fandom.com/wiki/Alexander,_Warrior_Jar)
Throughout your learning journey, "Alexander, the Pot Friend" will give you advice throughout the 
assignment speciﬁcations that you may need to take note of inside "info" boxes. For example:
Alexander says, "Prithee, peruse the assignment speciﬁcations with care ere thou dost commence."
Please read the assignment speciﬁcations thoroughly before you start. We recommend that you visit (or revisit)
the Assignment Support modules in Weeks 2-5.
Disclaimer:
In the spirit of the original game, we have enlisted the help of ChatGPT 4.0 (Microsoft Copilot) to 
generate all Old English quotes within these assignment speciﬁcations. It always starts with a wise 
quote from Alexander, the Pot Friend, followed by the actual information/hint/warning that you 
need to care about. We hope this adds a slight element of fun and whimsy as you read through 
the requirements. Enjoy the journey back in time!
Here are some example prompts we have used:
“Generate an Old-English quote about the XXX.”
“Create an Old-English phrase about 'keep it simple, stupid'.”
“Provide an Old-English proverb related to 'be careful of giant's attack'.”REQ1: The Lord of the Old Order
Image: The Tarnished (source: 
https://static.wikia.nocookie.net/eldenring/images/5/52/Tarnished_E3_2021.jpg/revision/latest/scale-towidth-down/1000?cb=20210621011318)
In
 Elden Thing, you play as the “Tarnished” ( @ ), who has claimed the Elden Throne, becoming the 
Lord of the Old Order.
Now, following the trail of a seemingly missing demigod, the Tarnished enters the Land of Shadow 
(see REQ2 Title), where the event of the game takes place.
The “Tarnished” starts at a map called the “Gravesite Plain” inside a small shack (see info box below).
"..........~~~~~~~...~~~~~~~......~...........",
"~..........~~~~~....~~~~~~...................",
"~~.........~~~~.....~~~~~~...................",
"~~~..#####..~~.....~~~~~~~...................",
"~~~..#___#........~~~~~~~~~..................",
"~~~..#___#.......~~~~~~.~~~..................",
"~~~..##_##......~~~~~~.......................",
"~~~~...........~~~~~~~...........~~..........",
"~~~~~.........~~~~~~~~.......~~~~~~~.........",
"~~~~~~.......~~~~~~~~~~.....~~~~~~~~........."
The "Gravesite Plain" map
The small shack is represented by several squares of ﬂoor ( _ ) and surrounded by walls ( # ).
```
#####
#____#
#____#
##_##
```They start with 150 hit points (health), 100 mana, and 5 strength.
Alexander says, "Verily, ensure thou dost ever display the Tarnished’s vitalities"
Make sure to always display the Tarnished’s attributes (hitpoints, mana, and strength) at each game tick.
Within the surroundings of the shack, there are two weapons that the Tarnished can pick up: A Short 
Sword ( ! ) and Great Knife ( † ).
The Tarnished must have at least 10 strength points to pick up the Short Sword and at least 5 strength 
points to pick up the Great Knife. Once picked up, they can use the Short Sword to attack enemies (see 
REQ4), dealing 100 damage with a 75% chance to hit (hit rate). The Great Knife can also be used to 
attack enemies, dealing 75 damage with a 60% chance to hit. The Tarnished may also decide to drop 
any of the picked-up weapons at any time and pick any of them up again.
The Tarnished may also decide to attack enemies with their bare ﬁst, dealing 25 damage with a 50% 
chance to hit.
Alexander says, "Gather thou the weapons thy heart desires, for in thy hands lies the power to wield them all.”
The Tarnished can pick up as many weapons as they want. If there are multiple weapons in their inventory, the 
Tarnished can choose to attack with each weapon, in addition to the bare ﬁst.REQ2: The Land of Shadow
Image. The Land of Shadow (source: 
https://static.wikia.nocookie.net/eldenring/images/5/52/ER_The_Land_of_Shadows.jpeg/revision/latest/scal
e-to-width-down/1000?cb=20240221154538)
Inside the small shack, the Tarnished can pick up two items: Flask of Healing ( u ) and Flask of 
Rejuvenation ( o ). Both items can be consumed by the Tarnished. Similar to the weapons in REQ1, 
both items can be dropped oﬀ at any time.
Upon use, Flask of Healing heals the Tarnished by 150 hit points. This ﬂask has 5 charges, i.e., it can be 
consumed by the Tarnished 5 times.
Flask of Rejuvenation restores the Tarnished’s mana by 100 points when used. Unlike the Flask of 
Healing, this ﬂask only has 3 charges.
Once a ﬂask (Flask of Healing or Flask of Rejuvenation) runs out of charges, it will not vanish from the 
world, i.e., the Tarnished can still choose to consume the empty ﬂask, but attempting to consume an 
empty ﬂask will result in a message, such as Flask of Healing is empty or Flask of 
Rejuvenation is empty , to be displayed on the screen.
Heading out to explore the Land of Shadow, the Tarnished ﬁnds several Shadowtree Fragments ( e ) 
scattered around, which can be picked up and dropped oﬀ at any time. Consuming one Shadowtree 
Fragment blesses the Tarnished, increasing their maximum hit points by 50 points, their maximum 
mana by 25 points, and their maximum strength points by 5 points.
Alexander says, "Pray thee, kind soul, lend thine aid in this endeavour, for together we shall achieve greatness."
You must manually put 5 instances of the Shadowtree Fragment on the ﬁrst game map.
Unlike the Flask of Healing and Flask of Rejuvenation, once consumed, the Shadowtree Fragment will disappear from the Tarnished’s inventory, i.e., it can only be consumed once.
Here are some design considerations when working on this requirement (Note that this list is non-exhaustive): 
- In the future version of the game, there could be other “things” that the Tarnished can consume. 
- A “thing” may not always be an item. 
- Once consumed, these “things” may produce diﬀerent eﬀects, such as poisoning the player, healing the 
player over time, etc. 
Can your design accomodate this potential extension while adhering to the principles taught in the unit, e.g., 
the SOLID principles?REQ3: The Furnace Golem
Expand
Image. The Furnace Golem (source: 
https://static.wikia.nocookie.net/eldenring/images/0/08/Shadow_of_the_Erdtree_promotional_screenshot_2
.jpg/revision/latest/scale-to-width-down/1000?cb=20240221190058)
The Furnace Golems ( A ) are foes that the Tarnished must face in the Land of Shadow. They are large 
titans with ﬂames set eternally ablaze in their basket-like torso.
A Furnace Golem has 1000 hit points. It can wander around the game map.
If the Tarnished is within its surroundings (adjacent squares), the golem will stop wandering around, 
but instead, it will stomp the Tarnished with its foot, dealing 100 damage with a 5% chance to hit. 
Alexander says, “An enemy’s blade may not seek their own ally, yet in the clash of arms, unintended harm may befall.”
An enemy cannot directly target and attack another enemy. An enemy's attack may result in a collateral 
damage to another enemy.
Alexander says, "Pray thee, kind soul, the heavens proclaim thy name should thee meet thy end, for it is a reminder of our 
mortal trials."
Make sure to print out the "YOU DIED" message when the Tarnished dies.
Once within its surroundings, the Furnace Golem will follow the Tarnished around the map until either 
one of them dies.
Alexander says, "Venture forth upon the path to the Red Planet, and grand rewards shall be thine!"
It also cannot enter the ﬂoor ( _ ), allowing the Tarnished to escape safely to the small shack if needed.Here are some design considerations when working on this requirement (Note that this list is non-exhaustive)
- There may be other NPCs (non-playable characters) in the future version of the game, which may or may not 
be hostile towards the Tarnished.
- Other NPCs may be able to wander around and attack the Tarnished if they are hostile. They may have other 
ways of behaving, e.g., following the Tarnished around, picking up items, etc.
- There's a possibility to have more behaviours in the future, and these behaviours must be 'ordered' to 
simulate a "rule-based Artiﬁcial Intelligence".
Can your design accomodate this potential extension while adhering to the principles taught in the unit, e.g., 
the SOLID principles?REQ4: "O Tarnished of no renown, you shall burn"
Expand
Image. The Furnace Golem's stomp attack, resulting in a large explosion within its surroundings area 
(source: https://eldenring.wiki.fextralife.com/ﬁle/Elden-Ring/furnace-golem-elden-ring-wiki.jpg)
Due to its size, a Furnace Golem stomp has a 10% chance to create an explosion regardless of whether 
the stomp attack hits the Tarnished, dealing 50 collateral damage to all actors (friends or foes) within 
the golem's surroundings. This means that there is a possibility for the Golem to deal damage twice 
to the tarnished: one with its stomp attack and the other one with the explosion.
Alexander again says, “An enemy’s blade may not seek their own ally, yet in the clash of arms, unintended harm may 
befall.”
An enemy cannot directly target and attack another enemy. An enemy's attack may result in a collateral 
damage to another enemy.
Alexander says, "Beware the giant’s onslaught, for their might is great and their wrath ﬁerce."
Make sure to print out a message when the Furnace Golem deals the explosion damage, e.g., Furnace 
Golem's stomp attack results in shockwave in the surrounding areas.
Additionally, the explosion results in the surrounding area of the Furnace Golem being burned. The 
ﬁre ( w ) lasts for 5 turns. If the tarnished stands within the burning ground, they will take 5 damage 
per turn. The Furnace Golem itself is resistant to ﬁre, i.e., stepping into the burning ground will not 
inﬂict damage upon it. Puddles ( ~ ), however, cannot be burned, allowing the Tarnished to stay safe 
from the burn damage, i.e., Other grounds, including Dirt, Wall, and Floor can be burned. Once the 
burning ends, the ground will return to its original form.
Depending on your implementation, the ﬁre damage may stack if the Furnace Golem burns the 
same locations over and over again.Here are some design considerations when working on this requirement (Note that this list is non-exha代 写program、Java
代做程序编程语言ustive)
- Other NPCs' attack may result in a diﬀerent eﬀect, e.g. Furnace Golem's attack can cause a shockwave, 
damaging all actors within its surroundings.
- There may be other types of grounds that are not burnable.
- Other NPCs' may be resistant to burning
Can your design accomodate this potential extension while adhering to the principles taught in the unit, e.g., 
the SOLID principles?Submission Instructions
Not following any one of the instructions below will result in penalty being applied to your ﬁnal submission.
You do not need to submit an interaction diagram (e.g. sequence diagram or communication diagram) in 
assignment 1. However, you will need to submit these documents for assignment 2 and assignment 3. For 
assignment 1, you may still create these documents if you ﬁnd them useful for designing the system although 
we cover them in later weeks.
We will mark your assignment based on the latest commit in the main branch in your GitLab repository by the 
due date, not in the master branch.
Class Diagrams  Documentation Submission
As mentioned in the Design  Diagrams section, you MUST create one design (class) 
diagram per requirement. In other words, each requirement must be represented in its own 
separate diagram. Organising them in one large design diagram or combining requirements 
based on their packages is not allowed. Doing so may reduce the clarity of your design diagram 
or could be seen as an attempt at reverse engineering. Penalties will be applied if this occurs. 
Please keep each requirement diagram distinct and avoid any attempts to merge or combine 
them.
You MUST save your design documentation, including design diagrams, rationale and report 
(diagram + rationale combined into a single document), in the 
"docs/design/{assignmentName}" directory. So, for Assignment 1, you must save all design 
documentation in the "docs/design/assignment1" directory.
TAs cannot be expected to look at other directories, except for "docs/design/{assignmentName}", when 
marking the design diagrams and rationale.
All design documentation must be saved in PDF format (or PNG/PDF for diagrams, such as 
REQ1.png, REQ2.png, and so on).
A Moodle submission is compulsory, and it must be done before the deadline. Please, 
compress ALL ﬁles (code, documentation, and diagrams) as one zip ﬁle, and submit the 
compressed ﬁle.
Disclaimer: Although there are multiple ways to design the game, there are also bad designs and good designs 
- we will mark your submission not against one design but based on the design principles
Design DiagramsWe expect you to produce four UML class diagrams following the FIT2099 Assignment Rules. These 
Rules are available on EdLesson.
You should not create one class diagram that shows the entire system. The sample diagram in 
the base code shows the whole system to help you understand how the game works with the 
engine . But, in this assignment, you only need to show the following:
the new parts, 
the parts you expect to change, and 
enough information to let readers know where your new classes ﬁt into the existing system. 
As it is likely that the precise names and signatures of methods will be refactored during 
development, you do not have to put them in these class diagrams. Instead, the overall 
responsibilities of the classes need to be documented somewhere, as you will need this information to 
begin implementation. This can be done in a separate text document ( .md markdown format) or 
spreadsheet, which you should put inside the docs directory. We will not assess this document, but 
we believe it will be handy during the implementation phase.
Design Rationale
A design rationale should be created for each requirement, with a maximum word limit of 1,000 words per 
requirement. However, aim for concise and focused explanations (at least ~500 words). You can submit a single 
text-based/PDF document.
To help us understand how your system will work, you must also write a design rationale to explain 
your choices. You must demonstrate how your proposed system will work and why you chose to do 
it that way. Here is where you should write down concepts and theories you've learnt so far (e.g., 
DRY, coupling and cohesion, etc.). You must consider the pros and cons of the design to justify your 
argument.
The design (which includes all the diagrams and text that you create) must clearly show the following:
what classes will exist in your extended system
what the roles and responsibilities of any new or signiﬁcantly modiﬁed classes are
how these classes relate to and interact with the existing system
how the (existing and new) classes will interact to deliver the required functionality
You are not required to create new documentation for components of the existing system that you do 
not plan to change.
IMPORTANT! We will not accept any Word document because it cannot be opened/displayed in Gitlab.
ImplementationWe will assess your design implementation (i.e., Java codes). We will assess all of your codes in the 
Gitlab repository. Please ensure you push/merge all of your local Java codes to the main branch. 
You need to ensure that your game can run without breaking. Please follow the "Testing Instructions" 
from each requirement to satisfy the completeness of its features.
A reminder: you must not modify the game engine, as stated in the assignment rules document.
Your implementation must adhere to the Google Java coding standards. 
Google Java coding standards: https://google.github.io/styleguide/javaguide.html#s5-naming 
Write Javadoc comments for at least all public and protected methods and attributes in your classes.
You will be marked on your adherence to the standards, Javadoc, and general commenting guidelines 
that were posted to EdStem earlier in the semester.
To ensure that your work adheres to good coding practices in this unit, we encourage you to minimise the use 
of instanceof and/or downcasting, as they are considered code smells. It's important to note that if there are 
any instances where you need to use them, please provide appropriate justiﬁcations in code comments or 
design rationale. We believe learning how to properly utilise polymorphism is crucial in addressing this code 
smell, and we are committed to teaching you how to do so eﬀectively.Marking Rubric
Assignment 1 rubric
Prerequisite for marking: Design documents (UML diagrams and design rationale) and 
implementation need to be submitted for the assignment to go through the marking process. Missing 
any of these will result in 0 marks. 
Overview:
Total: 28 points
Feature implementation completeness (6 points)
Implementation quality: design principles (8 points)
Design rationale (4 marks)
Integration with the existing system (2 points)
UML syntax and clarity (2 points)
Alignment and design consistency (2 points)
Style  Javadoc (1 point)
Git usage (2 points) 
Format and directory structure (1 point)
Detailed rubric items:
Feature implementation completeness (6 points)
6 marks - The system runs and perfectly meets all functional expectations as per the relevant 
requirement(s) with no runtime errors. All required classes and relationships are implemented, and 
the program's behaviour aligns perfectly with the speciﬁcation.
5 marks - The system runs and meets all functional expectations (with some minor errors or 
punctual omissions) as per the relevant requirement(s). All necessary classes and relationships are 
included, and the program's behaviour largely matches the speciﬁcation, except for one or two 
minor unexpected behaviours. No runtime errors occur.
4 marks - The system runs and partially meets all functional expectations, displaying several 
minor functional errors or omissions as per the relevant requirement(s). Despite this, the majority 
of necessary classes and relationships are included, and only a few minor unexpected behaviours 
occur. No runtime errors are present.3 marks - The system runs and all functional expectations were addressed to some extent, 
(with one or two major functional errors) as per the relevant requirement(s). Most important classes 
and relationships are included but at least one or two major unexpected behaviors are 
observed. A major unexpected behaviour is that which aﬀects considerably the completeness of at 
least one requirement. No runtime errors occur.
2 marks - The system runs but several functional expectations were not addressed as per the 
relevant requirement(s) (e.g. the notion of Behaviour is not included even though it is a part of the 
requirement). Alternatively, runtime errors occur during the execution of the system but they can be 
easily ﬁxed. 
1 mark - The system runs but addresses only some functional expectations and shows major 
omissions as per the relevant requirement(s) (important classes or relationships are missing). 
Alternatively, runtime errors occur during the execution of the system without a clear idea of the 
cause or cannot be easily ﬁxed. 
0 marks - The system runs but it poorly addresses or doesn’t address the functional 
expectations as per the relevant requirement(s). Alternatively, the system might not run at all.
Implementation quality: design principles (8 points)
This item applies across all functional expectations as per the relevant requirement(s)
8 marks - The implementation of all functional expectations as per the relevant requirement(s) 
ﬂawlessly adheres to good design principles and concepts (e.g., DRY and SOLID principles), 
making the design easy to extend and maintain. Any punctual violations are convincingly justiﬁed in 
the design rationale (e.g., using singleton to implement a feature). All relevant requirements have 
been addressed.
7 marks - The implementation follows good design principles nearly perfectly making the design is 
easy to extend and maintain (if some punctual principles are violated, the trade-oﬀ is somewhat 
justiﬁed in the design rationale. All relevant requirements have been addressed.
6 marks - The implementation involves one or two minor violations of design principles (could 
be easily ﬁxed) across all functional expectations as per the relevant requirement(s) (e.g., some 
attributes are not set to private without any justiﬁcation). All relevant requirements have been 
addressed.
5 marks - The implementation involves minor violations of design principles in multiple places 
(could still be easily ﬁxed) across all functional expectations as per the relevant requirement(s). All 
relevant requirements have been addressed. 
4 marks - The implementation involves one or two non-severe violations of design principles 
that could be implemented in a better way (no trade-oﬀs are convincingly provided in the 
design rationale) across all functional expectations as per the relevant requirement(s) (e.g. some code repetitions are found in the implementation that would require some refactoring to be ﬁxed). All 
relevant requirements have been addressed.
3 marks - The implementation involves non-severe violations of design principles in multiple 
places (no trade-oﬀs are convincingly provided in the design rationale). All relevant requirements 
have been addressed.
2 marks - The implementation involves one or two severe violations of design principles that could 
be implemented in a better way across all functional expectations as per the relevant requirement(s), 
e.g. violating the basic principles covered so far. Fixing them would require substantial refactoring. 
Alternatively, not all relevant requirements have been attempted. 
1 mark - The design/implementation can be considered hacky or various instances of procedural 
programming are found. For example, the implementation uses downcasting and ‘instanceof’ in 
various cases without a convincing justiﬁcation. Alternatively, it can also be the case that abstraction 
is not used, making the design diﬃcult to extend and maintain. Alternatively, only some relevant 
requirements have been attempted. 
0 marks - The implementation mainly follows a non-OO paradigm; or the UML class diagram(s) or the 
implementation is missing. Alternatively, most relevant requirements have not been attempted. 
Design rationale (4 points)
4 marks - The design rationale includes a description of what has been done and why, focusing on 
the principles and concepts taught in the unit (such as DRY and SOLID principles) and not in terms of 
game design. The rationale discusses the advantages and disadvantages of the design (pros and 
cons), the reasons for choosing the current design, and ways in which it can be easily extended 
(e.g. my design achieves OCP because if a new character is added in the future ...). All relevant 
requirements have been addressed.
3 marks - The rationale describes what has been done and why, based on the principles and 
concepts taught in the unit. It also includes some discussion of the pros and cons of the design and 
the reasons for the current design choice but lacks examples of future extensibility. All relevant 
requirements have been addressed.
2 marks - The rationale describes what has been done and why, aligning with the principles and 
concepts taught in the unit. However, it lacks a discussion on the pros and cons of the design 
and/or examples of future extensibility. All relevant requirements have been addressed.
1 mark - The rationale primarily describes what has been done without a thorough explanation 
of the decision-making reasons. For instance, it may mention design principles ad concepts without 
providing convincing explanations, discussion of pros and cons, or examples of how the system can 
be extended. Alternatively, not all relevant requirements have been attempted. 
0 marks - The design rationale is either very challenging to read, is missing, or the submitted work omits more than one relevant requirement.
Integration with the existing system (2 points)
This item applies across all relevant requirements.
2 marks - The implementation eﬀectively uses the engine classes (e.g. the submitted work 
demonstrates that the students understand the diﬀerence between actions and behaviours). All 
relevant requirements have been addressed.
1 mark - The implementation does not use some engine classes as intended (e.g. behaviours are 
created for some actions that do not need it, such as actions performed by the player) or includes 
custom classes for functionality that could be implemented with the engine class (e.g. 
created a custom ground class instead of using the ground class given in the engine package). Most 
relevant requirements have been addressed.
0 marks - The engine has been modiﬁed in a minor or signiﬁcant way OR the UML class diagram OR 
the implementation is missing
UML syntax and clarity (2 points)
This item applies across all relevant requirements.
2 marks - Relevant (static and/or dynamic) diagrams are perfect in terms of syntax, with no 
missing multiplicities, correct arrowheads for all relationships, and appropriate usage of realisation 
for classes implementing interfaces, generalisation for classes or interfaces inheriting others, etc. 
Diagram formatting is consistent and clear. All requested diagrams have been submitted.
1 mark - Diagram(s) contain some minor syntax errors, such as missing multiplicities for several 
associations, inappropriate use of generalisation for classes implementing interfaces, realisation for 
classes extending others, or classes extending multiple classes, etc. Nonetheless, the design can still 
be understood by the TA with a little eﬀort. Alternatively, there are several inconsistencies across 
diagrams. All necessary diagrams have been submitted.
0 marks - Diagram(s) are signiﬁcantly hard         
加QQ：99515681  WX：codinghelp
