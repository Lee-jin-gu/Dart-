# Dart 기본 문법 정리
Dart 언어 기본 문법 정리

## 1. 기본 출력문
>Print를 통해 콘솔에 출력을 할 수 있다

    void main() {
    print("Hello World");
    }

## 2. 변수 선언 및 연산자
>Var, Int, Double, Boolean, String, Dynamic 등 변수 선언 방식이다.

>더하기 곱하기 등 많은 연산자의 사용 예시이다.

    void main() {
        // Var -> 가변적으로 변수가 지정됨(모든 타입 선언 가능)
        var string_test = '김진구'; // 문자열 String
        var int_test = 5; // 숫자열 Int
        var double_test = 2.5; // 숫자열 Double
        
        
        // Int -> 숫자 타입 변수 정수
        int num1 = 10;
        int num2 = 20;
        int num3 = num1 + num2; // 10+20인 30이 num3에 할당
        
        // Double -> 숫자 타입 변수 숫자
        double number1 = 2.5;
        double number2 = 1.5;
        
        // Boolean -> 불린 타입 변수 True/False
        bool isTrue = true;
        bool isFalse = false;
        
        // String -> 문자 타입 변수
        String name1 = '이진구';
        String name2 = '김진구';
        
        // dynamic -> 가변적으로 변수가 지정됨(모든 타입 선언 가능 or 타입 변경 가능)
        dynamic change = '이진구';
        change = 2;
        var change2 = '이진구';
        change2 = 2; // change2에 할당된 최초 타입이 Char 이므로
        
        
        //숫자열 연산자
        print(num1+num2); // 더하기
        print(num1-num2); // 빼기
        print(num1/num2); // 나누기
        print(num1*num2); // 곱하기
        print(num1%num2); // 나머지 Ex) 3%2 = 1
        
        //문자열 연산자
        print(name1 + name2); // 출력결과 : 이진구김진구
    }

# 3. nullable, non-nullable
>기본적으로 변수 선언시, Null 값 지정이 불가능하다.

>변수 지정문 이후 물음표를 붙히게 되면 Null 지정이 가능하다.

>사용할 변수 이후 느낌표를 붙히게 되면 무조건적으로 null값이 아님을 의미한다.

>변수에 값을 지정하지 않고, 변수명만 선언을 하는 경우 물음표를 붙여야 한다.

    void main() {
        String name = '이진구';
        name = null; // 에러 발생
        
        String? name2 = '이진구';
        name2 = null;
        
        print(name2!);

        String? a; // 값 지정 X 변수명 할당 O
    }


# 4. Final, Const
1. Final, Const는 값 선언 시 변경이 불가능하다.
2. 안에 변수 타입을 제거하면, 자동적으로 Var와 같이 타입이 지정된다.
3. 코드가 컴퓨터 언어로 변경되는 단계를 컴파일 / 컴파일 이후 코드가 실행되는 단계를 런타임이라고 한다.
4. Final은 런타임 시점에 할당이 된다.
5. Const는 컴파일 시점에 할당이 된다.
6. 하기 코드의 DateTime.now 는 코드가 실행되는 당시, 즉 런타임 시점을 가져온다.
7. 따라서 Final은 선언이 가능, Const는 선언시 에러가 발생한다.
---
    void main() {
        final String name = '이진구';
        const String name2 = '이진구';
        final name3 = '이진구'; //자동적으로 String으로 할당
        const name4 = '이진구'; //자동적으로 String으로 할당
        name = '김진구'; //에러발생
        final DateTime now = DateTime.now();
        const DateTime now2 = DateTime.now(); // 에러 발생
    }

