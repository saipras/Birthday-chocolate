# Birthday-chocolate
solution to birthday chocolate
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    // Complete the solve function below.
    static int solve(int[] s, int d, int m) 
    {
        int sum =0,count =0,j=1,k=0;
        int n = s.length; 
        for(int i=0;i<=n-m;i++)
        {
            k=i;
            sum=0;
            j=1;
    
        while(j<=m)
        {
            sum=sum+s[k];
            j++;
            k++;
        }
        if(sum == d)
        {
            count++;
        }
        }
        return count;
    }  
    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) throws IOException {
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        int n = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        int[] s = new int[n];

        String[] sItems = scanner.nextLine().split(" ");
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        for (int i = 0; i < n; i++) {
            int sItem = Integer.parseInt(sItems[i]);
            s[i] = sItem;
        }

        String[] dm = scanner.nextLine().split(" ");

        int d = Integer.parseInt(dm[0]);

        int m = Integer.parseInt(dm[1]);

        int result = solve(s, d, m);

        bufferedWriter.write(String.valueOf(result));
        bufferedWriter.newLine();

        bufferedWriter.close();

        scanner.close();
    }
}
