# 웹 포트폴리오 인수인계 문서

최종 정리일: 2026-09-08  
작업 경로: `C:\Users\user\Desktop\webPortfolio`  
Git 원격 저장소: `https://github.com/LKH1134/webPortfolio.git`  
현재 브랜치: `main`  
문서 대상: 후속 작업자 및 코딩 에이전트

## 1. 프로젝트 개요

이 프로젝트는 게임 기획자 이기현의 정적 웹 포트폴리오다. 별도 빌드 과정 없이 HTML 파일을 직접 열어 확인할 수 있으며, Pretendard 로컬 웹폰트를 사용한다.

주요 페이지는 다음과 같다.

- `index.html`: 메인 포트폴리오
- `resume.html`: 이력서
- `cover-letter.html`: 자기소개서
- `images/`: 프로젝트 이미지, 아이콘, 증명사진
- `fonts/`: Pretendard 웹폰트

`_next`, `index.rsc`, `vinext-client-entry-manifest.json` 등은 초기 웹 내보내기 과정에서 생성된 레거시 파일이다. 현재 편집 대상은 위의 HTML 3개와 `images`, `fonts`이며, 레거시 파일을 다시 소스로 사용하지 않는다.

## 2. 실행 및 확인 방법

빌드 명령은 필요 없다. 다음 파일을 Chrome 또는 Safari에서 직접 연다.

`C:\Users\user\Desktop\webPortfolio\index.html`

페이지 상단의 `메인 페이지`, `이력서`, `자기소개서` 링크로 세 HTML을 이동할 수 있다. 모든 링크와 이미지 경로는 로컬 상대 경로를 사용하므로 다른 기기로 옮길 때는 프로젝트 폴더 전체를 복사해야 한다.

수정 후 최소 확인 항목:

1. 데스크톱과 모바일 폭에서 세 페이지 열기
2. 메인 첫 섹션 이미지 전환 및 선택 바 확인
3. 프로젝트 카드 인디케이터 클릭과 카드 내부 마우스 휠 전환 확인
4. 외부 문서 링크가 새 탭에서 열리는지 확인
5. 이력서 증명사진과 인적사항 표 하단 정렬 확인
6. Chrome과 iOS Safari에서 레이아웃 및 터치 스크롤 확인

## 3. 현재 디자인 시스템

- 기본 강조색: `#5F90F0`
- 첫 섹션의 밝은 배경색: `#BDF8FC`
- 첫 섹션의 짙은 텍스트색: `#17233F`
- 밝은 파란 보조 배경: `#EEF3FF`
- 기본 본문색: `#08090a`
- 폰트: `fonts/Pretendard-Regular.woff2`, `Pretendard-Medium.woff2`, `Pretendard-SemiBold.woff2`

기존 녹색 계열 HEX/RGBA는 파란 계열로 교체했다. 새로운 요소를 추가할 때도 위 팔레트를 우선 사용한다.

## 4. 메인 페이지 현황

### 첫 섹션

- 문구: `꾸준하고 성실한 기획자 이기현입니다.`
- `꾸준`, `성실`은 `<em>`으로 감싸져 있으며 `#5F90F0`으로 강조된다.
- 프로젝트 01과 프로젝트 02 이미지를 선택 바로 전환할 수 있다.
- 자동 이미지 전환 간격은 현재 JavaScript에서 `10000`ms로 설정되어 있다.
- 과거 요구사항은 4초였으나 현재 코드에는 10초가 적용되어 있으므로, 변경 전 사용자 의도를 다시 확인한다.

### 프로젝트 경험

- 화면에는 한 번에 프로젝트 카드 1개만 표시된다.
- 우측 세로 인디케이터를 누르면 PROJECT 01~03이 전환된다.
- 프로젝트 카드 위에서 휠을 아래로 굴리면 다음 프로젝트, 위로 굴리면 이전 프로젝트로 전환된다.
- 카드 영역에서는 페이지 전체 스크롤이 차단된다. 첫 카드나 마지막 카드에서도 휠 기본 동작이 차단되므로 페이지를 계속 이동하려면 포인터를 카드 밖으로 옮겨야 한다.
- 전환 잠금 간격은 `420`ms다.

프로젝트 내용:

- PROJECT 01 `하이넘`
  - 이미지: `images/highnum.png`
  - 아이콘: `images/highnum-icon.png`
  - 5인 Unity 로그라이크 프로젝트
  - 2026.07~2026.08, 6주
  - 시스템 기획 및 프로그래밍
  - itch.io 출시, 이벤트 및 보상 시스템 기획서, 데이터 테이블 구조도 링크 포함
- PROJECT 02 `마인스톡`
  - 이미지: `images/minestock.png`
  - 아이콘: `images/minestock-icon.png`
  - 메인 페이지에는 `3인 프로젝트`로 표기됨
  - 2026.06~2026.07, 3주
  - 이미지 및 사운드 리소스 담당
  - 리소스 명세서와 Google Drive 리소스 모음 폴더 링크 포함
- PROJECT 03
  - 아직 예시 콘텐츠 상태이며 추후 추가 예정

### 보유 기술 및 게임 경험

- 보유 기술과 게임 경험은 초기 예시 콘텐츠가 남아 있다.
- 사용자 제공 실제 내용으로 교체하기 전 임의로 확정하지 않는다.

