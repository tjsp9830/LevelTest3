레벨테스트 9번문항  (시도중 - 아래 코드로 입출력 예시 2가지는 성공했으나, 정확성 테스트에서 반려당함)    
[> 문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/12915)


```cs
using System;

public class Solution 
{
    public string[] solution(string[] strings, int n)
    {

        string[] aaa = new string[strings.Length];

        string vvv;


        for(int i=0; i< strings.Length; i++)
        {
            // 처음에는 strings의 요소인 string형 변수들을 하나하나 쪼개서 비교를 시도했으나, 쪼개서 배열에 넣은 내용이 서로 중복될 경우에는 예외처리를 해야 했습니다.
            // 그래서 코드를 아예 수정하여, string형 변수들의 인덱스 n번째부터 뚝 잘라서 배열에 넣은 뒤에 비교를 시도하는 방법으로 바꿔보았습니다.
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
            for (int j = 0; j < strings.Length; j++)
            {
                if (strings[j].Contains(aaa[i]))
                {
                    string temp = strings[i];
                    strings[i] = strings[j];
                    strings[j] = temp;
                }

            }

        }

        //출력
        string[] answer = strings;
        return answer;
    }
}

```
