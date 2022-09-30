# Use Cases
## Key Terms
Below is a short list of terms used throughout these use cases.

| Term   | Definition  |
|:----------------------------|:------------|
| Spawn    | When an instance of a player is created within a game. For example, a game can be empty, but when a player spawns in, there is now a player in that game.|
| Host | The user whose network is being used as a server for the game. |
| Client | The user accessing a server that is being hosted by another user. |
| Lobby | A virtual room where one player waits for another player to connect prior to starting the game.
| Reload | Replenish the number of snowballs available to throw. For example, if a player runs out of snowballs to throw, they must reload to get more snowballs to throw.|
| Hit | A snowball collides with a user's collider.|

| Use Case 1 P0               | Launch Game  |
|:----------------------------|:------------|
| Actors                      | User        |
| Pre-Conditions              | No running instance of game exists, User launching game from a windows desktop|
| Post-Conditions             | The game is now running |
| Error-Condition             | Game fails to launch, windows exe error window displays |
| Non-Functional Requirements | Game should launch within 5-10 seconds |

| Use Case 2 P0               | Main menu displays  |
|:----------------------------|:------------|
| Actors                      | User        |
| Pre-Conditions              | User successfully launches the game |
| Post-Conditions             | The main menu displays all the following options for the game: Online, Options, Exit |
| Error-Condition             | Main menu fails to display |
| Non-Functional Requirements | Main menu should display all options and within 5 seconds from launch|

| Use Case 3 P0               | Online menu displays  |
|:----------------------------|:------------|
| Actors                      | User        |
| Pre-Conditions              | User selects Online from the Main menu |
| Post-Conditions             | The Online menu displays all the following options: Host, Connect |
| Error-Condition             | Online menu fails to display |
| Non-Functional Requirements | Online menu should display all options and within 5 seconds from selection|

| Use Case 4 P1               | User hosts/opens a lobby|
|:----------------------------|:------------|
| Actors                      | User/Host        |
| Pre-Conditions              | User selects the Host option from the Online menu. The user/host must create a connection to the network|
| Post-Conditions             | Lobby created by host. This user is now marked as host. Another user can now join this lobby. Display success or failure based on if lobby is established |
| Error-Condition             | Network connection failure. Host fails to open lobby. |
| Non-Functional Requirements | Host a lobby with a push of a button, lobby should be available in 5 seconds |

| Use Case 5 P1               | User joins a lobby|
|:----------------------------|:------------|
| Actors                      | User/Client        |
| Pre-Conditions              | Lobby must already be created by a host. User selects Connect from the Online menu|
| Post-Conditions             | Player connects to a lobby on a network, Display a failure or success to lobby connection|
| Error-Condition             | Network connection failure, User enters wrong information, Host leaves and server closes, Host + Client connection failure |
| Non-Functional Requirements | Client should be able to connect via IPs, Client connects within 5 seconds to lobby |

| Use Case 6 P2               | User leaves a lobby|
|:----------------------------|:------------|
| Actors                      | User/Client       |
| Pre-Conditions              | User/Client is connected to the host. User/Client selects Exit from Lobby menu or exits the game|
| Post-Conditions             | User/Client is disconnected from host lobby, Network connection terminates, Return to main menu if still in game |
| Error-Condition             | Network connection failure. |
| Non-Functional Requirements | User/Client can disconnect from lobby within 5 seconds|

| Use Case 7 P2              | User closes a lobby|
|:----------------------------|:------------|
| Actors                      | User/Host       |
| Pre-Conditions              | User/Host is hosting a lobby. User/Hosts selects Exit from the Lobby menu or closes game|
| Post-Conditions             | Host disconnects from lobby, Network connection terminates, Return to main menu if still in game|
| Error-Condition             | Network connection failure. |
| Non-Functional Requirements | Host can close and disconnect from network within 5 seconds|

