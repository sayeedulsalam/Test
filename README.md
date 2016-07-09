# Test
//java program to display spiral matrix

import java.util.ArrayList;
import java.util.Scanner;


public class SpiralMatrix {

	public static void main(String[] args) {
		int[][] values = {{1,2,3,4}, {5,6,7,8}, {9,10,11,12}, {13,14,15,16}};
		System.out.println(spiralOrder(values));
		
	}
	
	public static ArrayList<Integer> spiralOrder(int[][] matrix){
		ArrayList<Integer> result = new ArrayList<Integer>();
		if(matrix == null || matrix.length == 0)
			return result;
		int m = matrix.length; //down
		int n = matrix[0].length; //right
		int x = 0;
		int y = 0;
		while(m>0 && n>0){
			if(m==1){
				for(int i=0;i<n;i++){
					result.add(matrix[x][y++]);
				}
				break;
			}else if (n==1) {
				for(int i=0;i<m;i++){
					result.add(matrix[x++][y]);
			}
				break;
			}
			for(int i=0;i<n-1;i++){
				result.add(matrix[x][y++]);
			}
			for(int i=0;i<m-1;i++){
				result.add(matrix[x++][y]);
			}
			for(int i=0;i<n-1;i++){
				result.add(matrix[x][y--]);
			}
			for(int i=0;i<m-1;i++){
				result.add(matrix[x--][y]);
			}
			x++;
			y++;
			m=m-2;
			n=n-2;
		}
		return result;
	}

}
