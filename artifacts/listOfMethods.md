1. User

    1.1 Method: getHealth
	
	    1.1.1 Description: Returns the current health value of the user in the server
	
	    1.1.2 Preconditions: User must have a health value assigned in the server
 
	    1.1.3 Postconditions: User’s health float is returned to the control object

	    1.1.4 Signature: Float getHealth();

    1.2 Method: getPosition
	
	    1.2.1 Description: Returns the current position of the user in the server

	    1.2.2 Preconditions: User’s position must be in the server
	
	    1.2.3 Postconditions: User’s position is returned to the control object

	    1.2.4 Signature: Transform getPosition();

    1.3 Method: modifyHealth
	
	    1.3.1 Description: Updates the health value of the user stored in the server
	
	    1.3.2 Preconditions: User’s health must be greater than zero in the server
 
	    1.3.3 Postconditions: User’s health is updated in the server

	    1.3.4 Signature:void modifyHealth();

    1.4 Method: getPlayerName
	
	    1.4.1 Description: Returns the name of the user stored in the server
	
	    1.4.2 Preconditions: User’s name must be in the server
 
	    1.4.3 Postconditions: User’s name is returned to the control object

	    1.4.4 Signature: String getPlayerName();

    1.5 Method: getScore
	
	    1.5.1 Description: Returns the score of the user stored in the server
	
	    1.5.2 Preconditions: User’s score must be in the server
 
	    1.5.3 Postconditions: User’s score is returned to the control object

	    1.5.4 Signature: Int getScore(); 

2. User Hands

    2.1 Method: getPosition
	
        2.1.1 Description: Returns the position of the user’s hands stored in the				 server

	    2.1.2 Preconditions: User’s hand positions must be in server

	    2.1.3 Postconditions: User’s hand positions are returned to the control object

	    2.1.4 Signature: Transform getPosition();

    2.2 Method: getControllerType
	
        2.2.1 Description: Returns the type of controller the user is using 

	    2.2.2 Preconditions: The stock entity has already been created and stored in the server

	    2.2.3 Postconditions: Returns the controller type as a string 

	    2.2.4 Signature: String getControllerType();

    2.3 Method: updateHandAnimation
	
        2.3.1 Description: Updates the user hand animations for every frame in the game

	    2.3.2 Preconditions: User’s hand positions must be in the server

	    2.3.3 Postconditions: Position and animation of the user’s hand is updated in the server

	    2.3.4 Signature: void updateHandAnimation();

3. Game

    3.1 Method: startGame
	
        3.1.1 Description: Starts the game for the room (lobby) of users (players)

	    3.1.2 Preconditions: The minimum number of of users are in the lobby and the host user calls this method

	    3.1.3 Postconditions: The users are set in a starting position and the game begins

	    3.1.4 Signature: void startGame();

    3.2 Method: endGame
	
        3.2.1 Description: Ends the current game between two users

	    3.2.2 Preconditions: The game is running, one user reaches the score limit, or one user exits the game

	    3.2.3 Postconditions: The game is closed and users are returned to the lobby 

	    3.2.4 Signature: void endGame();

    3.3 Method: assignPlayers
	
        3.3.1 Description: assigns each user to a player model

	    3.3.2 Preconditions: both users are connected to the server

	    3.3.3 Postconditions: players have control over the models when the	game starts

	    3.3.4 Signature: void assignPlayers();

    3.4 Method: chooseWinner
	
        3.4.1 Description: The winner of the game is declared to both users

	    3.4.2 Preconditions: One of the users has reached the score limit

	    3.4.3 Postconditions: The game is ended and the winner is shown in a message to both users

	    3.4.4 Signature: void chooseWinner();

4. Snowball

	4.1 Method: hurtOnCollision

		4.1.1 Description: The player throwing a snowball hits the opposing player

		4.1.2 Preconditions: the snowball and player are registered on the server

		4.1.3 Postconditions: the snowball is deleted, hit players health is updated, and throwing players score is incremented on the server

		4.1.4 Signature: void hurtOnCollision();

	4.2 Method: incrementScore

		4.2.1 Description: increments the score of the player that successfully	lands a snowball

		4.2.2 Preconditions: The server registers that a player is hit with a snowball

		4.2.3 Postconditions: The score is updated on the server

		4.2.4 Signature: void incrementScore();

	4.3 Method: onSelectEnter

		4.3.1 Description: allows the user to interact with the snowball on selecting enter

		4.3.2 Preconditions: The users player model and a snowball are registered on the server

		4.3.3 Postconditions: The player model interacts with the snowball

		4.3.4 Signature: void onSelectEnter(XRBaseInteractor)

	4.4 Method: selectPlayerAsOwner

		4.4.1 Description: selects player with snowball as owner of the snowball

		4.4.2 Preconditions: the player is holding an unowned snowball

		4.4.3 Postconditions: the snowball registers as the players

		4.4.4 Signature: void selectPlayerAsOwner()

5. Network

	5.1 Method: connectToServer
		
		5.1.1 Description: Attempts to connect a user to a server

		5.1.2 Preconditions: A server is running and established

		5.1.3 Postconditions: The user attempting to connect, successfully							 connects

		5.1.4 Signature: void connectToServer()

	5.2 Method: onConnectedToMaster
		
		5.2.1 Description: notifies and establishes connection to server where a game room is created

		5.2.2 Preconditions: an attempt to connect to the server is being made

		5.2.3 Postconditions: A game room lobby is created 

		5.2.4 Signature: void onConnectedToMaster()

	5.3 Method: onJoinedRoom
		
		5.3.1 Description: notifies when the user has joined a room

		5.3.2 Preconditions: user is attempting to join a room

		5.3.3 Postconditions: user is added into the room

		5.3.4 Signature: void onJoinedRoom()

	5.4 Method: onLeftRoom
		
		5.4.1 Description: notifies when the user has left a room

		5.4.2 Preconditions: user closes game or chooses to exit room

		5.4.3 Postconditions: user is removed from the room

		5.4.4 Signature: void onLeftRoom()

	5.5 Method: initializeRoom
		
		5.5.1 Description: creates a game room

		5.5.2 Preconditions: the user chooses to create and host a game room

		5.5.3 Postconditions: the room is created

		5.5.4 Signature: void initializeRoom();

	5.6 Method: onPlayerEnteredRoom
		
		5.6.1 Description: notifies the user when a new player joins the room

		5.6.2 Preconditions: a new player successfully joins the room

		5.6.3 Postconditions: none

		5.6.4 Signature: void onPlayerEnteredRoom()