| Use Case 8 P0               | User starts a game|
|:----------------------------|:------------|
| Actors                      | Host + Client       |
| Pre-Conditions              | Lobby connection established. Both Host and Client are connected to the lobby. Host selects the Start option from the Lobby menu |
| Post-Conditions             | The game starts for both Host + client |
| Error-Condition             | Network connection failure, Host + client connection failure|
| Non-Functional Requirements | Play game should be a button that the hosts presses to start spawning players in level, Game should start within 10 seconds after button is pushed|

| Use Case 9 P0               | Players spawn into the game|
|:----------------------------|:------------|
| Actors                      | Host + Client    |
| Pre-Conditions              | The game starts. Both Host and Client are in the game.|
| Post-Conditions             | Each player is instantiated within the game, and each player can see one another. |
| Error-Condition             | Players do not successfully spawn or cannot see one another.|
| Non-Functional Requirements | Players spawn into the game within 5 - 10 seconds.|

| Use Case 10 P0               | Timer begins once both players spawn into the game |
|:----------------------------|:------------|
| Actors                      | Host + Client    |
| Pre-Conditions              | Players spawn into the game.|
| Post-Conditions             | The timer starts. |
| Error-Condition             | Timer fails to display or fails to count down. Error message displays. Network connection should err out.|
| Non-Functional Requirements | Timer decrements at the same rate as a standard clock. Timer lasts for 3 minutes. |

| Use Case 11 P1               | Player tosses a snowball|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | Timer starts. User has a snowball available to throw. User swings arm while holding the VR controller|
| Post-Conditions             | Snowball leaves the player's hand and towards the direction of the toss|
| Error-Condition             | Snowball fails to leave the player's hand or goes in the wrong direction. Server to client communication errors|
| Non-Functional Requirements | Physic rules should be applied to the trajectory of the snowball once leaving the player's hand. Snowball toss speed and distance should match the intensity of the throw captured by the VR controller.|

| Use Case 12 P1               | A snowball hits a player |
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | User hits other player with a snowball|
| Post-Conditions             | Increment score for the player that tossed the snowball|
| Error-Condition             | Hit detection failure, Server to client communication errors|
| Non-Functional Requirements | The game should register the hit as soon as contact is made|

| Use Case 13 P2              | A player reloads snowballs|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | User must have less than the max number of snowballs available to carry and hits the reload button|
| Post-Conditions             | Increment snowball for the player|
| Error-Condition             | Server to client communication errors|
| Non-Functional Requirements | The game should register that the player now has a snowball|

| Use Case 14 P2               | A player moves|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | User presses a movement button on controller|
| Post-Conditions             | Move player towards the direction captured by the controller. Users object and children move based on the direction|
| Error-Condition             | Server to client communication errors, Network lag, VR to PC delays|
| Non-Functional Requirements | This movement should register immediately and perform as soon as the users inputs a movement|

| Use Case 15 P0              | The game ends |
|:----------------------------|:------------|
| Actors                      | Host + Client   |
| Pre-Conditions              | Timer runs out. Both players are still in the game. Game winning condition met (5 snowballs hit) or time limit has been reached|
| Post-Conditions             | Display the winner on screen. Return to menu|
| Error-Condition             | Network connection failure, Host + client connection failure|
| Non-Functional Requirements | Game will end when win condition is met or time runs out. Game end sequence will display text and/or animated sprites of winner|

| Use Case 16 P1               | Return to menu after the game ends|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | End game sequence finished|
| Post-Conditions             | User disconnected from server, return each user to main menu|
| Error-Condition             | Network connection failure|
| Non-Functional Requirements |Game should disconnect within 10 seconds of game ending|

| Use Case 17 P0                | Exit the game|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | User selects Exit from Main menu|
| Post-Conditions             | Execution file closes|
| Error-Condition             | Windows exe error |
| Non-Functional Requirements | Game should close within 5 seconds of selecting Exit |


| Use Case 18 P2               | Enter game settings menu|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | Menu not shown to user, user presses options button|
| Post-Conditions             | The game settings now display for the user|
| Error-Condition             | Game settings menu does not load|
| Non-Functional Requirements |Settings menu should display within 2-5 seconds, All supported setting option should display|
