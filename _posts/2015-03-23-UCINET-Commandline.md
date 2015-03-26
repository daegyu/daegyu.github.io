---
layout: post
Date: 2015-03-23
Tags: UCINET
---


## UCINET VI for Windows

[UCINET VI for Windows](https://sites.google.com/site/ucinetsoftware/home) 는 현재 사회연결망분석을 활용하는 학술연구에서 가장 많이 사용되는 사회연결망분석 패키지 프로그램이다. 이 프로그램이 널리 활용되는 가장 주된 이유는 GUI(Graphic User Interface)를 제공하고 있다는 점이다. 그러나, 연구와 분석을 원활하게 하기 위해서는 GUI가 아닌 commandline 형식의 명령어 입력으로 사회연결망분석을 할 필요가 있다. 이같은 편의를 위하여 UCINET VI는 commandline으로 명령을 입력할 수 있는 모듈을 제공 하고 있는데, 그다지 활용도가 높지 않은 형편이다.

개인적으로 UCINET VI를 활용하여 간단한 매트릭스 연산 등을 할 필요가 있었기 때문에, UCINET VI의 commandline을 사용해야 할 필요가 있었다. 그리고 UCINET의 Commandline이 생각 이상으로 잘 만들어져 있고 편리하다는 판단을 하게 되었다. 다만 UCINET VI의 고질적이라면 고질적인 문제, 그 활용법을 친절하게 알려주지 않는다는 것이 commandline에 사람들이 접근하지 못하게 만들어 놓았을 뿐이라는 생각이 들어서, 이 문서를 통해서 UCINET VI의 commandline의 활용법을 간단하게 한국어로 소개해보려고 한다.

## UCINET VI commandline

### 모듈의 위치

UCINET VI는 메뉴바를 통해서 포함하고 있는 각종 사회연결망분석의 도구들이 제공되고 있다. commandline의 접근 또한 이 메뉴바의 명령을 통해서 접근할 수 있다. 메뉴바의 **Tools> Command Line/Matrix Algebra**로 해서 찾아가거나, 혹은 단축키 **Ctrl + G** 를 통해서 **Matrix Algebra Command Line**이라는 commandline 모듈을 실행시킬 수 있다. 

### 모듈의 업데이트

UCINET VI는 꾸준히 업데이트가 되고 있다. 업데이트를 하는 이유는 첫째 버그를 수정하는 것이고, 둘째 새로운 기능을 추가하는 것이다. [UCINET Webpage](https://sites.google.com/site/ucinetsoftware/home)에서 UCINET 의 업데이트된 내용을 꾸준히 보고하고 있는데, 이 중에는 commandline에 GUI 모듈로만 제공되는 기능을 포함시키는 것들이 포함되어 있다. 가끔씩 이 업데이트 내용을 파악하게 되면 commandline에 포함되는 추가 기능들을 파악할 수 있을 것이다. 


## UCINET VI commandline 명령어

## 프롬프트
**Ctrl+G** 나 **Tools> Command Line/Matrix Algebra** 메뉴를 찾아서 모듈을 실행시키면 결과를 보여주는 넓은 영역과 명령어를 입력시키는 별도의 작은 영역으로 나뉘어져 있는 창이 뜨는 것을 볼 수 있다. 명령어의 입력은 아래의 **Typle command below:**라는 이름의 입력 영역에서 하게 되고, 그 결과는 상단의 넓은 영역에서 출력하여 보여준다. 이때 상단 영역은 UCINET VI만의 프롬프트를 보여줌으로써 명령을 대기하거나 결과를 출력하는 것을 표시한다. 

	->

## 사전 준비
1. UCINET VI는 명령 실행의 결과물을 모두 UCINET file(확장자가 .##h, .##d)들을 생성하여 저장시킨다. 여러 명령을 실행하다보면 그만큼 많은 결과의 UCINET file들이 쌓여가게 된다. 그러므로 이 결과물을 한 곳에 모아서 저장할 필요가 생기게 되는데, 이를 위해 현재 작업의 결과물들을 모을 위치를 컴퓨터에서 지정해줘야만 한다. UCINET VI 주메뉴에서 **File> Change Default Folder**로 작업 폴더를 지정하도록 한다 (단축키: **Ctrl+F**).

2. UCINET VI commandline은 matrix를 직접 입력하는 명령을 제공하고 있지 않(는 듯 하)다. 따라서 commandline을 활용하여 조작(manipulation)하고자 하는 대상의 matrix들을 위에서 지정한 작업폴더 안에 위치시키도록 한다. 최근 이같은 작업을 가능하게 하도록 하는 명령을 commandline이 추가하였으나, UCINET VI이 가장 최신 버전으로 업데이트 되어 있지 않을 경우 실행되지 않을 수 있으므로 최신 버전으로 업데이트하도록 한다.

## 명령어

### matrix 자료 불러들이기
UCINET VI commandline을 활용하기 위해서는 명령어들의 조작 대상이 되는 matrix들을 불러들여야 한다. 위에서 간단히 말한 것 같이 미리 UCINET의 **Data> Import Excel**, 혹은 **Data> Import text file** 등의 기능으로 UCINET file 형식의 matrix 자료를 미리 준비하는 것을 권한다. 최근 포함된 commandline 명령어 중 아래와 같은 것이 있다. 

#### edit 명령어

	-> edit X

명령어 edit  이후 matrix의 이름을 부여하여 실행시키면 UCINET data editor가 실행된(다고 한)다. UCINET data editor는 스프레드시트 형식으로 matrix 자료를 입력할 수 있게 한 별도의 모듈이다. 이것의 사용법은 여기서 별도로 설명하지 않는다. 

#### loaddl 명령어

	-> A = loaddl(dl.txt)

UCINET이 제시하는 matrix 자료 입력의 규격 형식인 DL 파일이 있는 경우, 위의 명령어를 통해서 A라는 이름의 matrix를 dl.txt 파일의 내용으로 만들어준다(고 한)다. DL 파일의 형식은 대단히 간단하고 명료하게 만들어져 있는 편이다. DL 파일 입력 형식에 관해서는 여기서는 별도로 소개하지 않는다. UCINET VI의 설치 폴더 어딘가에 포함되어 있는 UCINET VI Manual 파일을 참조하기 바란다. 

#### loadexcel 명령어

	-> A = loadexcel(excel.xls)

loaddl 명령어와 사용법은 유사하다. 위의 자료 불러들이기 명령들이 제대로 실행되지 않는 경우는 UCINET VI이 최신판으로 업데이트 되지 않았기 때문이니, 업데이트를 하도록 한다. 

### Batch 실행과 matrix 내용 보여주기

#### batch 명령어

	-> batch set_of_commands.txt

batch 명령어는 UCINET VI commandline의 명령어를 일괄적으로 순서에 맞춰서 실행할 필요가 있을 때 사용하는 명령어이다. 이를 위해 먼저 연속적으로 실행하고자 하는 명령어의 집합을 set_of_commands.txt 에 해당하는 text 파일 안에 포함시켜 놓아야 한다. 반복적인 작업을 수행하거나, GUI 모듈에서 번거롭게 거쳐야 하는 과정을 단순화시킬 때 사용하는 명령이다. 

#### display 명령어

	-> display A

A라는 matrix의 내용을 UCINET command 모듈의 상단 결과 출력 화면에서 보여주기 위해 사용하는 명령이다.

### Matrix 연산에 필요한 명령어

#### add 명령어

	-> R = add(X,Y)

matrix X와 Y의 합을 R이라는 matrix에 저장하는 명령어이다. 이때 매트릭스 연산이 가능하기 위한 조건이 지켜져야 한다 (matrix X와 Y는 동일한 size여야 한다).

#### subtract 명령어

	-> R = subtract(X,Y)

X와 Y의 차를 R에 저장한다.


#### product 명령어

	-> R = product(X,Y)

매트릭스 연산에서의 X와 Y의 곱을 구하여 R에 저장한다. 이때 매트릭스 연산의 곱을 위한 전제조건이 반드시 지켜져야 한다. X의 size가 n x m 이고 Y의 size가 m x p 로 matrix X의 column의 수와 Y의 row의 수가 일치하여야 한다. 


#### multiply 명령어

	-> R = multiply(X,Y)

multiply 명령어와 product 명령어의 차이를 이해하는 것이 중요하다. multiply 명령어는 동일한 size의 X와 Y의 셀 단위의 곱을 계산하여 그 결과를 역시 동일한 size인 R이라는 매트릭스에 담는 명령어이다. (cell-wise multiplication)

#### replacena 명령어

	-> R = replacena(X,Y)

matrix X에 결측치가 있을 때, matrix Y에서 그 결측치에 해당하는 셀의 값을 가지고 와서 X의 결측치에 대치시켜 넣는 명령어이다. 즉, matrix R은 X의 결측치를 Y의 값으로 보완한 것이 된다. 

### Socio-matrix 자료정리에 필요한 명령어

#### dichotomize 명령어

	-> X_dich = dichotomize(X, GT 0)

socio-matrix X가 valued matrix, 다시 말해 관계 값이 강도를 지니고 있을 때, cutting point를 정하여 X를 관계의 유무인 0과 1의 값을 지닌 binary matrix로 전환할 필요가 있을 때 이 명령어를 사용한다. X는 dichotomize의 대상이 되는 socio-matrix (square matrix의 성격을 지닌다)이며, 뒤에 따라오는 **GT 0**은 dichotomizing rule에 해당한다 (greater than 0). cutting point를 설정하는 방식은 GT(=greater than), GE(=greater than or equal to), EQ(=equal to), LE(=less than or equal to), LT(=less than)이 있다. 

#### symmetrize 명령어

	-> X_sym = dichotomize(X, maximum)

socio-matrix X가 관계의 방향성을 가지고 있을 때 방향성을 탈각시켜주는 명령어이다. symmetrizing rule은 maxinum, minimum 이 있다. 현재 이 명령어에서의 symmetrizing rule은 GUI 모듈로 제공되는 **Transform> Dichotomize**와 일치하지 않는 에러를 지니고 있다. GUI에서는 다양한 symmetrizing rule을 제공하고 있는 반면, commandline에서는 불완전/불충분 상태이다. 버그 수정이 요청되는 부분이다. 

### Social Network Analysis 명령어

UCINET VI commandline은 단순히 matrix algebra와 matrix manipulation 명령어만 제공하는 것이 아니라 Social network analysis를 구형하는 명령어들을 제공하고 있으며, UCINET VI 개발자들은 꾸준히 SNA 명령어들을 보충/확장해나가고 있는 중이다. 새로운 명령어들이 제공되는 여부는 UCINET webpage의update report를 꾸준히 follow-up해서 알아볼 수 있다. 


#### centrality 명령어

	-> X_cent = centrality(X)

X_cent 에 socio-matirx X의 각 노드들의 centrality 값들을 산출한다. degree, betweenness, closeness 등이 계산된다. X의 symmetric 특성 여부를 반영하여 in-degree/out-degree를 별도로 계산하여 주는 것을 확인하였다. 


#### holes 명령어

	-> X_holes = holes(X)

sociomatrix X의 각 노드들의 structural holes (Burt, 1992)을 산출한다. 

#### egodensity 명령어

	-> X_egoden = egodensity(X)

sociomatrix X의 각 노드들의 ego-centric matrix를 산출한 뒤, 각 ego-cengric matrix의 density를 계산한다. 

## 기타

UCINET VI commandline은 UCINET VI를 사회연결망분석에 활용하기를 원하지만, UCINET VI의 GUI가 번거롭고 속도가 느리다고 생각하는 사람들에게 분명히 유용한 기능임이 분명하다. 개발자들이 꾸준히 commandline에서 활용하는 명령어들을 확장하고 있기는 하지만, 여전히 제한적인 면이 없지 않음도 분명하다.

UCINET VI의 활용도가 높은 사람에게는 유용한 측면이 없지는 않지만, commandline 유형의 명령어를 사용하는 여타의 패키지들이 그 완성도가 높다는 점을 고려할 때 UCINET VI의 commandline은 제약이 있음을 어쩔 수 없다. 예를 들어 commandline의 포괄적인 사용설명서가 부족하고, help를 통해서 접하는 문서의 내용도 충분하지 못하다. 기능이 존재하고 있으나, 그 기능을 활용하게 하는 매뉴얼이 부재한 것도 활용도가 높지 못하게 하는 요인이다.

모순적이기는 하지만, 그럼에도 불구하고 UCINET VI가 사회연결망분석을 포함하는 연구논문에서 가장 많이 쓰이고 있다는 점을 고려할 때 UCINET VI commandline의 이해는 이같은 연구에 목적을 가지고 있는 사람들에게는 GUI의 번거로움을 해소시켜줄 수 있는 좋은 도구라는 점도 무시할 수 없겠다.

이 문서를 통해서 UCINET VI를 중급 이상으로 활용하기를 원하는 연구자들이 약간이라도 도움을 얻기 바란다. 


