```mermaid
classDiagram
direction RL
Game "1"<|--"2" Hero
Game <|-- "1" Grave
Hero <|--"0.." Deck
Hero <|-- "1" Hand
Hero <|-- "1.." Grave
Deck "inf"<|--"20" Card
Card <|-- CardState
Hand <|-- "0.." Card
class Card{
int id
string type
string description
dict properties
string name
int cost
CardState state
draw()
play()
kill()
}
class CardState{
bool drawn
bool played
bool alive
}
class Game{
    bool win
    list cardsPlayed
    int mana
    int numTurn
    bool drawn
    Grave pubGrave
    start()
    end()
}
class Hero{
    dict stats
    int id
    string name
    dict condition
    int mana
    Hand hand
    list graveyard
    int maxHand
    Deck deck
    Grave grave
}
class Hand{
    list cards
}
class Deck{
    int id
    int cost
    int maxCardCopy
    int total
    int position
    bool empty
}
class Grave{
    list grave
    bool empty
}
```
