## List of Classes
# Boundary objects
Main Menu - will hold the buttons to other menus, can show the UI to the player

Network Player - Holds all of the players components and keeps track of how they move in VR.

XRGrabInteractable - Allows the snowball to be grabbed online

# Control Objects
Game Manager - Keeps tracks of gameplay related score, if the game will continue, or if the game is ready to start

Network manager - Relays all information from both host and client. Connects to the network and establishes a connection to the lobby

Network Player Spawner - Holds functions that will be called when players join and leave room

Hand presence - Placed on the plates hands. Hold all of the animations and players controller inputs.

# Entity Objects
Player - Will hold all our variables that associate with the player. Can modify variables based on gameplay.

PlayerHand - Will be placed on the hands of our players. Will be able to get position of the players hands and their controller type

Score - Reference to score, allows the game manager to get score, keeps track of time

Snowball - The object that can damage a player. Can modify score and modify players health on collision.

Lobby - Creates a lobby that players are able to join and leave and destroys self when all players leave
