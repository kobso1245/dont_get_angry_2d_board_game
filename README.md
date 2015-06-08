# dont_get_angry_2d_board_game
Features
---------
- can be played by 2, 3 or 4 people
- offline mode "you vs the all-mighty-computer"
- online mode for 2, 3 or 4 people

Forever-alone-guy part
----------------------
- the PC itself will act both as client and server
- the server will emulate the ammount of players you choose

Network part
------------
- the module 
- client-server architecture, where the server will be one of the clients
- the game logic works on the server
- the clients give all the data needed to the server
- the order is RR-


Realization
----------
- back end
  - table class
    - stores the table representation
    - stores the positions of all the 'pionki'
  - 'pionka' class
    - stores the possiosion of the 'pionka'
    - stores the player, who is the owner of the 'pionka'
    -  
  - dice class
    - function for random throw
  - logic class(might end up as a function)
    - gets the info from the client, does some calculations(like 'pionka' removal) and returns the result back
  - main server functions
    - the client sends msg, containing the player name and the dice roll
    - the server accepts it and checks if it is the right client(optional)
    - then it runs it trough the logic and makes the needed calculations
    - in the end he generates the answer, so he can update the front-end part(could be json format)
    - the server replies with the answer, generated on the previous step, so the front end part can be drawn


- front end
  - 
  - operation
    - the 'owner' of the game creates the server and sets the max interval(id) for decision
    - when a user connects to the server, the server returns a unique identifier(id) for his turn
    - then the current user's 'Throw' button is blocked unitl time.id is passed
    - after that you can press 'Throw', choose which ('pionka :D') to move and send the info to the server
    - after it's send, you go to point 3)

