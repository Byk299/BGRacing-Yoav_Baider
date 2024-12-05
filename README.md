# BGRacing-Yoav_Baider
Home Assignment for Ben Gurion Racing Autonomous Team- **Path Planning**
## My Work
I wrote a program in python, which when given a CSV file* containing the left and right coordinates, representing the left and right cones, uses math functions to build a smooth path, with a minimized curvature in between the cones. The code then plots the result in 2D, including the cones and the original midpoint path.

*Note that the CSV file used in the program is not the same as the file given in the assignment. It is modified to exclude the rows without titles and point values.
## My Approach
At first, I researched functions and techniques for curve finding given a set of points. During my research, I discovered that there are many different techniques, and many different considerations for an optimal path, such as the speed, the size of the car, minimal steering, the apex of a turn…. However, two main functions caught my eyes: B-Spline and Cubic Spline. Both are functions for calculating smooth curves from a given data set of points, and they each have different advantages and disadvantages, depending on the problem. 

After finding these functions, I ran tests to see how B-splines and cubic splines affect the given points, and found out that while the B-spline did result in a smoothed curve and shortened the path, the path crossed the left and right boundaries, disqualifying its results. This left me to work with the cubic spline. 

When working with the cubic spline, I found that one of the things influencing the curvature is the smoothness of the original path before the spline. For that reason, I decided to “pre-smooth” the path before applying the cubic spline, which gave me my final result. To smooth the path, I let the position of each point be influenced by the positions of the point before and after it, and then I played with the factor (the alpha) to get the best result which also does not cross the boundaries. 

Finally, using Google Collab I combined the whole process along with 2D plotting for visual feedback in one program, for my final result.
## Installation and Running Instructions
1. Download the CSV file labeled `BrandsHatchLayout.csv`
2. Go to the given link: [BGRacing Home Assignment- Yoav Baider](https://colab.research.google.com/drive/1ZLwXCB32Va_sp_vBhUO_KQgxqAJ-JoiE?usp=sharing)
3. In the tab, go to the files and upload `BrandsHatchLayout.csv` into content/sample_data
![image1](https://github.com/user-attachments/assets/f640e77e-69d2-4712-bd06-83df48fc6547)
5. Next, press the *Play* button to run the program
![image2](https://github.com/user-attachments/assets/7222e37e-87ce-4084-a2f6-b3d47235d8e4)

