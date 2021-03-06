---
layout: post
title: '카카오 신입 공채 3차 코딩 테스트 문제 해설'
author: danny.park
date: 2017-11-14 11:20
tags: [blind-recruitment,coding]
image: /files/covers/employment_cover.png
---

블라인드 채용으로 관심을 모은 카카오 신입 공채의 세 번째 테스트가 지난 10월 29일(일), 오후 2시부터 6시까지 네 시간에 걸쳐 오프라인으로 치러졌습니다. 두 차례의 온라인 테스트를 통과한 지원자들이 한 자리에 모여 다시 한번 실력을 검증하는 자리를 가졌습니다.

# 세 번째 관문
오프라인 코딩 테스트는 온라인 코딩 테스트와는 사뭇 달랐습니다. 1차와 2차 코딩 테스트에서 상위권의 우수한 성적을 거뒀던 지원자가 3차 코딩 테스트의 관문을 통과하지 못한 경우도 있었습니다. 현장에 와서 다른 지원자와 함께 경쟁한다는 긴장감도 있을 테고요. 자신이 쓰던 집이나 학교의 컴퓨터가 아니어 불편했을 겁니다. OS나 IDE 등의 개발 환경도 평소 자신이 쓰던 것과 달랐을 겁니다. 특히나 문제를 풀다가 막혔을 때 애용하던 “검색 찬스”도 쓸 수 없을 테고요.

1차 코딩 테스트에서 Java 언어 사용자들이 고전했다면, 2차와 3차 코딩 테스트에서는 C++ 사용자들이 힘들어했습니다.
1차 응시자들은 대부분 3차 코딩 테스트에서도 같은 언어로 시험을 봤습니다. 다만, 1차에서 여러 언어를 사용하던 지원자들은 3차에서는 절반 가량이 Python을 주 언어로 코딩 테스트에 참가했습니다.

이번 3차 테스트에서는 코딩 테스트와 함께 지원자들의 컴퓨팅 관련 기본 지식을 묻는 필기 시험도 함께 치러졌습니다. 사전에 알리지 않고 현장에 와서 필기 시험이 치러진다는 안내를 받고 조금은 놀라셨을 텐데요. 평소 실력이 있는 지원자들인지라 대부분 잘 답하셨더군요.

합격 기준은 코딩 문제 5 문제 중 3 문제 이상, 필기 시험 40점 이상을 기준으로 삼았습니다. 필기 시험은 준비없이 치렀다는 점을 고려하여 기준을 낮게 잡았습니다.


# 코딩 문제 설명
이번 3차 테스트에서는 코딩 테스트로 다섯 문제를 준비했습니다. 1차 테스트처럼 기초적인 구현 능력을 검증하는 문제들입니다. 1차 테스트와 난이도 면에서 크게 차이는 없지만, 조금은 더 복합적으로 생각하고 구현해야 하는 문제들이 많았습니다.

## 문제1. N진수 게임
튜브가 활동하는 코딩 동아리에서는 전통적으로 해오는 게임이 있다. 이 게임은 여러 사람이 둥글게 앉아서 숫자를 하나씩 차례대로 말하는 게임인데, 규칙은 다음과 같다.

1. 숫자를 0부터 시작해서 차례대로 말한다. 첫 번째 사람은 0, 두 번째 사람은 1, … 열 번째 사람은 9를 말한다.
1. 10 이상의 숫자부터는 한 자리씩 끊어서 말한다. 즉 열한 번째 사람은 10의 첫 자리인 1, 열두 번째 사람은 둘째 자리인 0을 말한다.

이렇게 게임을 진행할 경우,<br>
```0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 1, 0, 1, 1, 1, 2, 1, 3, 1, 4, …```<br>
순으로 숫자를 말하면 된다.

한편 코딩 동아리 일원들은 컴퓨터를 다루는 사람답게 이진수로 이 게임을 진행하기도 하는데, 이 경우에는<br>
```0, 1, 1, 0, 1, 1, 1, 0, 0, 1, 0, 1, 1, 1, 0, 1, 1, 1, …```<br>
순으로 숫자를 말하면 된다.

이진수로 진행하는 게임에 익숙해져 질려가던 사람들은 좀 더 난이도를 높이기 위해 이진법에서 십육진법까지 모든 진법으로 게임을 진행해보기로 했다. 숫자 게임이 익숙하지 않은 튜브는 게임에 져서 벌칙을 받는 굴욕을 피하기 위해, 자신이 말해야 하는 숫자를 스마트폰에 미리 출력해주는 프로그램을 만들려고 한다. 튜브의 프로그램을 구현하라.

