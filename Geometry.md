 # Intro

   Geometry is a branch of mathematics that is concerned 
   with properties of space that are related with distance, shape, size, and relative position of figures. 

   ONLY 2D Geometry asked

   Geometry is not the focus of problem but you asked to use othe algos and DS in the problem


   # Corner Cases


     Zero values


  # Techniques

    1. Distance between two points

       When comparing distance btwn 2 points dx2 + dy2 is sufficient no need of square root

    2. Overlapping circles

       To check if 2 circles overlap 
         Check IF dist btwn two centers < sum of theri radii

    3. Oerlapping rectangles

        2 rectangles overlap if following is TRUE:

          overlap = rect_a.left < rect_b.right and \
                rect_a.right > rect_b,left and \
                rect_a.top > rect_b.bottom and \
                rect_a.bottom < rect_b.top


  # Sample qs

        1. You have a plane with lots of rectangles find how many of them intersect
        2. Which DS to use to query K nearest points of a set on 2D plane
        3. Given many points find K points nearest to origin
        4. How would you triangulate a polygon
