---
title: "Anaconda Virtual Environment"
date: 2021-07-11T08:08:50-04:00
category: Programming
tags:
  - Anaconda
  - virtual environment
---

miniconda 가 Anaconda보다 훨씬 가볍기 때문에, Miniconda를 설치할 것을 추천한다.  
또한 miniconda 설치시 설치 경로에 띄어쓰기가 들어가지 않도록 주의해야 한다. 몇몇 패키지의(예: assimulo) 설치에 문제가 생길 수 있기 때문. 
"사용자"가 아닌 "공용"으로 쓰도록 miniconda를 설치하고 필요한 가상환경이나 패키지가 있을 경우에는 prompt를 사용자 권한으로 실행시킨 후 각각 설치하는 것이 깔끔하다. 이렇게 하면 miniconda는 C:\ProgramData 에 설치되게 된다.  

## 가상환경 확인하기
conda info &#8209;&#8209;envs  

## 가상환경 생성하기
conda create -n 가상환경이름 python=버전  

## 가상환경 라이브러리 확인하기
conda list  

## 가상환경 삭제하기
conda remove -n 가상환경이름 &#8209;&#8209;all  

## 가상환경 활성화하기
conda activate 가상환경이름  

## 가상환경 비활성화하기
conda deactivate  

## 가상환경 복사하기
conda create -n 복사된_가상환경이름 &#8209;&#8209;clone 복사할_가상환경이름  

## 라이브러리(패키지) 관리
pip freeze > requirements.txt  


[아나콘다 가상환경의 개념 및 활용방법](https://yganalyst.github.io/pythonic/anaconda_env_1/)
