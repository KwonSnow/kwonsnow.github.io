---
title: "Anaconda Virtual Environment"
date: 2021-07-11T08:08:50-04:00
category: Programming
tags:
  - Anaconda
  - virtual environment
---

## 가상환경 확인하기
conda info --envs  

## 가상환경 생성하기
conda create -n 가상환경이름 python=버전  

## 가상환경 활성화하기
conda activate 가상환경이름  

## 가상환경 비활성화하기
conda deactivate  

## 가상환경 라이브러리 확인하기
conda list  

## 가상환경 복사하기
conda create -n 복사된_가상환경이름 --clone 복사할_가상환경이름  

## 가상환경 삭제하기
conda remove -n 가상환경이름 --all  

## 라이브러리(패키지) 관리
pip freeze > requirements.txt  


[아나콘다 가상환경의 개념 및 활용방법](https://yganalyst.github.io/pythonic/anaconda_env_1/)
