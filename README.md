# 정규 표현식

정규식, Regular Expression

## 역할

- 문자검색(search)
- 문자대체(replace)
- 문자추출(extract)

## 테스트 사이트

https://regexr.com/

## 정규식 생성

```js
// 생성자
new RegExp('표현', '옵션')
new RegExp('[a-z]', 'gi')

//리터럴
/표현/옵션
/[a-z]/gi
```

## 예제 문자

```js
const str = `
010-1111-1111
thesecon@gmail.com
https://www.omdbapi.com/?apikey=7035c60c&s=frozen
The quick brown fox jumps over the lazy dog.
abbcccdddd
`
```

## 메소드

const regexp = /정규식표현/옵션<br>


메소드 | 문법 | 설명 | 예시
--|--|--|--
test | `정규식.test(문자열)` | 일치 여부(boolean) 반환 | `regexp.test(str)`
match | `문자열.match(정규식)` | 일치하는 문자의 배열반환 | `str.match(regexp)`
replace | `문자열.replace(정규식, 대체문자)` | 일치하는 문자를 대체 | `str.replace(regexp, 'aaa')`

## 플래그(옵션)

플래그 | 설명
--|--
g | 모든 문자 일치 (global)
i | 영어 대소문자를 구분하지 않고 일치 (ignore case)
m | 여러 줄 일치 (multi line)

나머지는 블로그 참고 

## 패턴(표현)

패턴 | 설명
--|--
^ab | 줄 시작에 있는 ab와 일치
ab$ | 줄 끝에 있는 ab와 일치
. | 임의의 한 문자와 일치
a\|b | a 또는 b와 일치
ab? | b가 없거나 b와 일치
{3} | 3개 연속 일치
{3,} | 3개 이상 연속 일치
{3,5} | 3개 이상 5개 이하 연속 일치
[abc] | a 또는 b 또는 c 
[a-z] | a부터 z 사이의 문자 구간에 일치 (영어 소문자)
[A-Z] | A부터 Z 사이의 문자 구간에 일치 (대문자)
[0-9] | 0부터 9 사이의 문자 구간에서 일치
[가-힣] | 가부터 힣 사이의 문자 구간에 일치(한글)
\w | 63개 문자 (word, 대소영문 52개 + 숫자 10개 + _)에 일치
\b | 63개 문자에 일치하지 않는 문자 경계(boundary) ex. 특수문자
\d | 숫자(digit)에 일치
\s | 공백(space, tap)에 일치
(?=) | 앞쪽일치(lookahead)
(?<=) | 뒤쪽일치(lookbehind)

.은 패턴으로 사용되기때문에 정말 단순히 .을 말하는 거면 앞에 \를 붙여줌