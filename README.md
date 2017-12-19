# Algorithms
import java.io.*;
import java.lang.*;
import java.util.*;

class Code1 {

	public static void main(String[] args) {
		
		Scanner input = new Scanner(System.in);

		System.out.println("Input:");
		System.out.println();
		//System.out.println();
		//variable for test case
		int T;
		T = input.nextInt();
		
		//output array
		int[] output = new int[T];

		for(int x = 0; x < T; x++) {

			//variable for row x column
			int m, n;
			m = input.nextInt();
			n = input.nextInt();

			//declare a 2d char array
			String[] array = new String[m];

			//taking the inputs in R and G
			for(int i = 0; i < m; i++) {

				array[i] = input.next();
				
				for (int j = 0; j < n-1; j++) {

					//side check
					if(array[i].charAt(j) == array[i].charAt(j+1)) {

						if(array[i].charAt(j) == 'R') {

							output[x] += 3;
						} else {
							output[x] += 5;
						}
					}				
				}

				//upper cherry check
				if(i != 0) {
					for (int j = 0; j < n; j++) {

						//side check
						if(array[i-1].charAt(j) == array[i].charAt(j)) {

							if(array[i].charAt(j) == 'R') {

								output[x] += 3;
							} else {
								output[x] += 5;
							}
						}				
					}
				}
			}//end of outer for		
		}
		System.out.println();
		//print output
		System.out.println("output:");
		System.out.println();
		
		for(int x = 0; x < T; x++) {
			System.out.println(output[x]);
		}

	}
}
