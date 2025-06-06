# <p align="center"><ins> Final Project Card Game </ins></p>
## <p align="center"><ins> Game: Guess the Suit: The Ultimate Card Challenge!!! </ins></p>
### **<ins> Rules of the Game </ins>**
1.  Start by Guessing the Suit of a Card (Pick from the 4 in the Suit List).
2.  Each player starts with 100 dollars.
3.  The cost per attempt to guess the suit is 20 dollars.
4.  Everyone starts with 0 correct. If you get it wrong, you still have 0 correct (no deduction for incorrect answers).
5.  The players must keep playing until their current balance is 0 and they will be informed when they reach that spot.
6.  After the players reach a current balance of 0, they will know their final score.
7.  After knowing the final score, then they will see if their name and score are on the leaderboard. The leaderboard has the highest player's name and score.
8.  The players can even upload the scorefile.txt to see their or whoever's name and score for having the highest score.

```{python}
print("I pledge my honor that I abided by the Stevens Honor System by Deep Shah")
print("Please make sure to capitalize the first letter of the suit")

import random #Importing the Random Library

class Card(): #Created a Class called Card
    suit_list = ["Clubs", "Diamonds", "Hearts", "Spades"] 
    def __eq__(self, Guess_Suit): #Checking if two cards are equal
        return (self.suit == Guess_Suit.suit)
    def __init__ (self, suit = 0): #Initalizes the suit of the card to have a default value of 0 if there is no suit provided
        self.suit = suit
    def __str__ (self): #Returns the string of the suit based on its index value of self.suit
        return (self.suit_list[self.suit])
    def __updatex__(self): #Checks if the player inputs a valid suit from the suit_list
        suit_list = ["Clubs", "Diamonds", "Hearts", "Spades"]
        while True:
            Guess_Suit = input("Choose the suit you think it will be: ")
            if Guess_Suit.capitalize() in suit_list:
                print("Nice Choice, Good Luck")
                return Guess_Suit
            else:
                print("Incorrect Input, Please Try Again")

class Deck(): #Created a Class called Deck
    def __init__(self): #Creates 4 cards, one for each suit, and adds it to the self.cards list. 
        self.cards = []
        for suit in range(4):
                self.cards.append(Card(suit))
    def __str__(self): #Creates a string of all cards, adding spaces before each card based on its position/index value
        s = ""
        for i in range(len(self.cards)):
            s += i * " " + str(self.cards[i]) 
        return s
    def shuffle(self): #Shuffles the cards in the self.cards list
        n_cards = len(self.cards)
        for i in range(n_cards):
            j = random.randrange(0, n_cards)
            self.cards[i], self.cards[j] = self.cards[j], self.cards[i]
    def pop_card(self): #Removes a card from the self.cards list
        return self.cards.pop()
    def is_empty(self): #Checks if the self.cards list is empty
        return len(self.cards) == 0
    def deal(self, hands, n_cards = 52): #Deals out the cards to the players that are playing evenly
        n_players = len(hands)
        for i in range(n_cards):
            if self.is_empty():
                break
            card = self.pop_card()
            current_player = i % n_players
            hands[current_player].add_card(card)

class Hand(Deck): #Created a class called Hand that inherits from the Deck class
    def __init__(self, name = ""): #Initalizes self.card as a list and self.name based on the player's input
        self.cards = []
        self.name = name
    def add_card(self, card): #Adds a card to the self.cards list
        self.cards.append(card)
    def __str__(self): #Outputs the player's name with 's Card Suit is followed by the card's suit or a message indicating it is empty
        s = self.name + "'s Card's Suit is "
        if self.is_empty():
            return s + " is empty"
        s += Deck.__str__(self)
        return s
    def __stringhand__(self): #Returns the cards and their suits
        return Deck.__str__(self)

class CardGame(): #Created a class called CardGame
    def __init__(self):
        self.deck = Deck()
        self.deck = shuffle()
        
def Highest_Score(Name, player_score): #Create a function to update the highest score for the players and save it to a file
    highest_score = {} #Created an empty dictionary to store the highest score
    file = open("scorefile.txt", "a") #Created a file called scorefile if it doesn't already exist
    file.close()
    with open("scorefile.txt", "r") as file: #Reads the file line-by-line, splits each lines into key and values, and stores the highest_score dictionary. 
        for line in file:
            S = line.strip().split(":")
            PlayerName = S[0] #Key
            HighestScore = S[1] #Value
            highest_score[PlayerName] = HighestScore
        if highest_score == {}:
            highest_score[Name] = player_score
        else: 
            if player_score > int(HighestScore):
                del highest_score[PlayerName]
                highest_score[Name] = player_score
    with open("scorefile.txt", "w") as file:
        b = list(highest_score.keys())
        c = list(highest_score.values())
        file.write(f"{b[0]}:{c[0]}")
    return highest_score

def main():
    player_starting_amount = 100 #player starts with 100 dollars
    cost_per_attempt = 20 #The cost per guess is 20 dollars
    player_score = 0 #Each player starts with 0 dollars
    first_name = input("What is your first name?") #Asking player for first name
    last_name = input("What is your last name?") #Asking player for last name
    Name = first_name.strip().capitalize() + " " + last_name.strip().capitalize() #Combining the player's first and last name
    while player_starting_amount > 0:
        d = Deck() #d is an instance of Deck
        c = Card() #c is an instance of Card
        x = c.__updatex__() #Calls the function above to update x after each guess
        print("Your guess is " + x)
        d.shuffle() #Shuffle the deck
        hand = Hand(Name) #Establishing the people that want to be in the game (This is a one-player game)
        hands = [hand]
        d.deal(hands, 1) #Deals out the card to the player playing
        print (hand) 
        if x == hand.__stringhand__(): #Checking if the player's guess matches the randomized card
            print("Correct, Nice work!")
            player_starting_amount = player_starting_amount + cost_per_attempt
            print(f"Your current balance is: ${player_starting_amount}") #f can used for string formatting.
            player_score = player_score + 1
        else:
            print("Incorrect! You just lost 20 dollars. Try Again!")
            player_starting_amount = player_starting_amount - cost_per_attempt
            print(f"Your current balance is: ${player_starting_amount}") 
    print (f"The final score for the player is: {player_score}")
    y = Highest_Score(Name, player_score) #Creates a dictionary with the player's name as key and highest score as value
    z = list(y.keys()) #Converts the player's name into a list
    a = list(y.values()) #Converts the highest score into a list
    print("Leaderboard: ")
    print(f"Name: {z[0]}")
    print(f"Highest Score: {a[0]}")

main()    
```
