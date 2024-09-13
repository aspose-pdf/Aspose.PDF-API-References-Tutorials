---
title: 플로팅 박스를 사용하여 헤더 푸터에 페이지 번호 추가
linktitle: 플로팅 박스를 사용하여 헤더 푸터에 페이지 번호 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 튜토리얼에서는 Aspose.PDF for .NET의 Floating Box를 사용하여 PDF 머리글과 바닥글에 페이지 번호를 쉽게 추가하는 방법을 설명합니다.
type: docs
weight: 150
url: /ko/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
## 소개

PDF 문서를 프로그래밍 방식으로 관리하는 경우 Aspose.PDF for .NET은 뛰어난 도구로 돋보입니다. .NET 애플리케이션에서 PDF 파일을 만들고, 편집하고, 조작하는 방식을 간소화합니다. 송장, 보고서 또는 모든 문서 유형을 생성하든 페이지 번호를 우아하게 추가하면 PDF의 전문성과 구성을 개선할 수 있습니다. 이 튜토리얼에서는 Floating Box를 사용하여 PDF의 머리글과 바닥글에 페이지 번호를 추가하는 방법을 알아봅니다. 시작할 준비가 되셨나요? 시작해 봅시다!

## 필수 조건

PDF 조작의 영역으로의 이 흥미로운 여정을 시작하기 전에 꼭 필요한 몇 가지가 있습니다.

### .NET 환경 설정
.NET 개발 환경이 있는지 확인하세요. .NET 애플리케이션 개발자들 사이에서 인기 있는 Visual Studio를 사용할 수 있습니다.

### Aspose.PDF 라이브러리
Aspose.PDF 라이브러리를 설치하세요. 웹사이트에서 쉽게 다운로드할 수 있습니다.

