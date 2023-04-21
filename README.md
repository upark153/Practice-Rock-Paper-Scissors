# Practice-Rock-Paper-Scissors
This is a rock-paper-scissors programming exercise in c language.
![image](https://user-images.githubusercontent.com/115389450/233513890-f8197ba8-8999-4cd9-8f29-111ea4e9fded.png)
```
#include <stdio.h>

int main(void)
{
  int i,j,k,o,a,b,c,d,e;

  for(i=0; i<10; i++)
  {
    for(j=0; j<i+1; j++)
    {
      printf("*");
    }
    for(k=0; k<10-i; k++)
    {
      printf(" ");
    }
    for(o=0; o<10-i; o++)
    {
      printf("*");
    }
    printf("\n");
  }
  for(a=0; a<10; a++)
  {
    for(b=0; b<10-a; b++)
    {
      printf(" ");
    }
    for(c=0; c<a+1; c++)
    {
      printf("*");
    }
    for(d=0; d<a+1; d++)
    {
      printf(" ");
    }
    for(e=0; e<10-a; e++)
    {
      printf("*");
    }
    printf("\n");
  }
  return 0;
}
```
- - -
﻿
다른 분들은

변수를 5개 정도만 썻는데

나는 9개를 썼다.

어떻게 하면 조금 간편하게 표현할 수 있을지 고민해봐야겠다.

미래의 의용이가 조금 더 발전해 있다면

11월 4일의 의용이에게 조언을 해 주길 바란다.


문제2.

삼각형의 밑변을 정해서 입력한 수만큼의 크기의

바람개비가 그려지게 코드를 작성하시오.


문제1번은 밑변이 10인 삼각형 4개가 모여 만들어진 바람개비이다.

그래서 위에 코드에서 변수 num을 지정해주고,

숫자 10이 써진 부분을 num으로 바꾸어 주었다.

그러니 실행이 됬다.

- - -
```
#include <stdio.h>

int main(void)
{
  int i,j,k,o,a,b,c,d,e;
  int num;

  printf("길이를 입력하시오 : ");
  scanf("%d", &num);

  for(i=0; i<num; i++)
  {
    for(j=0; j<i+1; j++)
    {
      printf("*");
    }
    for(k=0; k<num-i; k++)
    {
      printf(" ");
    }
    for(o=0; o<num-i; o++)
    {
      printf("*");
    }
    printf("\n");
  }
  for(a=0; a<num; a++)
  {
    for(b=0; b<num-a; b++)
    {
      printf(" ");
    }
    for(c=0; c<a+1; c++)
    {
      printf("*");
    }
    for(d=0; d<a+1; d++)
    {
      printf(" ");
    }
    for(e=0; e<num-a; e++)
    {
      printf("*");
    }
    printf("\n");
  }
  return 0;
}
```
- - -
바람개비 만들기( while문 )
- - -
```
#include <stdio.h>

int main(void)
{
     int line=0; // 열, 줄 만들기 !!
     int star=0; // 별 만들기 !!
     int blank=0; // 공백 만들기 !!
     while(line<10) // line이 0부터 시작하므로 0,1,2,3..9 = 총 10개의 열이 만들기 반복시작입니다.
     {
             star=0; 
             while(star<line+1)  // 별은 1,2,3....10이 만들어져야 해요 따라서 line=0부터 시작하므로 1을 더해줬어요
             {
                      printf("*");
                      star++;
             }
            blank=0;
            while(blank<10-line) // 공백은 10,9,8..1이 만들어져야 해요 따라서 line은 아직 0이므로 10-line 했어요
            {
                      printf(" ");
                      blank++; 
            }
           star=0;
           while(star<10-line) // 다시 별이 10,9,8,..1이 만들어져야 해요 따라서 line은 아직 0이므로 10-line 했어요
           {
                      printf("*");
                      star++;
           }
          printf("\n"); // 열(줄)이 띄어집니다!
          line++;  // 증가합니다.
    }
    line=0;
    star,blank=0;
    while(line<10) // 다시 10개 줄을 만들꺼에요
    {
        blank=0;
        while(blank<10-line) // 공백이 10,9,8..1로 줄어드므로 이렇게 했어요 line은 아직 0이에요
        {
                printf(" ");
                blank++;
        }
       star=0;
       while(star<line+1) // 별이 1,2,3...10개 증가 ! 따라서 이렇게 했어요 line은 아직 0이에요
       {
                printf("*");
                star++;
       }
      blank=0;
      while(blank<line+1) // 공백이 1,2,3..10개 증가 ! 따라서 이렇게 했어요 line은 아직 0이에요
      {
            printf(" ");
            blank++;
      }
      star=0;
      while(star<10-line) // 별이 10,9,8..1개 감소 ! line은 아직 0이에요
      {
            printf("*");
            star++;
      }
     printf("\n");
     line++;
   }
  return 0;
}
```

- - -
﻿
재일 vs 성일

재일이의 편 (의용 혹은 연재 랜덤 배정)

성일이의 편 (의용 혹은 연재 랜덤 배정)

배정 완료 후 가위바위 보

한판 끝나고 승률 표시

10판 이기면 승리

﻿
- - -
```
#include <stdio.h> // main 함수 사용하기
#include <stdlib.h> // rand, srand 함수 사용하기
#include <time.h> // time 함수 사용하기

int main(void) // main 함수 선언
{
 int go, pa, team, game; // 고연재, 박의용, 팀나누기, 게임
 printf("재일팀 성일팀을 뽑겠습니다.\n"); 

 srand(time(0)); // 항상 같지 않은, 매번 다른 난수를 발생시키기 위해

 team = rand() %2; // 변수 team은 0부터 n-1의 범위, 즉 n은 2이므로 0~1의 범위(고연재,박의용)
 if(team==0) // team이 0이면 true(진실), 0이 아니면 false(거짓)
  printf("재일팀 : 연재, 성일팀 : 의용\n"); // 0이면 현재 줄 출력
 else
  printf("재일팀 : 의용, 성일팀 : 연재\n"); // 0이아닌 1이면 현재 줄 출력
 return 0; 
}
```
```
int go, pa, team, game; // 고연재,박의용,팀나누기,game 시작 처음에 4개를 줬습니다.
int jteam=0; // 재일 팀 
int steam=0; // 성일 팀
int cnt=0; // 총 가위바위보 게임 횟수
double jrate=0; // 재일 팀 승률 
double srate=0; // 성일 팀 승률
```
```
printf("팀 배정이 완료되었으니 가위바위보 시작하겠습니다.\n");
printf("10판 먼저 이긴사람이 코드의 신입니다.\n");

while(jteam!=10 && steam!=10) // 재일팀, 그리고 성일팀이 이긴횟수가 10이 아닐때까지 반복한다. 
                                           // 처음에는 jteam=10 || steam=10 으로 시도했었습니다. 
                                           // 재일팀이 10이거나, 성일팀이 10일 경우 종료된다는 느낌을 받았었습니다.
                                           // 하지만 오류가 났었습니다. 재일팀이 10이거나, 성일팀이 10일 경우까지 반복한다.
                                           // 안되는 이유는 명확히 생각이 나지 않습니다. 조금 더 공부가 필요할 것 같습니다.
 {
  printf("가위바위보를 시작하려면 1을 입력하세요. 0을 입력하면 종료됩니다. : ");
  scanf("%d", &game); // game에는 1입력할 시 가위바위보 시작, 0 입력하면 종료
  if(game==1) // while(반복)문안에 if(조건문) 들어갑니다. 
   {
        printf("---------------------------------\n"); // 위에 1과 0을 입력하는 행과 구분 짓기 위해 넣었습니다.
        printf("++가위 바위 보 시작++\n"); // 강조하기 위해 적었습니다.
        go = rand() %3 // 가위=0, 바위=1, 보=2 , 숫자 3에서 1을 뺀값, 즉 0,1,2 가 랜덤으로 생성됩니다.
        pa = rand() %3 // 위에 줄과 마찬가지입니다.
```
```
                if(go==0 && pa==0)  // while문 > if문 > if문 . 이유는? 랜덤으로 가위바위보 내고 그 이후에는 승자가 정해져야 한다.
                                             // 가위바위보의 가지수는 총 9개다. 
                                             // (가위 가위) (가위 바위) (가위 보) 
                                             // (바위 바위) (바위 가위) (바위 보)
                                             // (보 보) (보 가위) (보 바위)
                                             // 고연재가 가위를 내고, 박의용이 가위를 내는 조건문
                   {
                    cnt++; // 가위바위보 게임을 한판 할 때마다 증가하게 넣어주었습니다.
                             // 승률을 생각해보니 단순히 이긴 횟수 / 총 가위바위보 횟수 이렇게  생각해서 그랬습니다.
                    printf("연재:가위, 의용:가위 \n");
                    printf("무승부입니다\n"");
                    printf("이긴 횟수 재일: %d 성일: %d \n", jteam, steam); // 이긴 횟수 표시하게끔.
                    printf("총 가위바위보 한 횟수 : %d \n" cnt);
                    jrate = jteam/(double)cnt*100; // 한판 끝나고 승률 표시하기 위해 작성. 
                    srate = steam/(double)cnt*100; // double을 준 이유는 위에 int cnt로 해서 나누기가 안됬습니다.
                                                             // 100을 곱한 이유는 1/2 = 0.5입니다. 여기서 100을 곱하면 50이 되고
                                                             // 최종적으로 50%가 표시가 됩니다.(표시를 위해서)
                    printf("재일 승률 : %.3f %%, 성일 승률 : %.3f %%\n", jrate, srate); // 소수점 3자리까지 표현.
                  }
               else if(go==0 && pa==1) // 고연재가 가위를 내고, 박의용이 바위를 내는 조건문
                 {
                    cnt++;
                    printf("연재:가위, 의용:바위 \n");
                    printf("의용 속해 있는 팀 승리\n"");
                    if(team==1) // 재일팀 :의용 , 성일팀: 연재
                      jteam++;   // 위에 일 경우 재일팀의 승리회수가 1 증가한다.
                    else
                     steam++;   // 아닐 경우 성일팀의 승리회수가 1 증가한다.
                    printf("이긴 횟수 재일: %d 성일: %d \n", jteam, steam); // 이긴 횟수 표시하게끔.
                    printf("총 가위바위보 한 횟수 : %d \n" cnt);
                    jrate = jteam/(double)cnt*100; // 한판 끝나고 승률 표시하기 위해 작성. 
                    srate = steam/(double)cnt*100; // double을 준 이유는 위에 int cnt로 해서 나누기가 안됬습니다.
                                                             // 100을 곱한 이유는 1/2 = 0.5입니다. 여기서 100을 곱하면 50이 되고
                                                             // 최종적으로 50%가 표시가 됩니다.(표시를 위해서)
                    printf("재일 승률 : %.3f %%, 성일 승률 : %.3f %%\n", jrate, srate); // 소수점 3자리까지 표현.
                  }
```
```
        if(jteam==10 || steam==10) // 재일팀이 10번이겼거나 혹은 성일팀이 10번이겼을 경우
          {
            if(team==1) // 재일 팀 : 의용, 성일 팀: 연재일 경우
              {
                if(jteam>steam) // 재일팀이 성일팀보다 승리회수가 높으면
                  {
                    printf("최종승자는 재일입니다\n"); // 최종 승자 재일
                  }
                else(jteam<steam); // 성일 팀이 더 높으면
                  {
                    printf("최종승자는 성일입니다\n"); // 최종 승자 성일
                  }
              }
            else // 재일 팀 :연재 , 성일 팀: 의용 일 경우
              {
                if(jteam<steam) // 성일팀이 재일팀보다 승리회수가 높으면
                  {
                    printf("최종 승자는 성일입니다\n"); // 최종 승자 성일
                  }
                else // 재일팀이 성일팀보다 승리회수가 높으면
                  {
                    printf("최종 승자는 재일입니다\n"); // 최종 승자 재일
                  }
              }
          }
      }
      else if(game==0) // 0을 입력하면 
          break; // while문을 벗어난다.
  }
  return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233514295-98949dff-be26-4607-98a9-7a248a5e3ca3.png)

