# dont_get_angry_2d_board_game
Features
---------
- can be played by 2, 3 or 4 people
- offline mode "you vs the all-mighty-computer"
- online mode available

Forever-alone-guy part
----------------------
- the client and the server will be ran on the player's computer
- there will be an extra module, which will work like if the other players are normal

Network part
------------
- client-server architecture
- the server is ran on one of the player's PC
- the game logic works on the server
- the clients give all the data needed to the server


Realization
----------
- back end
  - table class
    - stores the table representation
    - stores the positions of all the 'pionki'
  - 'pionka' class
    - stores the possiosion of the 'pionka'
    - stores the player, who is the owner of the 'pionka'
  - dice class
    - function for random throw
  - logic class(might end up as a function or a standalone module)
    - gets the info from the client, does some calculations(like 'pionka' removal) and returns the result back
  - robot-player class
    - uses a random name
    - implements method for self-playing(using the logic class)
  - main server functions
    - the client sends msg, containing the player name and the dice roll
    - the server accepts it and checks if it is the right client(optional)
    - then it runs it trough the logic and makes the needed calculations
    - in the end he generates the answer(json format most likely), so he can update the front-end part
    - the server replies with the answer, generated on the previous step, so the front end part can be drawn


- front end
  - operation
    - the 'owner' of the game creates the server and sets the max interval(time) for decision
    - when a user connects to the server, the server returns a unique identifier(id) for his turn
    - then the current user's 'Throw' button is blocked unitl time.id is passed
    - after that you can press 'Throw', choose which ('pionka :D') to move and send the info to the server
    - after it's send, you go to point 3)
    - on every 'time' seconds the client asks the server for the board, so he can check for updates

