# Use Cases

| Use Case 1                  | Launch Game |
|:----------------------------|------------:|
| Actors                      | User        |
| Pre-Conditions              | No running instance of game exists, User launching game from a windows desktop|
| Post-Conditions             | The game is now running |
| Error-Condition             | Game fails to launch, windows exe error window displays |
| Non-Functional Requirements | Game should launch within 5-10 seconds |

| Use Case 2                  | Host a lobby|
|:----------------------------|------------:|
| Actors                      | Host        |
| Pre-Conditions              | Host must create a connection to the network|
| Post-Conditions             | Lobby created by host is now joinable, This user is now marked as host, Display success or failure based on if lobby is established |
| Error-Condition             | Network connection failure |
| Non-Functional Requirements | Host a lobby with a push of a button, lobby should be available in 5 seconds |

| Use Case 3                 | Connect to lobby|
|:----------------------------|------------:|
| Actors                      | Client        |
| Pre-Conditions              | Lobby must be created by a host|
| Post-Conditions             | Players are connected in a lobby on a network, Display a failure or success to lobby connection|
| Error-Condition             | Network connection failure, User enter wrong information, Host leaves and server closes, Host + Client connection failure |
| Non-Functional Requirements | Client should be able to connect via IPs, Client connects within 5 seconds to lobby |

| Use Case 4                 | Disconnect a lobby|
|:----------------------------|------------:|
| Actors                      | Client       |
| Pre-Conditions              | Host must create a connection to the network|
| Post-Conditions             | Lobby created by host is now joinable, This user is now marked as host, Display success or failure based on if lobby is established |
| Error-Condition             | Network connection failure |
| Non-Functional Requirements | Host a lobby with a push of a button, lobby should be available in 5 seconds |
