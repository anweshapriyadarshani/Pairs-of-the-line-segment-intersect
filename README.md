# Pairs-of-the-line-segment-intersect
Suppose you are given two lists of n points, one list p1, p2, ..., pn on the line y = 0 and the other list q1, q2, ..., qn on the line y = 1. Imagine a set of n line segments connecting each point pi to qi. Write an algorithm to determine how many pairs of the line segments intersect.



//algorithm for intersecting points

1. Sort points from left to right on X-coordinate

2. Creating an empty self-balancing binary search tree. 
   It will contain all the active line segments of y-coordinate
   
3. for i=0 to 2n-1 //for all 2n points

 if(points[i].isleft) //if point is left end to its line
 
 T.insert(points[i].line()) //insert points into tree
 
 if dointersect((points[i].line(), T.pred(points[i].line()))
 return true
 
 if dointersect((points[i].line(), T.succ(points[i].line()))
 return true
 
 else
	 //if it is right end of line then check whether predecessor and successor intersect with each other
 
    if(dointersect(T.pred(points[i].line(), T.succ(points[i].line())))
		return true
	
	T.delete(points[i].line()) //delete from true
	return false
 
 
