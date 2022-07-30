# find-the-number-of-factors
# c program
# Find the number between the value entered on the left and the value entered on the right, adding the number of even divisors and subtracting the odd number of divisors! 왼쪽에 입력된 값부터 오른쪽에 입력된 값까지 사이에 있는 값들의 약수의 개수가 짝수인 수를 더하고 약수의 개수가 홀수인 수는 뺀 수를 구해라!
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>

int solution(int left, int right) {
    int answer = 0;
    int num,i,count;
    for(num=left;num<=right;num++){
        count=(num==1)?1:2; //num이 1이면 자기자신이 약수이고 2이면 1과 자기자신이다!
        for(i=2;i<=num/2;i++){ //약수는 값을 2로 나눈것보다 크지않다.
            if(num%i==0){
                count++;
            }
        }
        answer+=(count%2==0)?num:-num; //약수의 개수가 짝수면 +하고 홀수이면 -를 한다.
    }
    return answer;
}
int main(void){
    solution(13,17);
    return 0;
}
#result--> 43 이유는 13+14+15-16+17=43
