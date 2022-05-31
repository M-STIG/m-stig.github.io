---
permalink: /find-pi
---

## [Approximating Pi]()
One method for approximating the value of Pi could be the use of a Monte Carlo method.
By creating a circle within a bounding square, the value of Pi can be found by calculating the ratio of the area of the circle divided by the area of the bounding square.
A rough approximation of Pi can be achieved by placing many random points within that overall area and then dividing the number of points that fell within the circle by the total number of points placed.

In an example of this exercise, we will create a space that contains a quarter circle in a bounding square which represents π/4.
Our final calculation will be multiplied by 4 to obtain a whole estimate of Pi.

```java
//-Create a new random number generator.
		Random n = new Random();
		//-For loop executes the input number of desired coordinates
		for (int j=0; j<e; j++) {
			//-Generate new x and y coordinates
			x = n.nextDouble();
			y = n.nextDouble();
			/*-Check to see if the coordinate is within 1 distance of the origin
			 * and thus within the circle.*/
			if (Math.sqrt(Math.pow(x, 2) + Math.pow(y, 2)) < 1) {
				//-Increment the number of coordinates within the circle if true.
				inside++;
			}
		}
		/*-Pi is estimated by dividing the number of coordinates inside the circle by the total
		 * number of coordinates and then multiplying that number by four since the original
		 * estimate is for one quarter of the actual circle*/
		estimate = 4 * ((double) inside / e);
```
