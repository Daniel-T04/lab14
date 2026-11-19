# GDB log

One dated section per week. Paste the commands you used and the output you saw, then explain what it means in your own words. Pasted output with no explanation earns partial credit at most.

## Week 12 (Lab 12)

### The constructor chain

Commands, in the order you typed them, with one line on what each did:

Backtrace inside `Hangman::Hangman` (paste it):

Backtrace inside `Game::Game` (paste it):

Where `finish` returned to:

Order of destructor breakpoints when the program ended:

Construction order and destruction order, as read from the backtraces:

### What a base pointer shows

`print hangman` (paste it):

`print *g` (paste it):

What is different, and why:

`ptype Hangman` and `ptype g` (paste them):

One sentence on what `ptype Hangman` revealed about inheritance:

## Week 14 (Lab 14)

Each partner writes their own section. Put your name here:

### Binary search

Breakpoint, `display low`, `display mid`, `display high`, and the values after three `next` iterations (paste them):
1: low 
2: mid
3. high

-Line 113: low = 0, high = -15328 (gabage value before init)

-Line 114 low = 0, high = 0 (after high = count - 1)

-Line 116: low = 0, high = 0 (entering while loop)

-Line 117: low = 0, mid = 32767 (before mid initialization), high = 0


The conditional stop you set (`condition N low > high`) and what it caught:

condition 1 low > high,  When searching for a name not on the leaderboard such as "zzz" and GSB paused execution at line 113 upon entering 'binary_search_name' because the uninitialized stack variables initially satisfied the condition.

Loop iterations you counted versus the comparison count the program reported:

The Successful search are when it was searching for "Daniel": The loop ran for 1 iteration because the target was found immediately at the midpoint which this is 'mid = 0'. So the program reported 1 comparison use a  '==' to check.

An unsuccessful search is  searching for "zzz", like the last one it ran for one iteration, but executed  in 2 compariosns and the '==' to check for failure  them the use '<' relational check executed before adjusting bounds to terminate the loop). The final comparison count reported matched the total increments.

### Insertion sort

The `watch comparisons` stops: the counter and the array position after you skipped the first 50 stops with `ignore`:

One count you read in the debugger, and the number the program reported:
