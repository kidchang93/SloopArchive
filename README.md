# SloopArchive
클래스 아카이브 CMS 페이지
> - [콘텐츠 관리 (by 이창규)](#콘텐츠-관리-(by-이창규))
>>    + [콘텐츠 등록](#콘텐츠-등록)
>>    + [콘텐츠 등록 - 백엔드 코드](#콘텐츠-등록---백엔드-코드)
>>    + [등록 후 미승인 콘텐츠 탭으로 이동](#등록-후-미승인-콘텐츠-탭으로-이동)
>    + [승인 버튼 기능 - 누르면 해당 콘텐츠 권한 변경](#승인-버튼-기능---누르면-해당-콘텐츠-권한-변경)
>>    + [승인 버튼 기능 - 백엔드 코드](#승인-버튼-기능---백엔드-코드)
>>    + [승인 버튼 기능 - 프론트 코드](#승인-버튼-기능---프론트-코드)
>>    + [승인된 콘텐츠는 미승인 콘텐츠 -> 전체 콘텐츠](#승인된-콘텐츠는-미승인-콘텐츠-->-전체-콘텐츠)
>>    + [전체 콘텐츠에서 확인](#전체-콘텐츠에서-확인)
>>    + [승인된 콘텐츠만 사용자 화면 출력](#승인된-콘텐츠만-사용자-화면-출력)
>>    + [미승인 콘텐츠는 사용자 화면 출력 X](#미승인-콘텐츠는-사용자-화면-출력-x)
>>    + [미승인 콘텐츠 승인](#미승인-콘텐츠-승인)
>>    + [사용자 화면 출력](#사용자-화면-출력)
>    + [콘텐츠 수정](#콘텐츠-수정)
>>    + [수정시 미리보기 & 새로운 파일 추가시 미리보기](#수정시-미리보기-&-새로운-파일-추가시-미리보기)
>    + [S3 config](#s3-config)
>>    + [Generate PresignedURL 메서드](#generate-presignedurl-메서드)
>>    + [업로드시 byte로 변환 하는 메서드](#업로드시-byte로-변환-하는-메서드)
>>    + [공용 클래스 fileUtils 필드 주입](#공용-클래스-fileUtils-필드-주입)
>>    + [S3 업로드 - 백엔드 코드](#S3-업로드---백엔드-코드)
>>    + [파일 저장 메서드](#파일-저장-메서드)
>    + [다운로드 기능](#다운로드-기능)
>>    + [다운로드 기능 - 백엔드 코드 1](#다운로드-기능---백엔드-코드-1)
>>    + [다운로드 기능 - 백엔드 코드 2](#다운로드-기능---백엔드-코드-2)
>    + [리스트 출력시 for문을 돌면서 presignedURL 받아오기](#리스트-출력시-for문을-돌면서-presignedURL-받아오기)
>>    + [전체 콘텐츠 & 미승인 콘텐츠 리스트 출력시 서로 다른 SQL문 사용](#전체-콘텐츠-&-미승인-콘텐츠-리스트-출력시-서로-다른-SQL문-사용)
>>    + [리스트 출력 프론트 코드](#리스트-출력-프론트-코드)
>    + [상세보기 팝업창](#상세보기-팝업창)
>>    + [상세보기 팝업창 - 프론트 코드](#상세보기-팝업창---프론트-코드)
>    + [논리 삭제 메서드](#논리-삭제-메서드)

# 콘텐츠 관리 (by 이창규)
### 콘텐츠 등록
![create](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/00d19ce4-1201-4f13-b4cd-e4d734efde72)
### 콘텐츠 등록 - 백엔드 코드
![saved_content](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/5020b479-f810-45f9-88c4-ccbbbab35e08)
### 등록 후 미승인 콘텐츠 탭으로 이동
![등록후미승인콘텐츠](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/8bcad0c0-9444-44de-91a9-8491693fae79)
### 승인 버튼 기능 - 누르면 해당 콘텐츠 권한 변경
![승인으로권한변경](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/5ad74ad1-8465-4abd-bfcc-82242267e602)
### 승인 버튼 기능 - 백엔드 코드
![승인버튼](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/72eff462-d0ae-4a23-b5fc-f8bb8493c1ad)
### 승인 버튼 기능 - 프론트 코드
![승인버튼2](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/07b5fe0f-8b69-4416-bb84-d4e1f2afeaae)
### 승인된 콘텐츠는 미승인 콘텐츠 -> 전체 콘텐츠
![승인후미승인콘텐츠에서 사라짐](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/58dc2ecd-01b8-43fb-bd31-0970f4965ca7)
### 전체 콘텐츠에서 확인
![승인후전체콘텐츠에서 확인가능](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/cc83b143-6672-4dd3-b821-4a677a98a499)
### 승인된 콘텐츠만 사용자 화면 출력 
### 미승인 콘텐츠는 사용자 화면 출력 X
![승인콘텐츠만사용자화면출력](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/5b29bb8d-07a7-4970-b97e-55ba2bcf0373)
### 미승인 콘텐츠 승인
![미승인콘텐츠승인](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/f9af5e12-16ca-4b3d-8636-68e6059ae238)
### 사용자 화면 출력
![사용자화면2](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/694e8944-9b26-4046-ada0-1c908b0f54e8)
### 콘텐츠 수정
![update](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/a06488ed-8219-4413-ba4b-2e6e897629be)
### 수정시 미리보기 & 새로운 파일 추가시 미리보기
![update2](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/87648821-c2ec-4dde-ad25-1c3b5fa23dd6)

### S3 config
![s3config](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/438d6d7e-f330-4be2-bc15-db90607089f6)
### Generate PresignedURL 메서드
![generatePresignedURL](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/1e796c80-d1e8-413e-bc27-9f7151bee332)
### 업로드시 byte로 변환 하는 메서드
![byte코드변환](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/b6d27084-6a35-4bff-b806-9d270cd00c8c)
### 공용 클래스 fileUtils 필드 주입
![fileutils 필드주입](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/4e397901-1a27-4223-a4d6-61efc9eb54e3)
### S3 업로드 - 백엔드 코드
![s3Upload](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/a5b96a70-f461-470e-8d20-9e3f3bcf29c4)
### 파일 저장 메서드
![savefiles](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/27f2f9f5-02d8-482e-9b8f-f01a7aa2d977)

### 다운로드 기능
![다운로드 클릭시](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/81790260-e23d-4acd-b477-0272cf80a3bf)
### 다운로드 기능 - 백엔드 코드 1
![download](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/0e1bb041-38ef-4f0d-87c1-7172ba036774)
### 다운로드 기능 - 백엔드 코드 2
![download2](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/be703af7-6e70-4cb2-92ac-5292c5f92ec9)

### 리스트 출력시 for문을 돌면서 presignedURL 받아오기
![list-arc_for문](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/b745217f-d27f-49ae-9848-b2f83ad9c509)
### 전체 콘텐츠 & 미승인 콘텐츠 리스트 출력시 서로 다른 SQL문 사용
![list나눈SQL쿼리문](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/f4a85595-4236-4e53-95bc-f701767e00f1)
### 리스트 출력 프론트 코드
![리스트front](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/4579a8cd-cd52-41f5-b0ac-66a191f333a9)

### 상세보기 팝업창
![리스트팝업창2](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/764af1aa-963e-430d-87b7-a668b38f9b30)
### 상세보기 팝업창 - 프론트 코드
![리스트팝업창](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/d016f8e1-2e5b-4333-8a1b-9946e2fa0f02)
### 논리 삭제 메서드
![delete](https://github.com/kidchang93/Archive-SpringBoot/assets/145524731/98a3aea8-580b-46dd-a3b3-0cd0cbc8c1fb)

