20-09-24 C Study (Day 13)
=====
교제 : 윤성우의 열혈 C 프로그래밍

chapter 18

<hr>

## 2차원 배열이름의 포인터 형

1차원 배열의 포인터형은 `int *arr[4];` 이런 식으로 선언을 했던 기억이 있다.  
그런데 2차원 배열은 `int *arr[3][4]` 이런 식으로 선언을 하는 것인지  
이렇게 `int **arr` 더블 포인터형인지 의문이 든다.  

### 2차원 배열의 의미

`int arr2d[3][4];`  
위와 같은 2차원 배열을 선언했다 하자.  
위의 배열에서 `arr2d[0], arr2d[1], arr2d[2]`는 각각의 행의 첫번째 요소를 의미한다.  
그런데 `arr2d`이런 배열의 이름도 `arr2d[0]`와 같은 기능을 할 수 있지 않은지에 대한 의문이 든다.  

```c
int main() {
	int arr2d[3][4];
	printf("%d %d \n", sizeof(arr2d[0]), sizeof(arr2d));
	return 0;
}
```
위의 코드의 출력결과는 `16 48`이다.  

출력 결과로 `sizeof(arr2d[0])`는 1행의 크기가 `sizeof(arr2d)`는 배열 전체의 크키가 반환 되었음을 유추할 수 있다.  
이를 통해 `arr2d[i]`는 i행의 첫번째 요소를 의미하고 `arr2d`는 전체 배열의 첫번째 요소를 의미한다는 것을 알 수 있다.

### 2차원 배열이름 기반의 포인터 연산: 덧셈

`int arr[6];`  
`arr+2;` 이 식의 의미는 arr의 3번째 요소의 주소 값과 같다.  
그렇다면 2차원 배열에서는 어떻게 동작하는지 궁금해진다.  

```c
int main() {
	int arr2d[3][4];
	printf("%p %p %p \n", arr2d, arr2d+1, arr2d+2);
	return 0;
}
```
위의 결과를 보면 주소 값의 차이가 16이다.
2차원 배열의 포인터 덧셈 연산의 +1은 `sizeof(int)*(행의 개수)`인 것이다.