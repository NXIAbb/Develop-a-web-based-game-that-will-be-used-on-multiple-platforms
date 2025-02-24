Download link :https://programming.engineering/product/develop-a-web-based-game-that-will-be-used-on-multiple-platforms/


# Develop-a-web-based-game-that-will-be-used-on-multiple-platforms
Develop a web-based game that will be used on multiple platforms
Executive Summary

The gaming Room wants to develop a web-based game that will be used on multiple platforms. They currently have an android-based version of the game. The development of this application needs to be streamlined. The game will include an option to play with a single team or multiple teams. It also must prevent users from creating duplicate team names.

Requirements

A game will have the ability to have one or more teams involved.

Each team will have multiple players assigned to it.

Game and team names must be unique to allow users to check whether a name is in use when choosing a team name.

Only one instance of the game can exist in memory at any given time. This can be accomplished by creating unique identifiers for each instance of a game, team, or player.

Design Constraints

Consistent Gameplay for both a single team or more than one team, this will require the development team to implement the Game class in a way that supports multiple teams, such as using a list of teams rather than a single team attribute.

Players must be grouped within a team, again this will require the development team to add an attribute to team class will which players are on that team, additionally players may also need to contain an attribute with their team.

Players within the same team receive the same information, this will require a way for the game class to communicate with all the players on a team, this could be done using a teams class.

Check for game and team names to prevent duplicates. The implications of this is likely a list of team names will need to be maintained, in order to check for repeated names before instantiation. The Game object should instead adopt a singleton pattern, to prevent duplicate instantiations.

System Architecture View

<Please note: There is nothing required here for these projects, but this section serves as a reminder that describing the system and subsystem architecture present in the application, including physical components or tiers, may be required for other projects. A logical topology of the communication and storage aspects is also necessary to understand the overall architecture and should be provided.>

Domain Model

The Entity class is used as an outline for its child classes: Game, team and Player. It contains relevant information we will use, such as id, name, and a toString() method. Game, team and Player will inherit these attributes from Entity so we can give them an id and name. These classes may overload the toString() method to display the relevant class type. This will make our code easier to understand and more efficient when programming classes as less information will be repeated. Additionally, it still allows for flexibility in the child class definitions.

2


In addition to the attributes listed above, the Game class also includes a list of teams, a constructor, as well as the ability to add teams. As we can see on the UML diagram, the game can have none to many teams.

Similarly, the Team class includes a list of players, a constructor, and a method to add players to the team. This is also shown on the diagram as a team can have none to many players.

Finally, the Player class contains a constructor.

The Game service object implements the singleton pattern, which restricts it from being instantiated multiple times. It contains a list of Games, the Id of the next game, the id of the next player, and id of the next team. It also allows the user to add a game, get game, view team or player id, and get the number of games. From the diagram, the Game Service class does not inherit from another class in the diagram. It may have none to many Games. Implementing the check internally is more efficient than implementing the check externally, which would require the program driver to contain a GameService attribute.

The program driver contains the main method, which is where program execution will start. The SingletonTester class will test if there only one instance of the GameService class.

Evaluation

Using your experience to evaluate the characteristics, advantages, and weaknesses of each operating platform (Linux, Mac, and Windows) as well as mobile devices, consider the requirements outlined below and articulate your findings for each. As you complete the table, keep in mind your client’s requirements and look at the situation holistically, as it all has to work together.

In each cell, remove the bracketed prompt and write your own paragraph response covering the indicated information.

Client Side

One key

advantage, is the

ability to develop

for both the

MacOS and other

apple products at

the same time. So

if this application

was prepared to

launch on the

MacOS through

Xcode, it could also

be launched on

other Apple

devices. However,

that is also

limitation, since

not all hardware

uses the MacOS.

There are

dedicated Mac

developers, and

because of the

benefit of

developing for

both Mac and Ios

at the same time

the cost is still

reasonable. There

are fewer ways to

test the web app

without a mac

device, although

xcode does provide

a MacOs simulator.

The browser that is

unique to Mac and

Ios devices is

Safari. Some

versions of Safari

require CSS vendor

