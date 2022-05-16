# C언어 GCD, LCM 구하기

GCD : 최대공약수

LCM : 최소공배수

1. 하나씩 늘려가거나 줄여가면서 구하기

   ```c
   int GDB(int A, int B) {
   	int m = A > B ? B : A; // A,B중에서 작은 수
   	for (int i = m; i >=1 ; i--) { //하나씩 줄여가면서 가장 큰 공약수 구하기
   		if (A % i == 0 && B % i == 0) //두 수로 둘다 나누어 떨어지면 공약수임
   			return i;
   	}
   }
   
   int LCM(int A, int B) {
   	int M = A > B ? A : B, i; // A,B중에서 큰 수
   	for (i = M; ; i++) {//하나씩 늘려가면서 가장 작은 공배수 구하기
   		if (i % A == 0 && i % B == 0) // 두 수로 둘 다 나누어 떨어지면 공배수임
   			return i;
   	}
   }
   ```

2. 유클리드 호제법 이용하기

   ```c
   int GCD(int A, int B) {
   	int n;
   	while (B != 0) { //0이 아닐때까지 반복
   		n = A % B; 
   		A = B;
   		B = N;
   	}
   	return A;
   }
   
   int LCM(int A, int B) {
   	return A * B / GCD(A, B); //두 수 곱하고 최대공약수로 나누기
   }
   ```

3. 유클리드 호제법-

   ```c
   int GCD(int a, int b){
   	int max = (a < b) ? a : b; //작은수
   	for (int i = max; i > 0; i--) { // 줄여가면서 가장 큰 공약수 찾기
   		if (a % i == 0 && b % i == 0) //나누어떨어지는 수 있으면 저장하고 바로 나가기
   		{
   			max = i;
   			break;
   		}
   	}
       return max;
   }
   
   int LCM(int a, int b)
   {
   	int min = a * b / GCD(a,b); //두 수 곱하고 최대공약수로 나누기
   	return min;
   }
   ```

   