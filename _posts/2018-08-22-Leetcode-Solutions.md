---
layout: post
title: "Leetcode Questions and understanding 'em \2"
published: true
---

[221. Maximal Square - Medium](https://leetcode.com/problems/maximal-square/)
##Code:
<script src="https://gist.github.com/xynazog/32b600bdd7ac1405277fd6b03ba98a2d.js"></script>
This question uses DP. 
1. There is a dp matrix which stores the length of the largest square with dp[i][j] as the bottom right corner. 
2. If matrix[i-1][j-1] is 1, update dp[i][j] as min of the three elements around it.
Consider these cases:
### Case 1:
1 0
0 1
In this, the bottom right 1 is not a part of the 1 up diagonally. Thus, it's a new square and the side length starts from 1.

### Case 2:
1 1
1 1
In this case, the bottom right 1 is part of the bigger square. Thus, 1 is added to the original length.

[836. Rectangle Overlap](https://leetcode.com/problems/rectangle-overlap/)
##Code:
<script src="https://gist.github.com/xynazog/1bb41ed41612dd9befff9777015023de.js"></script>
This question is a simple math one.