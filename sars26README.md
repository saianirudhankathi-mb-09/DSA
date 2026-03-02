BufferedReader v/s Scanner:

BufferedReader is faster than Scanner class
BR reads entire single line input testcases at once.

CODE:

Better Method (Recommended for CP)

Use StringTokenizer (faster than split):

import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        
        StringTokenizer st = new StringTokenizer(br.readLine());
        
        int a = Integer.parseInt(st.nextToken());
        int b = Integer.parseInt(st.nextToken());
        int c = Integer.parseInt(st.nextToken());
        int d = Integer.parseInt(st.nextToken());
        
        System.out.println(a + " " + b + " " + c + " " + d);
    }
}
