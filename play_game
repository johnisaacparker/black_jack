import random
from DeckOfCards import DeckOfCards #gives access to the DeckOfCards class

game = 0
while game == 0:
    
    #calls the DeckOfCards class to generate the deck for the game
    deck = DeckOfCards()
    
    print("Welcome to the Blackjack world championship!!! \n")
   
    print("Deck before shuffle: \n")
    deck.print_deck() 
   
    deck.shuffle_deck() 
    
    print("\nDeck after shuffle: \n")
    deck.print_deck() 
    
    # deal two cards to the user
    card = deck.get_card()
    card2 = deck.get_card()
    
    score = 0
    # calculate the user's score
    score += card.val
    score += card2.val
    
    #assigns the dealer's score by generating a random number between 17 and 23
    dealer_score = random.randint(17, 23)
    
    print("\nCard number 1 is: ", card)
    print("Card number 2 is: ", card2)
    print("Your score is: ", score, "\n")
    
    #logic for when the user wants another card
    hit_tracker = 0
    while hit_tracker == 0:
        
        hit = input("would you like a hit? (y/n)")

        #if the user decides to take a hit
        if hit == "y":
            
            #call function get_card from DeckOfCards to get user another card
            card3 = deck.get_card()
            
            #logic to turn an ace's value to 1 if user will bust with an 11
            if card3.face == 'Ace':
                if score + 11 > 21:
                    card3.val = 1
                else:
                    pass
            else:
                pass
            
            score += card3.val
            
            print("New card is: ", card3)
            print("new score: ", score, "\n")
            
            #logic to end the game if user 'busts'
            if score > 21:
                print("Busted! You lose.\n")
                hit_tracker += 1
                break
            else:
                pass
    
        
        #logic to score game when user is done taking hits
        else:
            #trigger termination condition to end 'hit' while loop
            hit_tracker += 1
            
            print("dealer score: ", dealer_score)
            
            #if dealer busts, user wins
            if dealer_score > 21: 
                print("Dealer busted. YOU WIN!!!!!")
                    
            #if dealer score is higher, user loses
            elif dealer_score > score: 
                print("Dealer score is higher. You lose!")
                    
            #if dealer has the same score, user loses
            elif dealer_score == score:
                print("You got the same score as the dealer, but you lose anyway. Haha, you lose!")
            
            #if user has a higher score and didn't bust, user wins      
            else: 
                print("Your score is higher. YOU WIN!!!!!!")
   
    another_game = input("Another game? y/n")
    
    #if yes, loop continues
    if another_game == "y":
        pass
    
    #if no, end the loop
    else:
        print("Thanks for playing!")
        #termination condition to end 'game' while loop
        game += 1