# 5. Operator
>사칙연산및 조건부 연산, 비교 등의 연산자의 예시.

    void main() {
        int num = 1;
        
        num ++ ; // 기존 변수에 + 1 현재 num : 2
        num -- ; // 기존 변수에 - 1 현재 num : 1
        num +=5; // 기존 변수에 + 5 현재 num : 6
        num *=2; // 기존 변수에 * 2 현재 num : 12
        
        num ??= 3; // 만약 num이 Null 이라면 3을 선언, 아니면 기존값 유지
        
        print(num);
        
        int num1 = 1;
        int num2 = 2;
        
        print(num1 > num2); // num1이 num2보다 큰가? -> 출력값 False
        print(num1 < num2); // num1이 num2보다 작은가? -> 출력값 True
        print(num1 >= num2); // num1이 num2보다 크거나 같은가? -> 출력값 False
        print(num1 <= num2); // num1이 num2보다 작거나 같은가? -> 출력값 True
        print(num1 == num2); // num1과 num2가 같은가? -> 출력값 False
        print(num1 != num2); // num1과 num2이 다른가? -> 출력값 True

        
        print(num1 is int); // num1의 타입이 Int인가? => True
        print(num1 is String); // num1의 타입이 String인가? => False
        print(num1 is! String); //num1의 타입이 String이 아닌가? => True
        
        bool result = 12 > 10 ; //12가 10보다 크므로 result = True;
        bool result1 = 12 > 10 && 9 > 10; // 12가 10보다 큼과 동시에, 9가 10보다 큰가? -> False( 앞 뒤 조건이 충족 )
        bool result2 = 12 > 10 || 9 > 10; // 12가 10보다 크거나, 9가 10보다 큰가? => True ( 앞에 조건이 충족 )
    }


# 6. List 변수
>List 변수 형태, 타입을 지정할 수 있다.

>데이터 중복이 가능하다 Ex) ['a','a'];

    void main() {
        List<String> name = ['진구','준우'];
        List<int> number = [1,2,3,4];
        
        print(name); // 출력 : [진구, 준우]
        print(number); // 출력 : [1, 2, 3, 4]
        
        //Index는 0번째부터 시작한다.
        //Name의 0번쨰는 진구, 2번째는 준우
        
        print(name[0]); // 출력 : 진구
        print(number[1]); //출력 2
        
        //print(name[2]); // name의 2번째 값이 없음으로 에러
        
        print(name.length); //List name의 길이, 출력 : 2
        
        name.add('준서'); //List에 값이 추가된다.
        
        print(name); // 출력 : [진구, 준우, 준서]
        
        print(name.indexOf('준서')); //값의 위치, 출력    
    }

# 7. Map 변수
>Key와 Value형태를 가진 데이터 타입, Key Value의 변수 타입을 지정해줘야한다

>Key는 중복값으로 들어갈 수 없다.

>데이터 추가 시, Key가 있을경우 Value가 업데이트된다.

>데이터 추가 시, Key가 없는 경우 Key Value 형태로 생성된다.

    void main() {
        Map<String, int> age ={
            '이진구' : 20,
            '여준우' : 18,
            '김준서' : 3,
        };
        
        print(age);
        // 출력 : {이진구: 20, 여준우: 18, 김준서: 3}
        
        age.addAll({ // 값 추가 방식 1
            '박찬희' : 5,
            '이진구' : 15,
        });
        // 없었던 Key와 Value는 생성, 있었던 Key는 Value가 업데이트
        
        print(age['이진구']); // 출력 : 15
        
        
        age['배화'] = 19; // 값 추가 방식 2
        
        age.remove('이진구'); // Key : 이진구 < 인 데이터가 삭제됨
        
        print(age.keys); // Key 값만 가져옴
        //출력 : (여준우, 김준서, 박찬희, 배화)
        
        print(age.values); // Value 값만 가져옴
        //출력 : (18, 3, 5, 19)
    }

# 8. Set 변수
>기본적으론 List와 유사하다.

>List는 중복 값이 들어갈 수 있지만, Set은 자동 중복 제거가 된다.

    void main() {
        Set<String> name={
            '이진구',
            '김진구',
            '박진구',
            '이진구' //앞에 이진구가 있음으로 중복 제거됨.
        };
        
        print(name); 
        //출력 : {이진구, 김진구, 박진구}
        
        name.add('진진구'); //name에 진진구 추가
        
        name.remove('진진구'); //name에 진진구 삭제
    }

