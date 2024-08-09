레벨테스트 9번문항  (시도중)    
[> 문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/12915)


```cs
using System;

public class Solution 
{
    public static string[] solution(string[] strings, int n)
{

    string[] aaa = new string[strings.Length];

    string vvv;


    for(int i=0; i< strings.Length; i++)
    {
        for (int j = n; j<=strings[i].Length; j++)
        {                
            vvv = strings[i].Substring(n);                
            aaa[i] = vvv;               

        }
        

    }// aaa에는 un, ed, ar가 들어있음 (ce, cd, x)

    //이제 이걸 ar, ed, un으로 정렬함 (cd, ce, x)
    Array.Sort(aaa);


    //  sun  bed car ---->  car  bed sun 순서로 출력
    // abce abcd cdx ----> abcd abce cdx 순서로 출력하기 위해
    // aaa[]의 순서를 strings[]에 강요해야함 
    // aaa는 012 012 돼있지만 strings는 아직 210 210 돼있음

    for (int i = 0; i < strings.Length; i++)
    {
        for (int j = 0; j < aaa.Length; j++)
        {
            if (strings[i].Contains(aaa[j]))
            {
                string temp = strings[j];
                strings[j] = strings[i];
                strings[i] = temp;
            }

            // 이렇게 해봤는데 첫번째는 통과고 두번째는 반대로 나와요 ㅠㅠ

        }

    }

    string[] answer = strings;

    return answer;
}
}

```