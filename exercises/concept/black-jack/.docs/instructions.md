# Instructions

In this exercise you are going to implement some rules of [Blackjack][blackjack],
such as the way the game is played and scored.

**Note** : In this exercise, _A_ means ace, _J_ means jack, _Q_ means queen, and _K_ means king cards.
A [standard 52-card deck][standard_deck] is assumed.

## 1. Calculate the value of a card

In Blackjack, it is up to each individual player if an ace is worth 1 or 11 points.
Face cards (_J_, _Q_, _K_) are worth 10 points and any other card is worth its pip (numerical) value.

Define the `value_of_card` function with a parameter `card`.
The value of _J_, _Q_ or _K_ is 10.
Otherwise, return the numerical value of a card.
An ace can take on multiple values so let's ignore _A_ for the time being.

```python
>>> value_of_card('K')
10
>>> value_of_card('4')
4
```

## 2. Calculate the value of an ace

As mentioned before, an ace can be worth _either_ 1 or 11 points.
At the same time, players are trying to get as close to 21 as possible, without going _over_ 21.

Define the `value_of_ace(<hand_value>)` function with a parameter `hand_value`,
which is the total hand value before getting an ace card.
You now have to decide if the upcoming ace card will be scored as a 1 or 11.
The value of the hand with the ace needs to be as high as possible _without_ going over 21.

```python
>>> value_of_ace(19)
1
>>> value_of_ace(7)
11
```

## 3. Determine Blackjack

If the first two cards are an ace and a ten-card, giving a count of 21 in two cards, it is known as blackjack.

Define the `is_blackjack(<card_one>, <card_two>)` function with parameters `card_one` and `card_two`, which are a pair of cards.
Determine if the two-card hand is a blackjack.

**Note** : This calculation can be done in many ways.
 If possible, check if there is an ace and a ten-card in the hand.

```python
>>> is_blackjack('A', 'K')
True
>>> is_blackjack('10', '9')
False
```

## 4. Splitting pairs

If the first two cards are of the same value,
such as two sixes, or a _Q_ and _K_ a player may choose to treat them as two separate hands.
This is known as "splitting pairs".

Define the `can_split_pairs(<card_one>, <card_two>)` function with parameters `card_one` and `card_two`, which are a pair of cards.
Determine if this two-card hand can be split into two pairs.
```python
>>> can_split_pairs('Q', 'K')
True
>>> can_split_pairs('10', 'A')
False
```

## 5. Doubling down

When the original two cards dealt total 9, 10, or 11 points
a player can place an additional bet equal to the original bet.
This is known as "doubling down".

Define the `can_double_down(<card_one>, <card_two>)` function with parameters `card_one` and `card_two`, which are a pair of cards.
Determine if the two-card hand can be "doubled down".
```python
>>> can_double_down('A', '9')
True
>>> can_double_down('10', '2')
False
```

[blackjack]: https://en.wikipedia.org/wiki/Blackjack
[standard_deck]: https://en.wikipedia.org/wiki/Standard_52-card_deck
