# CA_3_test
#### 해당 repository는 CA_3 과제 검증셋이다.
* 가장 먼저 git clone을 이용해 사용자의 local 폴더로 해당 repository를 가져온다.
<pre><code>git clone https://github.com/gosury32/CA_3_test.git</code></pre>

# 1. 컴파일
* 먼저 다음 명령어와 같은 형식으로 소스코드 컴파일을 진행한다. (컴파일 옵션으로 -o runfile을 부여하는 것을 추천)
<pre><code>gcc -o runfile [your_source_code_file].cpp</code></pre>
</br>

# 2. sample.o에 대한 실행 결과 저장
* sample.o는 atp 및 antp의 옵션에 따른 결과의 차이가 없다. 따라서 atp, antp옵션의 구현에 확신이 있다면 홀수번째 결과 혹은 짝수번째 결과만 비교하여도 무방하다.

### 홀수번째 실행 결과만을 저장하기 위한 명령어 (-atp인 경우)
<pre><code>mkdir result1_odd && 
  ./runfile -atp sample.o -n 0 -m 0x400000:0x400050 >> result1_odd/result1_1.txt && 
  ./runfile -atp sample.o -m 0x10000000:0x10000010 >> result1_odd/result1_3.txt && 
  ./runfile -atp sample.o -m 0x10000000:0x10000010 -d >> result1_odd/result1_5.txt && 
  ./runfile -atp sample.o -m 0x10000000:0x10000010 -d -p >> result1_odd/result1_7.txt && 
  ./runfile -atp sample.o -m 0x10000000:0x10000010 -d -p -n 5 >> result1_odd/result1_9.txt &&
  ./runfile -atp sample.o -m 0x10000000:0x10000010 -d -p -n 15 >> result1_odd/result1_11.txt && 
  ./runfile -atp sample.o >> result1_odd/result1_13.txt</code></pre>
### 짝수번째 실행 결과만을 저장하기 위한 명령어 (-antp인 경우)
<pre><code>mkdir result1_even && 
  ./runfile -antp sample.o -n 0 -m 0x400000:0x400050 >> result1_even/result1_2.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 >> result1_even/result1_4.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 -d >> result1_even/result1_6.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 -d -p >> result1_even/result1_8.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 -d -p -n 5 >> result1_even/result1_10.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 -d -p -n 15 >> result1_even/result1_12.txt && 
  ./runfile -antp sample.o >> result1_even/result1_14.txt</code></pre>
### 전체 실행 결과를 저장하기 위한 명령어
<pre><code>mkdir result1 && 
  ./runfile -atp sample.o -n 0 -m 0x400000:0x400050 >> result1/result1_1.txt && 
  ./runfile -antp sample.o -n 0 -m 0x400000:0x400050 >> result1/result1_2.txt && 
  ./runfile -atp sample.o -m 0x10000000:0x10000010 >> result1/result1_3.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 >> result1/result1_4.txt && 
  ./runfile -atp sample.o -m 0x10000000:0x10000010 -d >> result1/result1_5.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 -d >> result1/result1_6.txt && 
  ./runfile -atp sample.o -m 0x10000000:0x10000010 -d -p >> result1/result1_7.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 -d -p >> result1/result1_8.txt && 
  ./runfile -atp sample.o -m 0x10000000:0x10000010 -d -p -n 5 >> result1/result1_9.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 -d -p -n 5 >> result1/result1_10.txt && 
  ./runfile -atp sample.o -m 0x10000000:0x10000010 -d -p -n 15 >> result1/result1_11.txt && 
  ./runfile -antp sample.o -m 0x10000000:0x10000010 -d -p -n 15 >> result1/result1_12.txt && 
  ./runfile -atp sample.o >> result1/result1_13.txt && ./runfile -antp sample.o >> result1/result1_14.txt</code></pre>
#### 각 명령어에 따라 result1_odd, result1_even, reslut1이라는 폴더에 해당 txt결과들이 저장된다.
</br>