# 9. IF
>조건을 걸어서 로직을 수행하게 한다.

>조건 후 Else를 사용하여 조건의 값이 아닌 모든 상황을 처리한다.

>조건 후 Else IF 를 사용하여 다중적으로 조건을 걸 수 있다.

    void main() {
        int number = 2;
        
        if(number % 2 == 0){
            print('짝수');
        }else{
            print('홀수');
        }
        // N을 2로 나눴을 때, 나머지가 0이면 짝수 출력
        // N을 2로 나눴을 때, 나머지가 0이 아니면 홀수 출력
        
        if(number == 1){
            print('1');
        }else if(number == 3){
            print('3');
        }else if(number == 2){
            print('2');
        }else{
            print('그 외');
        }
        //Number가 1,2,3 일때 각각 1,2,3을 출력, 그 외면 '그 외' 출력
        //number는 현재 2 이므로 2 출력 후 If문 종료
    }

# 10. Switch
>조건을 걸어서 로직을 수행하게 한다.

>Case안에 Break가 없는 경우 모든 Case를 조회하기때문에, 통상적으로 Break를 사용한다.

    void main() {
        int number = 2;
        
        switch(number % 2){
            case 0:
                print('나머지가 0');
                break;
            case 1:
                print('나머지가 1');
                break;
            default:
                print('그 외');
                break;
        }
    }
    //2를 2로 나눴을 경우, 나머지가 0이므로 '나머지가 0'이 출력되고 Switch 문 종료.

# 11. For 문
>여러 로직을 상황에따라 반복할 때 사용

>기본적으로 for(선언, 조건, 증감식){수행코드} 형태로 사용한다.


    void main() {
        for(int i = 0; i < 10; ++i){
            print(i);
        }
        //1. 값이 0인 i를 선언한다. (int i = 0)
        //2. 조건문을 확인한다. (i<10)
        //3. print(i)가 실행된다 ※초기값 0이므로 0 출력
        //4. 수식을 실행한다 (i++)
        //5. 2로 돌아간다.
        //출력 : 0 1 2 3 4 5 6 7 8 9
        
        int total = 0;
        List<int> numbers = [1,2,3,4,5];
        
        for(int i=0;i<numbers.length;i++){
            total += numbers[i];
        }
        //numbers의 크기만큼 반복한다.
        //total의 numbers[i]번째(0,1,2..)의 값을 더한다.
        
        print(total); // 출력 : 15
        
        // 확장 For 문, List 크기만큼 도는 For문
        // 하기와 상기의 For문은 일치하다.
        total = 0;
        for(int i in numbers){
            total+= i;
        }
        
        
        print(total); // 출력 : 15
    }

# 12. While 문
>기본적으로 For문과 비슷하게 수행된다.

>보편적으로 While을 많이 쓴다.

>Do while은 조건과 관계 없이 무조건 1회 수행된다.

    void main() {
        int total = 0;
        
        while(total < 10){
            print(total);
            total +=1;
        }
        //1. 조건문을 실행한다.
        //2. 실행문을 실행한다..
        //3. 1로 돌아간다.
        //출력 : 0~9
        
        
        total = 0;
        do{
            print(total);
            total+=1;
        }while(total<10);
        //1. Do 안에 있는것을 실행한다.
        //2. 조건문을 실행한다.
        //3. 1로 돌아간다.
        //출력 : 0 ~ 10
        print(total);
    }


# 13. Break, Continue 
>통상적으로 조건에 부합할 시 Break, Continue를 함

>Continue 사용 시 당 회의 반복을 건너뜀.

