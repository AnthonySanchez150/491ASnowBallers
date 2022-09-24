# Use Cases

| Use Case 1 P0              | Launch Game  |
|:----------------------------|:------------|
| Actors                      | User        |
| Pre-Conditions              | No running instance of game exists, User launching game from a windows desktop|
| Post-Conditions             | The game is now running |
| Error-Condition             | Game fails to launch, windows exe error window displays |
| Non-Functional Requirements | Game should launch within 5-10 seconds |

| Use Case 2 P1                | Host a lobby|
|:----------------------------|:------------|
| Actors                      | Host        |
| Pre-Conditions              | Host must create a connection to the network|
| Post-Conditions             | Lobby created by host is now joinable, This user is now marked as host, Display success or failure based on if lobby is established |
| Error-Condition             | Network connection failure |
| Non-Functional Requirements | Host a lobby with a push of a button, lobby should be available in 5 seconds |

| Use Case 3 P1               | Connect to lobby|
|:----------------------------|:------------|
| Actors                      | Client        |
| Pre-Conditions              | Lobby must be created by a host|
| Post-Conditions             | Players are connected in a lobby on a network, Display a failure or success to lobby connection|
| Error-Condition             | Network connection failure, User enter wrong information, Host leaves and server closes, Host + Client connection failure |
| Non-Functional Requirements | Client should be able to connect via IPs, Client connects within 5 seconds to lobby |

| Use Case 4 P2               | Disconnect a lobby|
|:----------------------------|:------------|
| Actors                      | Client       |
| Pre-Conditions              | Client is connected to host, Press disconnect from host button or client closes game|
| Post-Conditions             | Client is disconnected from host lobby, Network connection terminates, Return to main menu if still in game |
| Error-Condition             |  |
| Non-Functional Requirements | Client can disconnect from lobby within 5 seconds|

| Use Case 5 P2              | Close lobby|
|:----------------------------|:------------|
| Actors                      | Host       |
| Pre-Conditions              | Host is hosting a lobby, Press disconnect from lobby or close game|
| Post-Conditions             | Host disconnects from lobby, Network connection terminates, Return to main menu if still in game|
| Error-Condition             |  |
| Non-Functional Requirements | Host can close and disconnect from network within 5 seconds|

| Use Case 6 P0              | Play game|
|:----------------------------|:------------|
| Actors                      | Host       |
| Pre-Conditions              | Lobby connection established, Host starts game|
| Post-Conditions             | Host + client spawn into level|
| Error-Condition             |  Network connection failure, Host + client connection failure|
| Non-Functional Requirements | Play game should be a button that the hosts presses to start spawning players in level, Game should start within 10 seconds after button is pushed|

| Use Case 7 P0               | Spawn players|
|:----------------------------|:------------|
| Actors                      | Host + Client    |
| Pre-Conditions              | Host started game, Lobby connection established|
| Post-Conditions             | Players can play the game|
| Error-Condition             | Network connection failure, Host + client connection failure, Virtual Reality connection failure|
| Non-Functional Requirements | Game will last 3 minutes, Game will end when win condition is met or time runs out|

| Use Case 8 P1               | Hit User|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | User hit other with snowball|
| Post-Conditions             | Increment score for that player|
| Error-Condition             | Hit detection failure, Server to client communication errors|
| Non-Functional Requirements | The game should register the hit as soon as contact is made|

| Use Case 9 P2                | "Reload" Snowball|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | User does not have snowball to throw|
| Post-Conditions             | Increment snowball for player|
| Error-Condition             | Server to client communication errors|
| Non-Functional Requirements | The game should register that the player now has a snowball|

| Use Case 10 P2                | Movement|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | User presses a movement button on controller|
| Post-Conditions             | IMove users object and children based on direction|
| Error-Condition             | Server to client communication errors, Network lag, VR to PC delays|
| Non-Functional Requirements | This movement should register and perform as soon as the users inputs a movement|

| Use Case 11 P0                | End Game|
|:----------------------------|:------------|
| Actors                      | Host + Client   |
| Pre-Conditions              | Game winning condition met (5 snowballs hit) or time limit has been reached|
| Post-Conditions             | Declare user who won on screen, Return to menu|
| Error-Condition             | Network connection failure, Host + client connection failure|
| Non-Functional Requirements |Game end sequence will display text and/or animated sprites of winner|

| Use Case 12 P1                | Return to menu|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | End game sequence finished|
| Post-Conditions             | User disconnected from server, return each user to main menu|
| Error-Condition             | Network connection failure|
| Non-Functional Requirements |Game should disconnect within 10 seconds of game ending|

| Use Case 13 P0                | Close game|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | User presses close game button|
| Post-Conditions             | Execution file closes|
| Error-Condition             | Windows exe error|
| Non-Functional Requirements |Game should close within 5 seconds of pressing button|


| Use Case 14 P2               | Enter game settings menu|
|:----------------------------|:------------|
| Actors                      | User   |
| Pre-Conditions              | Menu not shown to user, user presses options button|
| Post-Conditions             | The game settings now display for the user|
| Error-Condition             | Game settings menu does not load|
| Non-Functional Requirements |Settings menu should display within 2-5 seconds, All supported setting option should display|
