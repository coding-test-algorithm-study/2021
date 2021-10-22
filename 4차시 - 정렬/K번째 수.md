```java
import java.util.*;

class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];
        
        for (int i=0; i<commands.length; i++) {
            List<Integer> sublist = new ArrayList<>();
            
            for (int idx = commands[i][0] - 1; idx <= commands[i][1] - 1; idx++) {
                sublist.add(array[idx]);
            }
            Collections.sort(sublist);
            
            answer[i] = sublist.get(commands[i][2] - 1);
        }
        return answer;
    }
}
```
