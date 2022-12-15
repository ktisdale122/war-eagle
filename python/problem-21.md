challenge_tictactoe_server_restoration_v1
In this challenge, you are asked to support the ABC Tic Tac Toe game, who recently faced a server crash. You need to help them restore the data and the game restores with all the winnings and player stats.
There is an event log that can be used to restore the game stats and player stats.
Note

Before submitting to hobbes please update the file path to have "app/src/" before filename like "app/src/<filename.extension>"

At this stage of the challenge you are expected to demonstrate the concepts like:

Reading and writing structured data like CSV and JSON
Reliable exception handling
Defining data structures to solve the problem

Event Logs are provided to you in the format of csv (game_events.csv).
TimeStamp,GameId,PlayerId,Coodinate1,Coodinate2 

T001,G0001,P001,1,1 

T002,G0001,P002,1,2 

T003,G0001,P001,0,0 

T004,G0001,P002,2,2 

T005,G0001,P001,2,0 

T006,G0001,P002,0,1 

T007,G0001,P001,0,2
There is timestamp to denote the time a move was made by the players. The GameId denotes the game played by the 2 players P0001 and P0002. The move on the square is shown by those numbers. The coordinates are given as below.

Tic Tac Toe Voard and moves:-


Part 1
As the first task, read the CSV data and create the game report for each game played so far in separate json file with file name tictactoe_(gameid).json. like tictactoe_G0001.json
The game events csv has only co-ordinates of the box you played in the tic tac toe board. You will have to evaluate the winner for each game separately.
You may use the list below, which shows possible winning moves to evaluate whether the moves played by a given player is winning or not.
possible_win_moves = [ 

    [(0,0),(1,0),(2,0)], 

    [(0,0),(0,1),(0,2)], 

    [(0,0),(1,1),(2,2)], 

    [(0,1),(1,1),(2,1)], 

    [(0,2),(1,2),(2,2)], 

    [(0,2),(1,2),(2,2)], 

    [(0,2),(1,1),(2,0)], 

    [(1,0),(1,1),(1,2)], 

    [(1,0),(1,1),(1,2)] 

] 
The json file of all the individual games contains the following content.
output file sample
{
    "game": "G0009", 
    "winner": "P005", // id of the player who won the game, if it’s a draw it will be empty
    "game_status": "COMPLETED", // containing status like “COMPLETED”, “DRAW”.
    "players": ["P005", "P002"] // showing list of player ids who played that game.
}

Part 2
Now, we need to calculate the player statistics next.
Create a json file player_stats.json giving the player stats of every person with each item having playerid and their respective dictionary item containing their stats.
output file sample
{
    "<playerid>": {
        "matches_played": <int>, 
        "matches_won": <int>, 
        "matches_lost": <int>, 
        "matches_drawn": <int>
    }
}
