---
layout: single
title:  "Git 명령어 정리"
date:   2020-04-02 16:19:40 +0900
categories: jekyll update
---
<h2>git 소개</h2>



<p>
<b> git? : 소스 관리를 위한 분산버전 시스템</b> <br>
    코드 버전을 관리할 수 있음
<li>git flow를 숙지하는 것을 추천</li>
    <img src = "https://miro.medium.com/max/1222/1*AZa45AoRHDQJsMKdAkTlLA.png">
</p>





<h3>명령어 요약</h3>

--------------

><li>git init : git 저장소 생성</li>
>
><li>git clone git_path : 코드가져오기</li>
>
><li>git checkout branch_name : 브랜치 선택하기</li>
>
><li>git checkout -t remote_path/branch_name : 원격 브랜치 선택하기</li>
>
><li>git branch branch_name : 브랜치 생성하기</li>
>
><li>git branch -r : 원격 브랜치 목록보기</li>
>
><li>git branch -a : 로컬 브랜치 목록보기</li>
>
><li>git branch -m branch_name change_branch_name : 브랜치 이름 바꾸기</li>
>
><li>git branch -d branch_name : 브랜치 삭제하기</li>
>
><li>git push remote_name — delete branch_name : 원격 브랜치 삭제하기 ( git push origin — delete gh-pages )</li>
>
><li>git add file_path : 수정한 코드 선택하기 ( git add * )</li>
>
><li>git commit -m “commit_description” : 선택한 코드 설명 적기 ( git commit -m “내용”)</li>
>
><li>git push romote_name branch_name : add하고 commit한 코드 git server에 보내기 (git push origin master)</li>
>
><li>git pull : git서버에서 최신 코드 받아와 merge 하기</li>
>
><li>git fetch : git서버에서 최신 코드 받아오기</li>
>
><li>git reset — hard HEAD^ : commit한 이전 코드 취소하기</li>
>
><li>git reset — soft HEAD^ : 코드는 살리고 commit만 취소하기</li>
>
><li>git reset — merge : merge 취소하기</li>
>
><li>git reset — hard HEAD && git pull : git 코드 강제로 모두 받아오기</li>
>
><li>git branch — set-upstream-to=remote_path/branch_name : git pull no tracking info 에러해결</li>