### Contact

- 이메일: `rlgus845@gmail.com`이며 하이퍼링크가 아닌 일반 텍스트다.
- 전화번호: `010 - 3762 - 6979`
- 아이콘: `images/gmail-icon.png`, `images/phone-icon.png`
- 이메일과 전화번호에는 밑줄 및 굵은 글꼴이 적용되지 않는다.

## 5. 이력서 현황

`resume.html`에는 다음 내용이 입력되어 있다.

- 인적사항 및 증명사진
- 프로젝트 경험: Beat Time, 마인스톡, 하이넘
- 보유 기술: Unity, AI 활용
- 교육 이력
- GS25 업무 이력
- 게임 경험: 테라리아, 사운드 볼텍스
- 희망 연봉: 입사 후 결정
- 출근 가능일: `xxxx.xx.xx` 임시값

증명사진은 `images/id-photo.webp`를 사용하며 테두리는 없다. 데스크톱에서 사진과 오른쪽 인적사항 표의 하단이 맞도록 CSS가 설정되어 있다.

주의: 이력서에는 마인스톡이 `5인 프로젝트`로, 메인 페이지에는 `3인 프로젝트`로 표기되어 있다. 어떤 값이 맞는지 사용자 확인 후 두 페이지를 통일해야 한다.

## 6. 자기소개서 현황

`cover-letter.html`은 페이지와 레이아웃만 구성되어 있다. 다음 세 항목은 아직 임시 문구다.

- 소개
- 강점과 일하는 방식
- 지원 동기와 목표

사용자가 실제 자기소개서 내용을 제공하기 전에는 임의로 작성하지 않는다.

## 7. 외부 링크

- 하이넘 itch.io: `https://panasaga.itch.io/highnum`
- 이벤트 및 보상 시스템 기획서: `https://drive.google.com/file/d/1bH8mo7WPFVuDRl3oOy-CSsLxg3vRgLzZ/view?usp=drive_link`
- 데이터 테이블 구조도: `https://drive.google.com/file/d/1QoIE6mO0nk5Xbg2mynd-JQXiUhP5mNI3/view?usp=drive_link`
- 마인스톡 리소스 명세서: `https://docs.google.com/spreadsheets/d/14z6vJ1G5oFnON3kpvcNvYBlzzcKoESQh-5h1Ldtansw/edit?usp=drive_link`
- 마인스톡 리소스 모음: `https://drive.google.com/drive/folders/1u8IeS9hOO1J9t3b3Bjmz3twvjLvbykMA?usp=drive_link`

외부 링크는 `target="_blank"`와 `rel="noopener noreferrer"`를 유지한다.

## 8. 코드 유지보수 주의사항

- HTML 3개는 대부분 CSS와 JavaScript가 파일 내부에 포함된 단일 파일 구조다.
- CSS가 압축된 긴 한 줄과 후반 override 선언으로 누적되어 있다. 같은 선택자가 여러 번 등장하며 뒤쪽 선언이 최종 적용된다.
- `resume.html`과 `cover-letter.html`에는 문서 최상단, `<html>`보다 앞에 추가 override `<style>`이 있다. 브라우저에서는 동작하지만 표준 HTML 구조는 아니므로 다음 정리 작업에서 모든 스타일을 `<head>` 내부로 통합하는 것이 좋다.
- CSS 정리를 수행할 때 시각적 결과가 달라지지 않도록 최종 override 우선순위를 보존한다.
- 이미지 파일 이름과 상대 경로를 바꾸면 세 HTML의 참조도 함께 수정한다.
- 사용자 개인정보가 포함되어 있으므로 공개 배포 및 저장소 공개 범위를 확인한다.
- 사용자가 작업 중 직접 HTML을 편집할 수 있다. 수정 전 항상 최신 파일 내용을 다시 읽고 사용자 변경을 덮어쓰지 않는다.

## 9. Git 상태 및 전달 방법

문서 작성 직전 기준:

- 수정됨: `index.html`, `resume.html`, `cover-letter.html`
- 새 파일: `images/gmail-icon.png`, `images/id-photo.webp`, `images/phone-icon.png`
- 마지막 확인 커밋: `80e0095 [MOD] 260908 두번째 섹션 수정`
- 현재 변경 사항은 아직 커밋되지 않았다.

다른 기기로 인계하는 방법:

1. 현재 변경 사항과 새 이미지, 이 문서를 커밋한다.
2. `origin/main`으로 푸시한다.
3. 새 기기에서 저장소를 clone 또는 pull한다.
4. `index.html`을 직접 열어 위의 확인 목록을 수행한다.

커밋과 푸시는 사용자 요청 또는 승인을 받은 뒤 수행한다.

## 10. 후속 작업 우선순위

1. 메인/이력서의 마인스톡 인원 수 불일치 확인
2. 첫 섹션 자동 전환 시간 10초와 과거 4초 요구사항 중 최종값 확인
3. PROJECT 03 실제 콘텐츠 입력
4. 메인 보유 기술 및 게임 경험 실제 콘텐츠 입력
5. 자기소개서 임시 문구 교체
6. 출근 가능일의 `xxxx.xx.xx` 교체
7. 중복 CSS를 정리하고 HTML 유효성 검사
8. 모바일 Safari에서 최종 시각 검수