# 3. sample2.o에 대한 실행 결과 저장
* sample2.o는 atp 및 antp의 옵션에 따른 결과의 차이가 존재하기 때문에 전체 결과를 다 비교하여야 한다.
### 전체 실행 결과를 저장하기 위한 명령어
<pre><code>mkdir result2 && 
  ./runfile -atp sample2.o -n 0 -m 0x400000:0x400030 >> result2/result2_1.txt && 
  ./runfile -antp sample2.o -n 0 -m 0x400000:0x400030 >> result2/result2_2.txt && 
  ./runfile -atp sample2.o -m 0x10000000:0x10000004 >> result2/result2_3.txt && 
  ./runfile -antp sample2.o -m 0x10000000:0x10000004 >> result2/result2_4.txt && 
  ./runfile -atp sample2.o -m 0x10000000:0x10000004 -d >> result2/result2_5.txt && .
  /runfile -antp sample2.o -m 0x10000000:0x10000004 -d >> result2/result2_6.txt && 
  ./runfile -atp sample2.o -m 0x10000000:0x10000004 -d -p >> result2/result2_7.txt && 
  ./runfile -antp sample2.o -m 0x10000000:0x10000004 -d -p >> result2/result2_8.txt && 
  ./runfile -atp sample2.o -m 0x10000000:0x10000004 -d -p -n 10 >> result2/result2_9.txt && 
  ./runfile -antp sample2.o -m 0x10000000:0x10000004 -d -p -n 10 >> result2/result2_10.txt && 
  ./runfile -atp sample2.o -m 0x10000000:0x10000004 -d -p -n 20 >> result2/result2_11.txt && 
  ./runfile -antp sample2.o -m 0x10000000:0x10000004 -d -p -n 20 >> result2/result2_12.txt && 
  ./runfile -atp sample2.o -m 0x10000000:0x10000004 -d -p -n 30 >> result2/result2_13.txt && 
  ./runfile -antp sample2.o -m 0x10000000:0x10000004 -d -p -n 30 >> result2/result2_14.txt && 
  ./runfile -atp sample2.o >> result2/result2_15.txt && 
  ./runfile -antp sample2.o >> result2/result2_16.txt</code></pre>
#### reslut2라는 폴더에 해당 txt결과들이 저장된다.
</br>

# 4. 각 sample.o의 txt파일 결과 설명
* result1_1.txt : Instruction 메모리 초기화 확인 (atp)
* result1_2.txt : Instruction 메모리 초기화 확인 (antp)
* result1_3.txt : 최종 결과 확인 (atp)
* result1_4.txt : 최종 결과 확인 (antp)
* result1_5.txt : 최종 과정 및 결과 확인 (atp)
* result1_6.txt : 최종 과정 및 결과 확인 (antp)
* result1_7.txt : 최종 파이프라인 과정 및 결과 확인 (atp)
* result1_8.txt : 최종 파이프라인 과정 및 결과 확인 (antp)
* result1_9.txt : -n 옵션 사용시 결과 확인1 (atp)
* result1_10.txt : -n 옵션 사용시 결과 확인1 (antp)
* result1_11.txt : -n 옵션 사용시 결과 확인2 (atp)
* result1_12.txt : -n 옵션 사용시 결과 확인2 (antp)
* result1_13.txt : 선택 옵션이 없는 경우 (atp)
* result1_14.txt : 선택 옵션이 없는 경우 (antp)
</br>

# 5. 각 sample2.o의 txt파일 결과 설명
* result2_1.txt : Instruction 메모리 초기화 확인 (atp)
* result2_2.txt : Instruction 메모리 초기화 확인 (antp)
* result2_3.txt : 최종 결과 확인 (atp)
* result2_4.txt : 최종 결과 확인 (antp)
* result2_5.txt : 최종 과정 및 결과 확인 (atp)
* result2_6.txt : 최종 과정 및 결과 확인 (antp)
* result2_7.txt : 최종 파이프라인 과정 및 결과 확인 (atp)
* result2_8.txt : 최종 파이프라인 과정 및 결과 확인 (antp)
* result2_9.txt : -n 옵션 사용시 결과 확인1 (atp)
* result2_10.txt : -n 옵션 사용시 결과 확인1 (antp)
* result2_11.txt : -n 옵션 사용시 결과 확인2 (atp)
* result2_12.txt : -n 옵션 사용시 결과 확인2 (antp)
* result2_13.txt : -n 옵션 사용시 결과 확인3 (atp)
* result2_14.txt : -n 옵션 사용시 결과 확인3 (antp)
* result2_15.txt : 선택 옵션이 없는 경우 (atp)
* result2_16.txt : 선택 옵션이 없는 경우 (antp)
</br>

# 6. result_choi 폴더
* 이 안에는 비교할 결과의 txt파일이 저장되어있다. 아래의 사이트를 통해 각 txt파일들의 결과를 비교할 수 있다.  
#### &emsp; url : https://wepplication.github.io/tools/compareDoc/
</br>

# 7. ./choi 실행파일
* 더 많은 엣지 케이스나 옵션에 대한 결과를 비교하고 싶으면 choi실행파일에 원하는 옵션을 주어 나온 결과를 자신의 결과와 비교할 수 있다.
#### 예시)
<pre><code>./choi -atp sample.o -n 12 -d</code></pre>
</br>

### Updated by ChoiJongHyeon on May 20, 2024
