# CATCHPHRASE SOCKET PROJECT

## Intro
The Catchphrase game is a multi-player game, where the players need to guess a secret word. The game needs to work in different clients, meaning live client-to-client communication (two separate browser tabs/windows).



Each turn, a player is presented with a secret word that they need to describe to the other player via chat. The second player then needs to guess what the secret word is.



Guessing the correct word will win the player 10 points.



Each user can start a new game or join an existing one.

***

## Socket IO

For this project you will need to use Socket.io.

As their documentation states: "*Socket.IO enables real-time, bidirectional and event-based communication".*

In other words it means, that until now, when we wanted to receive data from the server, we had to make a GET request, and wait for the data. But, what happens if we are using an app, and the server wants to send a notification or message to the app without getting an action from the user? That's where we can use socket.io.

This service enables us to use real time communication, such as, notifications, messages (chat), analysis and more. You can read more about it [here](https://socket.io/).

For this project, you will need to read about [rooms](https://socket.io/docs/rooms-and-namespaces/#Rooms), which can allow socket to 'emit' something to a group of people (who are in the same room), for instance, when a user sends a message to a group, everyone in the group (or in the room - in socket.io language), will receive this message.

You'll want to use rooms in this project so that you can have more than two players play in the same game.

***

## Game Structure

Before beginning to write any code, please read through all the instructions and check out the screenshots to understand the architecture. It is also recommended to draw out the architecture on a piece of paper before you start coding.

Client

The client side comprises of two parts:

1.  Join or create a game: In this part the user must add their name, and then click on 'create a game' or 'join a game'.
2.  The game board, which includes:
3.  A chat room - an area where the users can chat together
4.  A 'Get Secret Word' button - clicking this will give the user a secret word that they will need to describe to the other players
5.  You can append the secret word to the chat area (only for the player who is describing the word)
6.  Score view - list of all the players and their scores

*Note*: Not all these things will need socket. Some can just use regular routing.

* * * * *

Server

On the server side you will need to handle the following (and more) options with socket.io:

-   Login of a user - add the user to a data structure when they click 'create/join a game'
-   No need to use a DB, just store it on the server
-   New game - when the user chooses to create a new game you must handle this on the server
-   Join game - when the user decides to join another game, you will need to add them to the correct game and let the other users know that they have joined (think of how when someone joins a Whatsapp group you get notified)
-   New message - when a player sends a message
-   You will need to check if it's a guessing message or a describing message
-   If necessary:
    -   Add points to the correct player
    -   Change turns
    -   Let the players know the guess was correct

Feel free to add more functionality and to handle more edge cases.

Here are some screenshots for inspiration:

![](https://kernel-files.s3-eu-west-1.amazonaws.com/images/PROD_A2394-0.png)

![](https://kernel-files.s3-eu-west-1.amazonaws.com/images/PROD_A2394-1.png)

![](https://kernel-files.s3-eu-west-1.amazonaws.com/images/PROD_A2394-2.png)

![](https://kernel-files.s3-eu-west-1.amazonaws.com/images/PROD_A2394-3.png)