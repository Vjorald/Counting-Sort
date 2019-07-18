//Implementation of Counting Sort (Sorting Process)


public class CountingSort {
	
	public static int [] countingSort ( int [] sort){
		
		int summit = sort [0];
		// Control for the biggest element in the array
		for(int i = 0; i < sort.length; i++){
			if (sort[i] > summit){
				summit = sort[i];
			}
		}
    
		
		// New count array of length equal to summit(biggest element
		int [] count = new int [summit + 1];
    
		
		//Mark at first with 1 all the elements of count with index sort[i]
		for(int i=0; i < sort.length; i++){
			int x = count [sort[i]];
			x++;
			count [sort[i]] = x;
		}
		
		int complete = 0;
		
		//Sorting
		for (int i = 0; i <= summit; i++){
			
			for(int j= 0; j < count[i]; j++){
				sort [complete] = i;
				complete++;
			}
		}
	
	
	return sort;
	}
	
  
  
	public static void main(String [] args){
		int [] array = {5, 2, 8, 4, 9, 1};
		
		System.out.println("Unsortiert: ");
		for(int i = 0; i < array.length; i++){
			System.out.println(array[i]+ " ");
		}
		
		System.out.println();
		
		countingSort(array);
		
		System.out.println("Sortiert: ");
		
		for(int i= 0; i < array.length; i++){
			System.out.println(array[i]+ " ");
		}
	}
}


