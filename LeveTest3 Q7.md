레벨테스트 7번문항     
[> 문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/120899)


```cs
using System;

public class Solution 
{
    public int[] solution(int[] array) 
    {
        int result = 0;
        int index = 0;
        
        for (int i = 0; i < array.Length; i++)
        {
            if (result < array[i])
            {
                result = array[i];
                index = i;
            }
        }
        
        
        return new int[] {result, index};
    }
}

```