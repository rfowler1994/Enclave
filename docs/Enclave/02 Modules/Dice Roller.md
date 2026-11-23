A minimal [[Modules|module]] that allows the DM to roll dice and receive text-based results without graphical dice animations or simulations.
# Core Features
- Ability to roll any of the following dice:
	- d4
	- d6
	- d8
	- d10
	- d12
	- d20
	- d100
- Ability to roll multiple dice at a time. 
- Ability to roll with advantage or disadvantage.
- Roll results display both the total and the individual dice values.
- Ability to view roll history in a scrollable list.
# Potential Features
- Send an initiative roll result to the [[Initiative Tracker]] module. This would create a module interaction.
- Support for dice formulas to perform more complex rolls.
- Custom dice formulas can be created, saved, and edited for reuse.
# Module Interactions
None currently planned for core functionality
# Open Questions
- What is a reasonable limit to the length of roll history? Should it be cleared at the end of each session or retained between sessions?
- How should roll results be displayed? Could a temporary pop-up or floating window show the latest result, with an optional persistent roll history window that prominently displays the most recent roll?
# Proposed Dice Formula Syntax
```
#d = number of dice to roll
d# = size of dice to roll
r[cond] = reroll 
rr[cond] = recursively reroll 
![cond] = explode a matching roll once
!![cond] = recursively explode matching rolls
kh# = number of high dice to keep
kl# = number of low dice to keep
dh# = number of high dice to drop
dl# = number of low dice to drop
+/-# = modifiers supporting simple addition or subtraction to the final value rolled
```
## Conditionals: 
```
<
>
<=
>=
=
min/max = the minimum or maximum possible result for the specified die
```
## Examples
- Advantage: `2d20kh1`
- Disadvantage: `2d20kl1`
- Stats: `4d6rr[=1]kh3`
## Execution Order
To be defined at a later point. Care must be taken to avoid infinite loops or unexpected results with very complex formulas. 