- [.NET용 Aspose.PDF 다운로드](https://releases.aspose.com/pdf/net/)

### C# 프로그래밍의 기본 지식
C#에 대한 기본적인 이해는 이 튜토리얼에서 제시되는 개념과 코딩 스니펫을 이해하는 데 도움이 됩니다.

### 문서에 대한 액세스
 항상 ~을 갖는 것이 유익합니다.[Aspose.PDF 문서](https://reference.aspose.com/pdf/net/) 추가 기능을 참고하거나 심층적으로 탐색하는 데 편리합니다.

## 패키지 가져오기

시작하려면 프로젝트에 필요한 패키지를 가져와야 합니다. 이렇게 하면 Aspose.PDF 어셈블리를 코드에서 사용할 수 있습니다. 방법은 다음과 같습니다.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이제, 플로팅 박스를 사용하여 페이지 번호를 추가하는 과정을 관리 가능한 단계로 나누어 보겠습니다. 우리가 안내하는 대로 따라하세요.

## 1단계: 문서 환경 설정

PDF 문서가 저장될 디렉토리를 지정하는 것으로 시작해 보겠습니다. 이는 출력 파일이 저장되는 위치를 결정하기 때문에 중요합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`YOUR DOCUMENT DIRECTORY` 출력 PDF 파일을 저장할 경로를 선택하세요.

## 2단계: 문서 인스턴스화

 새 PDF 문서를 만드는 것이 다음 단계입니다. 여기에는 다음을 사용하는 것이 포함됩니다.`Document` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
// 문서 인스턴스화
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```
 여기서 우리는 새로운 인스턴스를 생성합니다`Document` 클래스는 우리가 조작할 수 있는 캔버스 역할을 합니다.

## 3단계: 새 페이지 추가

이제 PDF 문서에 페이지를 추가해 봅시다. 모든 PDF에는 최소한 한 페이지가 필요하지 않나요?

```csharp
// PDF 문서에 페이지 추가
Aspose.Pdf.Page page = pdf.Pages.Add();
```
이 코드 조각은 문서에 새 페이지를 추가하여 페이지 번호가 적힌 떠 있는 상자를 비롯한 콘텐츠를 받을 수 있도록 준비합니다.

## 4단계: 떠다니는 상자 만들기

 다음으로, 페이지 번호를 보관할 플로팅 박스를 만들 시간입니다.`FloatingBox`클래스를 이용하면 페이지에 콘텐츠를 자유롭게 배치할 수 있습니다.

```csharp
// FloatingBox 클래스의 새 인스턴스를 초기화합니다.
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);
```
 여기서 매개변수는`(140, 80)` Floating Box의 너비와 높이를 지정합니다. 레이아웃 선호도에 따라 이러한 값을 조정할 수 있습니다.

## 5단계: 플로팅 박스 위치 지정

 포지셔닝이 핵심입니다! 페이지에서 페이지 번호가 어디에 나타날지 결정해야 합니다.`Left` 그리고`Top` 위치를 지정하는 속성입니다.

```csharp
// 문단의 왼쪽 위치를 나타내는 Float 값
box1.Left = 2;
// 문단의 최상위 위치를 나타내는 Float 값
box1.Top = 10;
```
이러한 값은 페이지에서 Floating Box의 위치를 결정합니다. 자유롭게 실험하여 문서에 가장 잘 어울리는지 확인하세요.

## 6단계: 페이지 번호 매크로로 텍스트 추가

이제 페이지 번호를 동적으로 표시하는 문자열을 추가합니다. 여기서 마법이 일어납니다!

```csharp
// FloatingBox의 문단 컬렉션에 매크로를 추가합니다.
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));
```
 이 경우에는,`($p/ $P)`현재 페이지 번호를 표시하는 매크로입니다.`$p`) 및 총 페이지 수(`$P`). 결과적으로 텍스트가 "페이지: 1/5"처럼 읽히도록 형식이 지정됩니다.

## 7단계: 페이지에 플로팅 상자 추가

새로 만든 페이지에 페이지 번호 텍스트와 함께 떠 있는 상자를 추가할 차례입니다.

```csharp
// 페이지에 floatingBox를 추가합니다
page.Paragraphs.Add(box1);
```
이 줄은 기본적으로 Floating Box를 페이지에 내장하여 문서 레이아웃의 일부로 만듭니다. 

## 8단계: 문서 저장

마지막으로, 작업을 저장하는 것을 잊지 마세요! 마지막 단계는 PDF 문서를 적절한 파일 이름으로 저장하는 것입니다.

```csharp
// 문서를 저장하세요
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```
지정된 경로에 원하는 파일 이름이 포함되어 있는지 확인하세요. 이제 페이지 번호가 있는 놀라운 PDF가 만들어졌습니다! 

## 결론

이제 다 됐습니다! Aspose.PDF for .NET을 사용하여 PDF의 머리글과 바닥글에 페이지 번호를 추가하는 것은 정말 간단합니다. 몇 줄의 코드만 있으면 애플리케이션에서 문서 처리를 마스터하는 여정을 시작할 수 있습니다. 다양한 레이아웃과 서식을 실험하는 것을 주저하지 마세요. 결국 창의성에는 한계가 없습니다! 전문적인 문서를 생성할 준비가 되셨나요? 코딩 모자를 쓰고 실험을 시작하세요.

## 자주 묻는 질문

### 페이지 번호 텍스트의 모양을 사용자 지정할 수 있나요?  
 예, 글꼴 크기, 색상, 스타일과 같은 텍스트 속성을 조정하여 사용자 정의할 수 있습니다.`TextFragment` 속성.

### Aspose.PDF는 무료로 사용할 수 있나요?  
 Aspose.PDF는 무료 평가판을 제공하지만 프로덕션 용도로는 유료 제품입니다.[여기서 사세요](https://purchase.aspose.com/buy).

### 더 자세한 문서는 어디에서 볼 수 있나요?  
 포괄적인 문서는 다음에서 찾을 수 있습니다.[Aspose.PDF 문서 사이트](https://reference.aspose.com/pdf/net/).

### 여러 페이지에 머리글과 바닥글을 적용하려면 어떻게 해야 하나요?  
문서의 모든 페이지를 반복하여 각 페이지에도 마찬가지로 '플로팅 상자'를 적용할 수 있습니다.

### 추가 기능에 대한 지원이 필요하면 어떻게 해야 하나요?  
추가 질문이나 지원이 필요한 경우 다음을 방문하세요.[애스포지 포럼](https://forum.aspose.com/c/pdf/10).