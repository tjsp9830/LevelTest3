레벨테스트 7번문항     
[> 문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/120899)


```cs
using System;

public class Solution 
{
    public int[] solution(int[] array) 
    {
        int result = 0; //원소 범위의 최소값을 넣고 요소들과 비교
        int index = 0; 
        
        for (int i = 0; i < array.Length; i++)
        {
            //조건에 맞는 요소를 찾으면 (더 큰 수) 결과에 반영해주고
            if (result < array[i])
            {
                result = array[i];
                index = i; //index라는 변수에 실제 인덱스를 넣어줌 
            }
        }
        
        //반환
        return new int[] {result, index};
    }
}

```