>Break 사용 시 해당 반복문을 멈춤.

    void main() {
        int total = 0;
        
        while(total < 10){
            if(total == 5){
            total +=100;
            continue;
            }
            total +=1;
        }
        //5에서 조건문 타고 멈춤
        print(total);
        
        
        total = 0;
        do{
            total+=1;
            if(total % 2 == 0){
            continue;
            }
            print(total);
        }while(total<10);
        //1. 짝수면 당 회를 건너뛴다.
        //출력 : 1,3,5,7,9
    }

# 14. Enum
> 코드 가독성 및 상태관리를 위해 사용한다.

> 타입 생성의 안정성이 보장된다.

> 열거형태로 사용됨을 명시한다.

    void main() {
        Status status = Status.ok;
        
        if(status == Status.ok){
            print('OK입니다.');
        }
    }

    enum Status{
        ok,
        no,
        check
    }

# 15. Function
>같은 동작을 여러번 수행할때 함수화 시켜서 사용한다.

>예를 들어, 세가지의 숫자를 계속 해서 더할 일이 있다면, 그 로직을 함수화한다.

>단순 수행이 아니더라도, Return을 통해 값을 반환해 줄 수도 있음.


    void main() {
        print(addNumber(5,4,3));
        addNumber2(5,4,3);
        addNumber3(5);
        addNumber4(a:5,b:4,c:3);
        addNumber5(a:5,b:4);
        }

        // 세개의 숫자 (a, b, c)를 더하고 홀, 짝 인지 값을 Return 해주는 함수
        String addNumber(int a, int b, int c){
        int d = a+b+c;
        if(d % 2 ==0){
            return "짝수";
        }else{
            return "홀수";
        }
        }

        // 세개의 숫자 (a, b, c)를 더하고 홀, 짝 인지 출력하는 함수
        void addNumber2(int a, int b, int c){
        int d = a+b+c;
        if(d % 2 ==0){
            print("짝수");
        }else{
            print("홀수");
        }
        }

        // 하기 함수는 a,b,c 중 a값만 들어와도 돌아감 b,c는 있어도 그만 없어도 그만, 허나 b,c의 기본값이 있어야됨
        void addNumber3(int a, [int b=4, int c=3]){
        int d = a+b+c;
        if(d % 2 ==0){
            print("짝수");
        }else{
            print("홀수");
        }
        }

        // 하기 함수는 함수의 순서와 상관없이 이름에 값을 지정해서 넣어줌, b:4,a:5,c:3의 순서도 가능.
        void addNumber4({
        required int a,
        required int b,
        required int c,
        }){
        int d = a+b+c;
        if(d % 2 ==0){
            print("짝수");
        }else{
            print("홀수");
        }
        }

        // 하기 함수는 a,b,c 중 a,b값만 들어와도 돌아감 c는 있어도 그만 없어도 그만, 허나 c의 기본값이 있어야됨
        void addNumber5({
        required int a,
        required int b,
        int c = 3,
        }){
        int d = a+b+c;
        if(d % 2 ==0){
            print("짝수");
        }else{
            print("홀수");
        }
    }

# 16. Arrow Function
> 기본적으로 함수기능은 같으나 형태가 Arrow형태로 바뀐 함수이다.

    void main() {
    print(addNumber(5,4,3));

    }

    // 세개의 숫자 (a, b, c)를 더하고 홀, 짝 인지 값을 Return 해주는 함수
    int addNumber(int a, int b, int c) => a+b+c;

# 17. Typedef
>함수의 형식을 명명하는 방식이다.

>유지보수 및 재사용성이 높아진다.

    void main() {
        int result = calculate(10,20,30,add);
        int result2 = calculate(10,20,30,subtract);
        print(result);
        print(result2);
    }

    typedef Operation = int Function(int x, int y, int z);
    //typedef로 함수 정의
    int add(int x, int y, int z)=> x+y+z;

    int subtract(int x, int y, int z)=> -x-y-z;

    int calculate(int x, int y, int z, Operation operation){
        return operation(x,y,z); 
    }
