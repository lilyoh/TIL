```java
import java.util.Scanner;

public class Application {
	public static void main(String[] args) {

		// 1d array
		int[] values = {1, 2, 3};
		
		// only need 1 index to access values
		System.out.println(values[0]); // 1
		
		// 2d array (grid or table)
		int[][] grid = {
				{1, 2, 3},
				{11, 22, 33},
				{111, 222, 333}
		};
		
		// need 2 indices to access values
		System.out.println(grid[0][0]); //1
		
		// can also create without initializing
		String[][] texts = new String[2][3];
		texts[0][1] = "hello";
		System.out.println(texts[0][1]); // hello
		
		// how to iterate through 2d arrays
		// 1) iterate each row
		// 2) for each row, go through the columns
		for(int row=0; row<grid.length; row++) {
			for(int col=0; col<grid[row].length; col++) {
				System.out.println(grid[row][col]);
			}
			System.out.println();
		}
		
		// the last array index is optional
		String[][] words = new String[2][];
		
		// each sub-array is null
		System.out.println(words[0]);
		
		// we can create the sub-arrays manually
		words[0] = new String[3];
		
		// can set a values in the sub-array we just created
		words[0][1] = "hi there";
		
		System.out.println(words[0][1]);
	}
}
```