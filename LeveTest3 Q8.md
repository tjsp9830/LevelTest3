레벨테스트 8번문항     
[> 문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/120811)


```cs
using System;

public class Solution 
{
    public int solution(int[] array) 
    {
        // 1. 배열을 버블정렬한 후, 배열의 길이/2 연산 결과의 인덱스를 꺼내는 코드 작성
        
        int answer = 0;        
        
        for(int j=0; j<array.Length; j++)
        {
            for(int i=0; i<array.Length-1; i++)
            {
                if(array[i] > array[i+1] ) // 2. 인덱스 0부터 길이-1까지 두개씩 비교해서 자리를 바꿔줌
                {
                    int temp = array[i];
                    array[i] = array[i+1];
                    array[i+1] = temp;
                }
                    
            }
        } // 3. 이것을 배열의 길이만큼 반복함 (j가 끝까지 가기 전에 오름차순이 완성될 수도 있음)
        
        //반환
        answer = array[(array.Length / 2)];                
        return answer;
    }
}

```