# 파이썬 객체지향 프로그래밍

이 코드는 파이썬으로 짠 성적 프로그래밍을 객체지향 프로그래밍으로 수정하였습니다.

## 📋 코드 예제
```dart
'''
1. 3명의 학생의 성명, 국,영,수 점수를 입력받아 각 학생별 합, 총점을 출력하고맨 마지막줄에 과목별 합, 평균, 전체학생 합 평균을 출력하는 것을 수정
2. 특정 학생의 이름과 변경할 과목, 값을 입력받아 해당값을 변경하는 기능 추가
3. 메뉴 : "전체학생 출력", "특정학생 성적 변경"
'''
# 학생 데이터 저장 리스트
list1 =[]
list2 = []

# 3명 학생 입력
for _ in range(3):
    list1.append(input("이름: "))
    list1.append(int(input("국어 성적: ")))
    list1.append(int(input("영어 성적: ")))
    list1.append(int(input("수학 성적: ")))
    list2.append(list1)
    list1 = []
    

def print_all():
    total_kor = 0
    total_eng = 0
    total_math = 0
    total_all = 0

    print("\n성명  국  영  수  합  평균")
    for stu in list2:
        total = stu[1] + stu[2] + stu[3]
        avg = total / 3
        print(f"{stu[0]:4} {stu[1]:3} {stu[2]:3} {stu[3]:3} {total:4} {avg:6.1f}")
        total_kor += stu[1]
        total_eng += stu[2]
        total_math += stu[3]
        total_all += total

    avg_kor = total_kor / 3
    avg_eng = total_eng / 3
    avg_math = total_math / 3
    avg_all = total_all / 3

    print("-" * 34)
    print(f"{'총합':4} {total_kor:3} {total_eng:3} {total_math:3}     ")
    print(f"{'평균':4} {avg_kor:3.0f} {avg_eng:3.0f} {avg_math:3.0f}     ")
    print()

def update_score():
    name = input("성적을 수정할 학생 이름: ")

    for stu in list2:
        if stu[0] == name:
            print(f"{name}의 새로운 성적을 입력하세요:")
            stu[1] = int(input("국어 성적: "))
            stu[2] = int(input("영어 성적: "))
            stu[3] = int(input("수학 성적: "))
            print(f"{name}의 성적이 수정되었습니다.\n")
            return

    print("학생을 찾을 수 없습니다.\n")

# 메뉴 루프
if __name__ == '__main__' :
    print_all()
    while True:
        print("메뉴: 1. 전체학생 출력  2. 특정학생 성적 변경  0. 종료")
        choice = input("선택 >> ")

        if choice == "1":
            print_all()
        elif choice == "2":
            update_score()
        elif choice == "0":
            print("프로그램을 종료합니다.")
            break
        else:
            print("잘못된 입력입니다. 다시 선택하세요.\n")


```

## 🖥️ 실행 결과
| 예제 실행 화면 |
|:---------------:|
| ![실행결과 화면](https://raw.githubusercontent.com/damuljang1547/flutterwork/main/img/python_grad.png) |