prefixes(A way for

browsers to locate

features specific to

them), so the

website is

consistent across

all versions.

As we are developing an application that runs almost completely within the browser, the Linux operating system provides sufficient support. Linux-only browsers are less popular than safari or internet explorer, so no additional design considerations are necessary. Linux also has good security, and most customization. One downside is that Linux developments may need specialization based on which distribution and version of linux you plan to use. However, Linux developers are very common, which means that it also would have

lower development cost and shorten development time.

5

Windows is very

commonly used,

so it would apply

to many clients.

Similarly,

windows offer a

large amount of

development

tools to simulate

the Operating

system. Hence,

more developers

are likely to have

experience with

the windows OS,

which lowers the

cost and time

requirements for

developing the

application. The

unique clients we

might encounter

on a windows

computer are

users using

internet explorer

or Microsoft Edge

as their internet

browser. Both of

these are

associated with

being older, so

making sure that

our web

application is

compatible with

previous versions

of these browsers,

while still being

safe and secure

for other users is

essential. This

might include,

supporting longer

response times or

decreasing the

amount of

information sent.

A good solution for

creating mobile

apps with a lower

budget is to design a

cross-plaform

application, or a

progressive web

app, as the Onix-

systems blog

explains.

(Sheremetov 2023)

This means that the

majority of

development is in

the form of web

development, but

the layout and UI is

changed to work

with a mobile

device. However, it

will still require

experts in more

than one OS,

because IOS and

Android applications

use different

development tools.

Which nearly

doubles the cost of

creating the

application(because

in many ways 2

applications are

being created). One

way this can be

leveraged in our

favor is by using the

MacOS to develop

for IOS devices. Or

similarly using the

Linux system to

develop for android

devices. However,

another

disadvantage is

hosting an

application on both

the App Store and

Google Play store

means paying the

required fees for

both of these

services.

Recommendations

Analyze the characteristics of and techniques specific to various systems architectures and make a recommendation to The Gaming Room. Specifically, address the following:

Operating Platform: <Recommend an appropriate operating platform that will allow The Gaming Room to expand Draw It or Lose It to other computing environments.>

Operating Systems Architectures: <Describe the details of the chosen operating platform architectures.>

Storage Management: <Identify an appropriate storage management system to be used with the recommended operating platform.>

Memory Management: <Explain how the recommended operating platform uses memory management techniques for the Draw It or Lose It software.>

Distributed Systems and Networks: <Knowing that the client would like Draw It or Lose It to communicate between various platforms, explain how this may be accomplished with distributed software and the network that connects the devices. Consider the dependencies between the components within the distributed systems and networks (connectivity, outages, and so on).>

Security: <Security is a must-have for the client. Explain how to protect user information on and between various platforms. Consider the user protection and security capabilities of the recommended operating platform.>

Sources:

Butler, R. (2022, February 14). Which OS is Best Suited for Your Development. BairesDev.

Develop Android games. (2023). Retrieved June 12, 2023, from Android Developers website:

https://developer.android.com/games

Gawin, M. (2021, April 23). Best Android App Development Tools & Software. INVO Blog. Retrieved June 12, 2023, from INVO Blog website: https://invotech.co/blog/best-android-app-development-tools-software/

Horne, K. (2021, May 4). Which Operating System Should You Choose for Your Web Hosting Server? Digital.com; Digital.com. https://digital.com/best-web-hosting/operating-systems/

O’Leary, R.(2021, May 5). Is Vendor Prefixing Dead?. https://css-tricks.com/is-vendor-prefixing-dead/.

Sheremetov, D. (2023, April 11). How Much Does It Cost to Make a Mobile App? Onix-Systems.com; Onix. https://onix-systems.com/blog/how-much-does-mobile-app-development-cost

7

Silberschatz, B.,Galvin P.,Gagne G. (2008) Operating System Concepts. 8th Edition.

Team, S. (2022, May 16). Develop Apple Apps: Learn Mac & iOS App Development, Xcode & Swift — SitePoint. Sitepoint.com; SitePoint. https://www.sitepoint.com/develop-apple-apps/

