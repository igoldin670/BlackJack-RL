# BlackJack-RL

This project implements a simple Blackjack simulator and a basic Q-learning agent in Python.

## Overview

The simulator follows simplified Blackjack rules:

- The player starts with two cards.
- Number cards are worth their face value.
- Face cards are worth 10.
- Aces are worth either 1 or 11, whichever gives the better valid hand.
- The player can choose to `hit` or `stand`.
- If the player goes over 21, they bust and lose.
- The dealer hits until reaching at least 17.
- The player wins only if their final hand is strictly greater than the dealer’s hand.

## Q-Learning

The project uses a Q-table to learn the value of each action in each state.

A state is represented as:

```python
(player_total, usable_ace)
```

Actions are:

- "hit"
- "stand"

The Q-table stores the estimated value of each action for every possible state. The agent explores by choosing random actions, observing rewards, and updating the table using the Q-learning rule.

Rewards:

Win  = +1
Lose = -1
Bust = -1
In play = 0
