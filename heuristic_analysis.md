## Tournament result
```
 Match #   Opponent    AB_Improved   AB_Custom   AB_Custom_2  AB_Custom_3
                        Won | Lost   Won | Lost   Won | Lost   Won | Lost
    1       Random       9  |   1     6  |   4    10  |   0     8  |   2
    2       MM_Open      9  |   1     6  |   4     8  |   2     6  |   4
    3      MM_Center     6  |   4     6  |   4     6  |   4     8  |   2
    4     MM_Improved    5  |   5     6  |   4     6  |   4    10  |   0
    5       AB_Open      6  |   4     5  |   5     4  |   6     5  |   5
    6      AB_Center     7  |   3     7  |   3     6  |   4     7  |   3
    7     AB_Improved    4  |   6     4  |   6     6  |   4     4  |   6
--------------------------------------------------------------------------
           Win Rate:      65.7%        57.1%        65.7%        68.6%
```

## Heuristic analysis
1. *improved*=own_moves-opp_moves: 
use the number of own moves subtract the number of opponent's moves, and win rate is 65.7%.

2. *custom*=own_moves-2*opp_moves: 
add a weight factor to opp_moves compared to *improved*, but performance is usually worse than *improved*.

3. *custom2*=own_moves^2-opp_moves^2: 
use square of move numbers compared to *improved*, and the result is slightly better than *improved*.

4. *custom3*=own_moves/(opp_moves+1): 
divide own moves over opponent's moves, and average win rate is the best one among all test heuristics.

## Recommendation
The *custom2* is recommended, and here are the reasons:
1. It's the only heuristic that can defeat AB_Improved,
2. The win rate is not the highest, but it's fairly good -- 65.7%.
3. It could defeat all minimax algorithms.
