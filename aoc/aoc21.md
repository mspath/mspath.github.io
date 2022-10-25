---
title: "Advent of Code 2021"
date: 2021-12-31
author: markus spath
---

`2021-12-25`

## aoc day 25 Sea Cucumber

find a safe parking spot at the floor of the ocean by waiting for two herds of sea cucumbers to stop.

fun puzzle which was trickier than expected since they loop back in from the other side.

`2021-12-24`

## aoc day 24 Arithmetic Logic Unit

well, this one went way over my head. I didn't fully understand the problem so I gave it a pass.

`2021-12-23`

## aoc day 23 Amphipod

a little, weird shortest path puzzle. need to revisit.

`2021-12-22`

## aoc day 22 Reactor Reboot

keep track of reactor cuboids.

`2021-12-21`

## aoc day 21 Dirac Dice

a dynamic programming puzzle. 

`2021-12-20`

## aoc day 20 Trench Map

a game of life style puzzle with a little twist, since the background of the world was flashing. 

the trick again was to find out what does not need be tracked. here we don't need to always keep track of the filled cells, we also can keep track of the empty cells only.

`2021-12-19`

## aoc day 19 Beacon Scanner

3d puzzle. I had to give another pass. Need to brush up on matrices and backtracking first.

`2021-12-18`

## aoc day 18 Snail Fish

I had to give a pass on this one. Need to brush up on trees first.

`2021-12-17`

## aoc day 17 Trick Shot

take probes in the sea. I got lucky with my solution since I found a correct answer just by setting various ranges, it will not relyably work on other inputs.

(the max range probably can be deducted by the size of the target field)

`2021-12-16`

## aoc day 16 Packet Decoder

write a parser for the Buoyancy Interchange Transmission System.

this was tough but rewarding.

`2021-12-15`

## aoc day 15 Chiton

find the shortest path through a cave covered in chitons.

another fun one, especially if you kind of reinvent a poor man's dijkstra.

`2021-12-14`

## aoc day 14 Extended Polymerization

second part of todays AoC was a tricky one again. those puzzles are great for getting a sense of data structures required for tackling problems which can't be just brute forced.

need to revisit this for better solutions.

`2021-12-13`

## aoc day 13 Transparent Origami

todays AoC was at the easier side again, still fun. the task basically was folding and mapping/merging points and thus finding a scret key.


`2021-12-12`

## aoc day 12 Passage Passing

todays AoC was a tough one for me, since I ran into the woods not finding the exit condition for the recursion. still fun und completed in time.


`2021-12-11`

## aoc day 11 Dumbo Octopus

todays AoC was a fun one. we had to navigate our submarine through a grid of bioluminisent octopuses.


`2021-12-10`

## aoc day 10 Syntax Scoring

todays AoC was another fun one. we had to help out syntax scoring algorithms picking a winner in their contests.

--

also did part one of AoC 20 day 7 HandyHaversacks.

`2021-12-09`

## aoc day 9 Smoke Basin

todays AoC was another good paced one. it was a similar problem to mine sweeper which I started coincidentally two days ago. the task was to fill basins.

`2021-12-08`

## aoc day 8 Seven Segment Search

todays AoC was reasonably tricky. the task was to decode seven segment signal patterns which have been scrambled. I've pretty much hardcoded the algorithm to match the patterns but this problem lends itself to being revisited and tried in a more 'computational' way (brute force, rule based based on the given constraints, etc. I'd also love to see peter norvigs approach to this)

`2021-12-07`

## aoc day 7 Treachery of Whales

todays AoC 21 was pretty straighforward. the task was to coordinate a fleet of submarines of a swarm of crabs to fight off a whale.


`2021-12-06`

## aoc day 6 Laternfish

todays AoC 21 was about exponential growth. my initial solution used a recursive approach which was able to yield a result, but my macbook had to work for it.

but once you figure out that you basically just have to keep track of the number of fish based on their lifecycle it becomes hilariously simple to solve. our brains just are not wired for understanding exponential growth.

`2021-12-05`

## aoc day 5

todays AoC 21 was about keeping track of lines on a grid.

`2021-12-04`

## aoc day 4

todays AoC 21 was easier again. the task was to battle against a giant squid in a bingo game.

my major takeaway: do read the instructions carefully. I got thrown off twice 'cause the result were wrong just to find out that I just was calculating the wrong thing. unlike other challenges or tasks AoC seems to be carefully drafted and usually concise and non ambiguous.

--

also did day 6 of AoC 20: custom customs, which basically is about reading input and mangling it in a way that kotlins collection methods can do the rest.

`2021-12-03`

## aoc day 3

todays AoC 21 picked it up a notch. the task was to decode ratings, the setup lended itself to bitwise operations and recursion i.e. we had to deal with increasing subsets.

If you have a good grasp on bitwise operations, shifts, mapping and masking this probably would allow for a solution in a couple of lines, but I hit too many roadblocks.

my solution was ok'ish in the end, I just stuck to Strings and providing filters.

`2021-12-02`

## aoc day 2

todays AoC 21 was another easy one. task was to navigate a submarine in the seas. I tried to keep it functional'ish with fold.

the whole momentum around AoC is massive. it's super interesting to see the same solution in dozens of different languages, it's also insane how fast the top competitive programmers are. also tons of videos and tutorials, everyone seems to be in good spirits. I'm glad I found it.

--

also did day 3 of AoC 20: toboggan trajectory, which is about counting stuff in a conceptual world. again tried to solve it functional'ish with fold.

--

also did day 4 of AoC 20: passport processing. mainly about validating input with regex.

--

also did day 5 of AoC 20: binary boarding. main takeaway was how the understanding / reframing of the problem affects any solution. obviously if you can't see a pattern you can't see yourself not 'can't seeing', but it probably helps to understand and think about the problem.

`2021-12-01`

### aoc day 1

todays AoC 21 was a cute warm up. task was to find matching numbers.

jetbrains reference solution had two nice gems: `windowed` and destructuring in lambdas. this is fantastic for all sorts of list manipulations without having to deal with the edges.

```kotlin
    println(
        input
            .windowed(2)
            .count { (a, b) -> b > a }
    )
```

--

also did day 1 of AoC 20: repost repair, which was a task about finding complementary numbers. actually I kinda liked my solution of creating a map on the go so that any matches will be found in the first go.

another goodie from jetbrains walkthroughs:

```kotlin
fun List<Int>.findPairOfSum(sum: Int): Pair<Int, Int>? {
    val complements = associateBy { sum - it }
    return firstNotNullOfOrNull { number ->
        val complement = complements[number]
        if (complement != null) Pair(number, complement) else null
    }
}
```

`associate`, `associateBy` and `associateWith` probably will come in hugely handy.

see

- https://www.youtube.com/watch?v=o4emra1xm88
- https://github.com/kotlin-hands-on/advent-of-code-2020/tree/master/src/day1d

---

also did day 2 of AoC 20: password philosophy, which is about validating strings via regex and destructioning.

---

`2021-11-30`

just testing whether my github pages repository still works. magically it does.

I'm thinking about finally making use of these fantastic github pages by keeping a diary of the _100 days of code_ challenge and/or _advent of code 2021_. Nothing fancy or particulary useful, just as some sort of habit for holding myself accountable a bit.
