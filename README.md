users = ("Osterejen", "Nobel", "Zilen", "Æman") # should probably be adictionary for now so that we can add passwords 
#games = open("games.txt")
user = input("Enter user information: ")

def addgame(game):
    games = open("games.txt") #this needed to be updated to work with csv/tables information
    if game in games:
        print("Game is already on the list: %s" %games.read())
    else:
        with open("games.txt", "a+") as games:
            games.write("\n %s" %game)
            games.seek(0)
            print("Updated list of games: %s" %games.read())
        #games.append(game)
        #print("Updated list of games: %s" %games)
    games.close()
 
if user in users:
    onetwo = input("would you like to check your current ranking press 1, entering new results press 2, or change game settings 3:  ")
    if int(onetwo) == 1:
        print("You are number ##!")
    elif int(onetwo) == 2:
        print("Insert result of your game here!  ") # add to a table
    elif int(onetwo) == 3:
        game = input("Which game would you like to add?  ")
        addgame(game)
    else:
        print("You did not type 1, 2 or 3 we don't understand your command please start over") ## possibility of recalling this entire process automatically? 
else:
    print("Not a valid user")

