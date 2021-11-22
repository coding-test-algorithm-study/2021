<백준 15881>

```java
import java.util.*;
import java.io.*;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int n = Integer.parseInt(br.readLine());
        String s = br.readLine();
        int answer = 0;

        for(int i=0;i<n;i++){
            if(s.charAt(i) == 'p' && i+3<n){
                if(s.substring(i,i+4).equals("pPAp")) {
                    answer++;
                    i+=3;
                }
            }
        }
        System.out.println(answer);
    }
}
```