### 입력 형식
진법 `n`,  미리 구할 숫자의 갯수 `t`, 게임에 참가하는 인원 `m`, 튜브의 순서 `p` 가 주어진다.

* 2 ≦ `n` ≦ 16
* 0 ＜ `t` ≦ 1000
* 2 ≦ `m` ≦ 100
* 1 ≦ `p` ≦ `m`

### 출력 형식
튜브가 말해야 하는 숫자 `t`개를 공백 없이 차례대로 나타낸 문자열. 단, `10`~`15`는 각각 대문자 `A`~`F`로 출력한다.

### 입출력 예제

| n | t | m | p | result |
| - | - | - | - | - |
| 2 | 4 | 2 | 1 | "0111" |
| 16 | 16 | 2 | 1 | "02468ACE11111111" |
| 16 | 16 | 2 | 2 | "13579BDF01234567" |

> ### 문제 해설
> 반복문과 진법 변환을 할 수 있다면 어렵지 않게 풀 수 있는 문제입니다. 진법 변환은 프로그래밍 언어를 처음 배울 때 연습 문제로 많이 풀어봤을 문제일 텐데요. 오래간만에 풀어보려니 쉽지만은 않았던 듯 싶습니다.
> 
> 참고로 이 문제는 [챔퍼나운 수](https://en.wikipedia.org/wiki/Champernowne_constant)라는 수학 상수를 이용한 문제입니다.
> 
> 이 문제의 정답률은 91.85%였습니다. 대부분 잘 풀어주셨으나, 언어별로는 C++ 사용자들이 약간 어려워했습니다.

## 문제2. 압축
신입사원 어피치는 카카오톡으로 전송되는 메시지를 압축하여 전송 효율을 높이는 업무를 맡게 되었다. 메시지를 압축하더라도 전달되는 정보가 바뀌어서는 안 되므로, 압축 전의 정보를 완벽하게 복원 가능한 무손실 압축 알고리즘을 구현하기로 했다.

어피치는 여러 압축 알고리즘 중에서 성능이 좋고 구현이 간단한 **LZW**(Lempel–Ziv–Welch) 압축을 구현하기로 했다. LZW 압축은 1983년 발표된 알고리즘으로, 이미지 파일 포맷인 GIF 등 다양한 응용에서 사용되었다.

LZW 압축은 다음 과정을 거친다.

1. 길이가 1인 모든 단어를 포함하도록 사전을 초기화한다.
2. 사전에서 현재 입력과 일치하는 가장 긴 문자열 `w`를 찾는다.
3. `w`에 해당하는 사전의 색인 번호를 출력하고, 입력에서 `w`를 제거한다.
4. 입력에서 처리되지 않은 다음 글자가 남아있다면(`c`), `w+c`에 해당하는 단어를 사전에 등록한다.
5. 단계 2로 돌아간다.

압축 알고리즘이 영문 대문자만 처리한다고 할 때, 사전은 다음과 같이 초기화된다. 사전의 색인 번호는 정수값으로 주어지며, 1부터 시작한다고 하자.

| 색인 번호 | 1 | 2 | 3 | ... | 24 | 25 | 26 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 단어 | A | B | C | ... | X | Y | Z |

예를 들어 입력으로 `KAKAO`가 들어온다고 하자.

1. 현재 사전에는 `KAKAO`의 첫 글자 `K`는 등록되어 있으나, 두 번째 글자까지인 `KA`는 없으므로, 첫 글자 `K`에 해당하는 색인 번호 11을 출력하고, 다음 글자인 `A`를 포함한 `KA`를 사전에 27 번째로 등록한다.
2. 두 번째 글자 `A`는 사전에 있으나, 세 번째 글자까지인 `AK`는 사전에 없으므로, `A`의  색인 번호 1을 출력하고, `AK`를 사전에 28 번째로 등록한다.
3. 세 번째 글자에서 시작하는 `KA`가 사전에 있으므로, `KA`에 해당하는 색인 번호 27을 출력하고, 다음 글자 `O`를 포함한 `KAO`를 29 번째로 등록한다.
4. 마지막으로 처리되지 않은 글자 `O`에 해당하는 색인 번호 15를 출력한다.

| 현재 입력(w) | 다음 글자(c) | 출력 | 사전 추가(w+c) |
| --- | --- | --- | --- |
| K | A | 11 | 27: KA |
| A | K | 1 | 28: AK |
| KA | O | 27 | 29: KAO |
| O | | 15 | |

이 과정을 거쳐 다섯 글자의 문장 `KAKAO`가 4개의 색인 번호 [11, 1, 27, 15]로 압축된다.

입력으로 `TOBEORNOTTOBEORTOBEORNOT`가 들어오면 다음과 같이 압축이 진행된다.

| 현재 입력(w) | 다음 글자(c) | 출력 | 사전 추가(w+c) |
| --- | --- | --- | --- |
| T | O | 20 | 27: TO |
| O | B | 15 | 28: OB |
| B | E | 2 | 29: BE |
| E | O | 5 | 30: EO |
| O | R | 15 | 31: OR |
| R | N | 18 | 32: RN |
| N | O | 14 | 33: NO |
| O | T | 15 | 34: OT |
| T | T | 20 | 35: TT |
| TO | B | 27 | 36: TOB |
| BE | O | 29 | 37: BEO |
| OR | T | 31 | 38: ORT |
| TOB | E | 36 | 39: TOBE |
| EO | R | 30 | 40: EOR |
| RN | O | 32 | 41: RNO |
| OT | | 34 | |

### 입력 형식
입력으로 영문 대문자로만 이뤄진 문자열 `msg`가 주어진다. `msg`의 길이는 1 글자 이상, 1000 글자 이하이다.

### 출력 형식
주어진 문자열을 압축한 후의 사전 색인 번호를 배열로 출력하라.

### 입출력 예제

| msg | answer |
| --- | --- |
| `KAKAO` | [11, 1, 27, 15] |
| `TOBEORNOTTOBEORTOBEORNOT` | [20, 15, 2, 5, 15, 18, 14, 15, 20, 27, 29, 31, 36, 30, 32, 34] |
|`ABABABABABABABAB` | [1, 2, 27, 29, 28, 31, 30] |

> ### 문제 해설
> GIF 파일 등에서 실제로 쓰이는 [LZW 알고리즘](https://en.wikipedia.org/wiki/Lempel–Ziv–Welch)을 설명해주고, 구현하는 문제입니다. 실제로 쓰이는 알고리즘을 구현해보는 것이 어떠셨나요? 압축이라는 말만으로 얼핏 어려워 보이지만, 설명에 나온 의사코드<sup>Pseudocode</sup>를 그대로 따라서 구현만 하면 되는 문제로, 기초적인 문자열과 배열을 다룰 수 있다면 풀 수 있는 문제입니다.
> 
> 이 문제의 정답률은 95.80%입니다. 가장 많은 지원자가 잘 풀어주셨습니다. 언어별로는 Java 언어 사용자들이 조금 어려워했습니다.

## 문제3. 파일명 정렬
세 차례의 코딩 테스트와 두 차례의 면접이라는 기나긴 블라인드 공채를 무사히 통과해 카카오에 입사한 무지는 파일 저장소 서버 관리를 맡게 되었다.

저장소 서버에는 프로그램의 과거 버전을 모두 담고 있어, 이름 순으로 정렬된 파일 목록은 보기가 불편했다. 파일을 이름 순으로 정렬하면 나중에 만들어진 ver-10.zip이 ver-9.zip보다 먼저 표시되기 때문이다.

버전 번호 외에도 숫자가 포함된 파일 목록은 여러 면에서 관리하기 불편했다. 예컨대 파일 목록이 ["img12.png", "img10.png", "img2.png", "img1.png"]일 경우, 일반적인 정렬은 ["img1.png", "img10.png", "img12.png", "img2.png"] 순이 되지만, 숫자 순으로 정렬된 ["img1.png", "img2.png", "img10.png", img12.png"] 순이 훨씬 자연스럽다.

무지는 단순한 문자 코드 순이 아닌, 파일명에 포함된 숫자를 반영한 정렬 기능을 저장소 관리 프로그램에 구현하기로 했다.

소스 파일 저장소에 저장된 파일명은 100 글자 이내로, 영문 대소문자, 숫자, 공백(" "), 마침표("."), 빼기 부호("-")만으로 이루어져 있다. 파일명은 영문자로 시작하며, 숫자를 하나 이상 포함하고 있다.

파일명은 크게 HEAD, NUMBER, TAIL의 세 부분으로 구성된다.

* HEAD는 숫자가 아닌 문자로 이루어져 있으며, 최소한 한 글자 이상이다. 
* NUMBER는 한 글자에서 최대 다섯 글자 사이의 연속된 숫자로 이루어져 있으며, 앞쪽에 0이 올 수 있다. `0`부터 `99999` 사이의 숫자로, `00000`이나 `0101` 등도 가능하다.
* TAIL은 그 나머지 부분으로, 여기에는 숫자가 다시 나타날 수도 있으며, 아무 글자도 없을 수 있다.

| 파일명 | HEAD | NUMBER | TAIL |
| --- | --- | --- | --- |
| `foo9.txt` | `foo` | `9` | `.txt` |
| `foo010bar020.zip` | `foo` | `010` | `bar020.zip` |
| `F-15` | `F-` | `15` | (빈 문자열) |

파일명을 세 부분으로 나눈 후, 다음 기준에 따라 파일명을 정렬한다.

* 파일명은 우선 HEAD 부분을 기준으로 사전 순으로 정렬한다. 이때, 문자열 비교 시 대소문자 구분을 하지 않는다. `MUZI`와 `muzi`, `MuZi`는 정렬 시에 같은 순서로 취급된다.
* 파일명의 HEAD 부분이 대소문자 차이 외에는 같을 경우, NUMBER의 숫자 순으로 정렬한다. 9 < 10 < 0011 < 012 < 13 < 014 순으로 정렬된다. 숫자 앞의 0은 무시되며, 012와 12는 정렬 시에 같은 같은 값으로 처리된다.
* 두 파일의 HEAD 부분과, NUMBER의 숫자도 같을 경우, 원래 입력에 주어진 순서를 유지한다. `MUZI01.zip`과 `muzi1.png`가 입력으로 들어오면, 정렬 후에도 입력 시 주어진 두 파일의 순서가 바뀌어서는 안 된다.

무지를 도와 파일명 정렬 프로그램을 구현하라.

### 입력 형식
입력으로 배열 `files`가 주어진다.

* `files`는 1000 개 이하의 파일명을 포함하는 문자열 배열이다.
* 각 파일명은 100 글자 이하 길이로, 영문 대소문자, 숫자, 공백(" "), 마침표("."), 빼기 부호("-")만으로 이루어져 있다. 파일명은 영문자로 시작하며, 숫자를 하나 이상 포함하고 있다.
* 중복된 파일명은 없으나, 대소문자나 숫자 앞부분의 0 차이가 있는 경우는 함께 주어질 수 있다. (`muzi1.txt`, `MUZI1.txt`, `muzi001.txt`, `muzi1.TXT`는 함께 입력으로 주어질 수 있다.)

### 출력 형식
위 기준에 따라 정렬된 배열을 출력한다.

### 입출력 예제

입력: ["img12.png", "img10.png", "img02.png", "img1.png", "IMG01.GIF", "img2.JPG"]<br>
출력: ["img1.png", "IMG01.GIF", "img02.png", "img2.JPG", "img10.png", "img12.png"]

입력: ["F-5 Freedom Fighter", "B-50 Superfortress", "A-10 Thunderbolt II", "F-14 Tomcat"]<br>
출력: ["A-10 Thunderbolt II", "B-50 Superfortress", "F-5 Freedom Fighter", "F-14 Tomcat"]

> ### 문제 해설
> 코딩의 기초 문제라고 할 수 있는 정렬 문제입니다. 하지만 조건은 꽤나 복합적입니다. 파일명을 세 부분으로 나눠, 첫 부분은 대소문자 구분 없이<sup>Case Insensitive</sup>, 다음 부분은 숫자 값에 따라<sup>Numerical</sup> 정렬해야 합니다. 또한 정렬 기준에 따라 차이가 없다면 원래 입력에서 주어진 순서를 유지하는 안정 정렬<sup>Stable Sort</sup>을 사용해야 합니다. 정렬 문제를 풀 때 한 번씩은 다 해보셨죠? 그런데 이걸 어떻게 꿰어서 하나의 프로그램으로 만들어야 할지 어려워하시더군요.
> 
> 여러 정렬 알고리즘을 배우셨을 텐데요. 이 중에 안정 정렬이 어떤 건지 알고 계신가요? 빠른 정렬 알고리즘으로 가장 유명한 퀵 정렬<sup>Quick Sort</sup>는 아쉽게도 안정 정렬이 아닙니다. 효율이 좋은 O(n log n) 복잡도의 정렬 알고리즘 중에는 병합 정렬<sup>Merge Sort</sup> 등 일부 알고리즘은 안정 정렬이고요. 효율이 떨어지는 O(n<sup>2</sup>) 복잡도의 알고리즘 중 버블 정렬<sup>Bubble Sort</sup>과 삽입 정렬<sup>Insertion Sort</sup>은 모두 안정 정렬입니다. 여러분이 아는 다른 알고리즘도 안정 정렬인지 아닌지 확인해보세요. 알고리즘의 구현 방법에 따라 같은 알고리즘이라도 안정 정렬이거나 아닐 수도 있습니다.
> 
> 정렬 문제가 워낙 많이 쓰이므로 많은 프로그래밍 언어에서 정렬 알고리즘을 기본 함수로 제공하고 있습니다. 자신이 사용하는 프로그래밍 언어에서 안정 정렬 알고리즘을 제공해주는지 알아두시는 게 좋습니다. 코딩 테스트에서 사용된 프로그래밍 언어 중 C++과 Python에는 안정 정렬이 있고, Java와 JavaScript, Swift에는 안정 정렬이 없습니다. PHP 언어는 숫자 값을 고려해 정렬하는 [natsort()](http://php.net/manual/en/function.natsort.php)를 기본 함수로 제공하기도 합니다. (아쉽게도 문제 3과 조건이 달라 그대로는 쓸 수 없지만요.)
> 
> 기본 정렬 함수가 안정 정렬을 지원하지 않거나, 이 문제처럼 비교 조건이 까다로운 경우에는 [decorate-sort-undecorate 패턴](https://en.wikipedia.org/wiki/Schwartzian_transform)을 이용해서 쉽게 해결할 수도 있답니다.
> 
> 이 문제의 정답률은 66.95%였습니다. 언어별로는 C++과 Python 사용자들이 힘들어했습니다. 안정 정렬을 지원해주는 언어인데 도움이 안 되었나 봅니다.

## 문제4. 방금그곡
라디오를 자주 듣는 네오는 라디오에서 방금 나왔던 음악이 무슨 음악인지 궁금해질 때가 많다. 그럴 때 네오는 다음 포털의 '방금그곡' 서비스를 이용하곤 한다. 방금그곡에서는 TV, 라디오 등에서 나온 음악에 관해 제목 등의 정보를 제공하는 서비스이다.

네오는 자신이 기억한 멜로디를 가지고 방금그곡을 이용해 음악을 찾는다. 그런데 라디오 방송에서는 한 음악을 반복해서 재생할 때도 있어서 네오가 기억하고 있는 멜로디는 음악 끝부분과 처음 부분이 이어서 재생된 멜로디일 수도 있다. 반대로, 한 음악을 중간에 끊을 경우 원본 음악에는 네오가 기억한 멜로디가 들어있다 해도 그 곡이 네오가 들은 곡이 아닐 수도 있다. 그렇기 때문에 네오는 기억한 멜로디를 재생 시간과 제공된 악보를 직접 보면서 비교하려고 한다. 다음과 같은 가정을 할 때 네오가 찾으려는 음악의 제목을 구하여라.

* 방금그곡 서비스에서는 음악 제목, 재생이 시작되고 끝난 시각, 악보를 제공한다.
* 네오가 기억한 멜로디와 악보에 사용되는 음은 C, C#, D, D#, E, F, F#, G, G#, A, A#, B 12개이다.
* 각 음은 1분에 1개씩 재생된다. 음악은 반드시 처음부터 재생되며 음악 길이보다 재생된 시간이 길 때는 음악이 끊김 없이 처음부터 반복해서 재생된다.  음악 길이보다 재생된 시간이 짧을 때는 처음부터 재생 시간만큼만 재생된다.
* 음악이 00:00를 넘겨서까지 재생되는 일은 없다.
* 조건이 일치하는 음악이 여러 개일 때에는 라디오에서 재생된 시간이 제일 긴 음악 제목을 반환한다. 재생된 시간도 같을 경우 먼저 입력된 음악 제목을 반환한다.
* 조건이 일치하는 음악이 없을 때에는 "`(None)`"을 반환한다.

### 입력 형식
입력으로 네오가 기억한 멜로디를 담은 문자열 `m`과 방송된 곡의 정보를 담고 있는 배열 `musicinfos`가 주어진다.

* `m`은 음 `1`개 이상 `1439`개 이하로 구성되어 있다.
* `musicinfos`는 `100`개 이하의 곡 정보를 담고 있는 배열로, 각각의 곡 정보는 음익이 시작한 시각, 끝난 시각, 음악 제목, 악보 정보가 '`,`'로 구분된 문자열이다.
  * 음악의 시작 시각과 끝난 시각은 24시간 `HH:MM` 형식이다.
  * 음악 제목은 '`,`' 이외의 출력 가능한 문자로 표현된 길이 `1` 이상 `64` 이하의 문자열이다.
  * 악보 정보는 음 `1`개 이상 `1439`개 이하로 구성되어 있다.

### 출력 형식
조건과 일치하는 음악 제목을 출력한다.

### 입출력 예시

| m | musicinfos | answer |
| - | - | - |
| "ABCDEFG" | ["12:00,12:14,HELLO,CDEFGAB", "13:00,13:05,WORLD,ABCDEF"] | "HELLO" |
| "CC#BCC#BCC#BCC#B" | ["03:00,03:30,FOO,CC#B", "04:00,04:08,BAR,CC#BCC#BCC#B"] | "FOO" |
| "ABC" | ["12:00,12:14,HELLO,C#DEFGAB", "13:00,13:05,WORLD,ABCDEF"] | "WORLD" |

### 입출력 설명
* 첫 번째 예시에서 HELLO는 길이가 7분이지만 12:00부터 12:14까지 재생되었으므로 실제로 CDEFGABCDEFGAB로 재생되었고, 이 중에 기억한 멜로디인 ABCDEFG가 들어있다.
* 세 번째 예시에서 HELLO는 C#DEFGABC#DEFGAB로, WORLD는 ABCDE로 재생되었다. HELLO 안에 있는 ABC#은 기억한 멜로디인 ABC와 일치하지 않고, WORLD 안에 있는 ABC가 기억한 멜로디와 일치한다.

> ### 문제 해설
> 부분 문자열 비교를 묻는 문제입니다. 하지만 멜로디의 각 음을 나타내는 글자가 한 글자일 수도 있고, 두 글자일 수도 있습니다. “ABC”라는 멜로디는 “ABCD”라는 악보에는 들어있지만, “ABC#”라는 악보에는 들어있지 않습니다. C#이 하나의 음을 이루고 있기 때문이죠.
> 
> 문자열 비교에서 이런 문제를 처리해야 할 일이 있습니다. 
> 1차 코딩 테스트에서 설명했던 토큰화<sup>Tokenizing</sup>를 통해 “ABC#”을 [“A”, “B”, “C#”] 식의 배열로 변환한 후에 비교를 수행할 수도 있고요. 아니면 두 글자로 된 “C#”, “D#”, “F#” 등을 악보에서 사용되지 않는 문자인 “c”, “d”, “e” 등으로 치환<sup>Substitution</sup>한 후에 문자열 비교 함수를 이용할 수도 있습니다.
> 
> 이 문제의 정답률은 47.50%였습니다. Python 사용자들이 가장 잘 풀었습니다.

## 문제5. 자동완성
포털 다음에서 검색어 자동완성 기능을 넣고 싶은 라이언은 한 번 입력된 문자열을 학습해서 다음 입력 때 활용하고 싶어 졌다. 예를 들어, `go` 가 한 번 입력되었다면, 다음 사용자는 `g` 만 입력해도 `go`를 추천해주므로 `o`를 입력할 필요가 없어진다! 단, 학습에 사용된 단어들 중 앞부분이 같은 경우에는 어쩔 수 없이 다른 문자가 나올 때까지 입력을 해야 한다.
효과가 얼마나 좋을지 알고 싶은 라이언은 학습된 단어들을 찾을 때 몇 글자를 입력해야 하는지 궁금해졌다.

예를 들어, 학습된 단어들이 아래와 같을 때

```
go
gone
guild
```

- `go`를 찾을 때 `go`를 모두 입력해야 한다.
- `gone`을 찾을 때 `gon` 까지 입력해야 한다. 
  (`gon`이 입력되기 전까지는 `go` 인지 `gone`인지 확신할 수 없다.)
- `guild`를 찾을 때는 `gu` 까지만 입력하면 `guild`가 완성된다.

이 경우 총 입력해야 할 문자의 수는 `7`이다.

라이언을 도와 위와 같이 문자열이 입력으로 주어지면 학습을 시킨 후, 학습된 단어들을 순서대로 찾을 때 몇 개의 문자를 입력하면 되는지 계산하는 프로그램을 만들어보자.

### 입력 형식
학습과 검색에 사용될 중복 없는 단어 `N`개가 주어진다. 
모든 단어는 알파벳 소문자로 구성되며 단어의 수 `N`과 단어들의 길이의 총합 `L`의 범위는 다음과 같다.

- 2 <= `N` <= 100,000
- 2 <= `L` <= 1,000,000

### 출력 형식
단어를 찾을 때 입력해야 할 총 문자수를 리턴한다.

### 입출력 예제

| words | result |
| - | - |
| ["go","gone","guild"] | 7 |
| ["abc","def","ghi","jklm"] | 4 |
| ["word","war","warrior","world"] | 15 |

### 입출력 설명
- 첫 번째 예제는 본문 설명과 같다.
- 두 번째 예제에서는 모든 단어들이 공통된 부분이 없으므로, 가장 앞글자만 입력하면 된다.
- 세 번째 예제는 총 `15` 자를 입력해야 하고 설명은 아래와 같다.
   - `word`는 `word` 모두 입력해야 한다.
   - `war`는 `war` 까지 모두 입력해야 한다.
   - `warrior`는 `warr` 까지만 입력하면 된다.
   - `world`는 `worl`까지 입력해야 한다. (`word`와 구분되어야 함을 명심하자)

> ### 문제 해설
> 3차 코딩 테스트에서 가장 어려운 문제였습니다. 열심히 코딩한 후에 제출하면 시간 제한에 걸려 좌절하는 지원자가 많았습니다. 두 단어 “world”와 “word”가 앞 세 글자가 겹친다는 걸 찾는 건 어렵지 않지만, 모든 단어 쌍을 비교하는 방식으로는 제한 시간 내에 풀 수 없습니다.
> 
> 이 문제 해결에 적합한 자료 구조로 트라이<sup>[Trie](https://en.wikipedia.org/wiki/Trie)</sup>가 있습니다. 입력으로 주어진 단어로 트라이를 구성하면, 같은 접두어<sup>Prefix</sup>를 갖는 단어가 얼마나 있는지를 효과적으로 찾을 수 있습니다.
> 
> 또 다른 방법이 하나 더 있는데요. 전체 단어를 사전 순으로 정렬한다면, 어떤 단어와 앞부분이 가장 많이 일치하는 단어는 정렬 후 인접한 두 단어 중 하나가 됩니다. 이 방법을 이용하면 모든 단어 쌍이 아닌, 정렬 후에 인접한 단어 쌍만 비교하면 되므로 빠르게 문제를 해결할 수 있습니다.
> 
> 이 문제의 정답률은 34.07%였습니다. Java 사용자들이 가장 잘 풀었습니다.


# 필기 시험
아마, 많은 지원자 분들이 필기 시험이 등장하여 적잖이 당황스러우셨을 겁니다. 알고리즘을 묻는 코딩 테스트 만으로는 자칫 채용 시험이 코딩 대회의 장이 될 수 있어 이를 보완하고자 기본 지식을 묻는 필기 시험을 추가하기로 했습니다. 필기 시험이 있다는 사실은 당일까지도 공지하지 않고 대외비로 준비했는데요. 대신 사전 학습 없이도 평소에 컴퓨터 과학을 공부했다면 누구나 쉽게 풀 수 있는, 상식 수준에 준하는 문제들로 출제하였습니다.

> [필기 시험 PDF 다운로드](/files//kakao-blind-recruitment.pdf)

문제는 총 20문제로 구성하였습니다.

이 중 10번까지는 빈칸을 채우는 문제였습니다. 컴퓨팅 및 컴퓨터 과학, 인터넷 등의 기본적인 개념에 대한 영어 위키백과의 설명을 제시하고 각각 무엇을 설명하는 지를 맞추는 문제였습니다.

현업에서 일을 하려면 평소에도 영어로 된 문서를 많이 접하게 될 텐데요. 따라서 문제 또한 모두 영어로 제시하여 독해 능력도 함께 보고자 했고, 각각의 문항 앞뒤로 충분한 부연 설명을 제시하여 최소한 이 정도 용어는 알고 있으면 좋겠다는 출제 의도를 포함했습니다.

사실 이 문제들은 문장을 검색해보면 금방 정답을 찾을 수 있습니다. 그러나, 검색 없이도 이 정도 용어들은 바로 대답할 수 있길 바랬고, 인터넷이 제한된 오프라인 테스트여서 가능한 문제들이었습니다.

11번은 조금 어려운 문제였던 거 같습니다. TCP의 커넥션 종료 과정의 순서를 묻는 문제였는데요.  순서보다 좀 더 정확히는 active close와 passive close를 숙지하고 있는지를 묻고 싶었습니다.
실무에서 TIME_WAIT으로 인한 문제는 여전히 간간히 발생하고 있으므로 이 개념은 꼭 숙지했으면 하는 의도로 출제하였습니다.
더 깊은 이야기는 카카오 기술 블로그에 올라왔던 [CLOSE_WAIT & TIME_WAIT 최종 분석](http://tech.kakao.com/2016/04/21/closewait-timewait/) 글을 읽어보세요.

12번은 제록스 팔로알토 연구소에서 1979년에 소개한, 소프트웨어 구조를 설명한 사실상 최초의 방법론이자 여전히 중요하게 쓰이고 있는 [MVC 소프트웨어 디자인 패턴](https://en.wikipedia.org/wiki/Model–view–controller)에 대한 문제입니다.

13, 14, 15번 문제는 시간 복잡도, 빅오를 구하는 문제였는데요. 13번의 경우 실행 순서를 손으로 그려본다면 2<sup>n</sup>이 됨을 알 수 있습니다. 14, 15번은 상수항이 있는데요. 빅오에서는 일반적으로 상수항을 제거하기 때문에 각각 n이 됩니다. 특히 14번의 경우 ½ n이 되는데, 이는 log n과 혼동할 수 있으나 엄연히 전혀 다릅니다. 따라서 상수항 ½ 이 제거되어 n이 됩니다.

16번은 재밌는 문제인데요. 약간의 함정이 숨어 있는데 각각의 시간 복잡도를 계산해보면, len(A) = N, len(B) = M 이라 할 때, A를 정렬할 경우 정렬과 이진 검색을 합하면 N log N + M log N = (N+M) log N, B를 정렬할 경우 M log M + N log M = (N+M) log M 이 됩니다. 길이가 짧은 A를 정렬하는 쪽이 좀 더 빠르게 동작하겠죠?

17, 18, 19번은 적합한 자료 구조를 묻는 문제였고 어렵지 않게 풀 수 있었으리라 생각합니다. 18번의 경우 위키백과에도 인덱스 구현에 대한 설명<sup>[참고](https://en.wikipedia.org/wiki/Database_index#Index_implementations)</sup>이 등장합니다. 인기 있는 인덱스 구현  자료구조는 균형 트리, B+ 트리, 해시라고 나오네요.

20번은 트리 순회를 직접 계산해보는 문제입니다. 알고리즘을 설명에 상세히 제시하였기 때문에 기존에 트리 순회 알고리즘을 몰랐던 분들도 충분히 쉽게 풀 수 있었으리라 생각합니다.


# 마무리하며
코딩 테스트 참가자들의 메일이나 후기로 블라인드 테스트에 대한 많은 의견들을 들을 수 있었습니다. 1차 코딩 테스트 후기에서 언급되었던 것처럼 채용을 위한 시험이기에  이번 세 차례의 블라인드 테스트는 어려운 문제보다는 기본기를 확인하기 위한 기본적인 문제 중심으로 출제했으며, 실무에서 접할 수 있을법한 문제 중심으로 구성했습니다.

세 차례의 코딩 테스트를 통과한 지원자들은 이제 또다시 두 차례의 면접이 기다리고 있습니다. 코딩 테스트를 통해 다양한 방식으로 개발 역량을 검증했다면, 면접은 카카오에서 함께 일할 수 있는 사람인지를 확인하는 과정입니다. 카카오 크루로 함께 일할 수 있게 되길 기대해보겠습니다.


> **함께 보기:**
>
> * [카카오 블라인드 신입 개발자 공채를 실시합니다!](http://tech.kakao.com/2017/08/30/employment/)
> * [카카오 신입 공채 1차 코딩 테스트 문제 해설](http://tech.kakao.com/2017/09/27/kakao-blind-recruitment-round-1/)
> * [카카오 신입 공채 2차 코딩 테스트 문제 해설](http://tech.kakao.com/2017/10/24/kakao-blind-recruitment-round-2/)
