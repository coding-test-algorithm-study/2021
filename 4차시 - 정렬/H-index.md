``` java
import java.util.Arrays;
import java.util.Collections;

class Solution {
    public int solution(int[] citations) {
        int answer = 0;
        int index =-1;

        //내림차순 정렬
        Integer [] arr = Arrays.stream(citations).boxed().toArray(Integer[]::new);
        Arrays.sort(arr, Collections.reverseOrder());

        //최소값 저장
        int min =arr[arr.length-1];


        for (int i = arr.length ; i>=0 ; i--){ //citations 의 배열 수 만큼 늘린다.
            
           //최소값이 i보다 클땐 나와야한다.
            if(min>i){
                answer = i;
                return  answer;
            }


            for ( int j =0 ; j <arr.length;j++){
               // h값보다 작을떄의 인덱스를 찾으면 그 인덱스값을 넘겨준다.
                if(i>arr[j]){ 
                    index=j; //j
                    break;
                }
            }
            //그 인덱스값이 h값보다 크거나 같으면 그게 정답이다.
            if(i<=index){
                answer=i;
                break;
            }


        }

        return answer;

    }
}
```
