Problem Statement:

There is a sequence whose n th term is
T_{n} = n ^ 2 - (n - 1) ^ 2
Evaluate the series
SnT1+T2+T3+Tn ...
Find Sn mod (10 ^ 9 + 7)
Example
n = 3
The series is 1 ^ 2 - 0 ^ 2 + 2 ^ 2 - 1 ^ 2 + 3 ^ 2 - 2 ^ 2 = 1 + 3 + 5 = 9
Function Description
Complete the summingSeries function in the editor below.
summingSeries has the following parameter(s):
int n: the inclusive limit of the range to sum
Returns
int: the sum of the sequence, modulo (10 ^ 9 + 7)

CODE:

import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.function.*;
import java.util.regex.*;
import java.util.stream.*;
import static java.util.stream.Collectors.joining;
import static java.util.stream.Collectors.toList;

class Result {

    /*
     * Complete the 'summingSeries' function below.
     *
     * The function is expected to return an INTEGER.
     * The function accepts LONG_INTEGER n as parameter.
     */

    public static int summingSeries(long n) {
    // Write your code here
        long m=(long)(1e9+7);
        long ans=((n%m)*(n%m))%m;
        return (int)ans;
        // return (int)((int)(n%m*n%m)%(int)m);
    }

}

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        int t = Integer.parseInt(bufferedReader.readLine().trim());

        IntStream.range(0, t).forEach(tItr -> {
            try {
                long n = Long.parseLong(bufferedReader.readLine().trim());

                int result = Result.summingSeries(n);

                bufferedWriter.write(String.valueOf(result));
                bufferedWriter.newLine();
            } catch (IOException ex) {
                throw new RuntimeException(ex);
            }
        });

        bufferedReader.close();
        bufferedWriter.close();
    }
}
