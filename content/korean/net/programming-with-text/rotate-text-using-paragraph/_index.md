---
title: PDF 파일에서 문단을 사용하여 텍스트 회전
linktitle: PDF 파일에서 문단을 사용하여 텍스트 회전
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에서 텍스트를 회전하는 방법을 알아보세요. 이 단계별 가이드를 따라 문서를 만드세요.
type: docs
weight: 380
url: /ko/net/programming-with-text/rotate-text-using-paragraph/
---
## 소개

동적 텍스트로 PDF를 만드는 것은 정보를 전달하는 매력적인 방법이 될 수 있습니다. 문서에 약간의 감각을 더하고 싶다면, 텍스트를 회전하면 핵심 요점을 강조하거나 시각적으로 매력적인 디자인을 제공하는 데 도움이 될 수 있습니다. 이 가이드에서는 Aspose.PDF for .NET을 사용하여 텍스트를 회전하는 방법을 안내하여 PDF 문서를 더욱 상호 작용적이고 흥미롭게 만들어 보겠습니다!

## 필수 조건

PDF 파일에서 텍스트 회전의 흥미로운 세계로 뛰어들기 전에 모든 것이 올바르게 설정되었는지 확인해 보겠습니다. 필요한 전제 조건은 다음과 같습니다.

1.  .NET용 Aspose.PDF: 프로젝트에 .NET용 Aspose.PDF가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/pdf/net/).
2. Visual Studio: 이 튜토리얼에서는 .NET 개발을 위해 Visual Studio를 사용한다고 가정합니다.
3. C#에 대한 기본 지식: C# 프로그래밍에 대한 지식은 예제를 더 잘 이해하는 데 도움이 될 것입니다. 처음이라면 걱정하지 마세요. 단계별로 진행하겠습니다!
4. .NET Framework: 프로젝트가 적절한 버전의 .NET Framework로 설정되었는지 확인하세요. Aspose.PDF는 다양한 버전을 지원하므로 설명서에서 호환성을 확인하세요.

이러한 전제 조건을 갖추면 이제 코드 작성을 시작할 준비가 되었습니다!

## 패키지 가져오기

Aspose.PDF를 효과적으로 사용하려면 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

### 프로젝트 열기

Visual Studio를 실행하고 PDF에서 텍스트 회전을 구현하려는 프로젝트를 엽니다.

### 참조 추가

솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택합니다. 

### Aspose.PDF 검색 및 설치

NuGet 패키지 관리자에서 "Aspose.PDF"를 검색하여 설치합니다. 이 작업을 통해 Aspose.PDF 라이브러리에서 사용 가능한 모든 클래스와 함수에 액세스할 수 있습니다.

### 네임스페이스 가져오기

C# 파일의 맨 위에서 Aspose.PDF 네임스페이스를 가져와야 합니다.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

이제 코딩을 시작할 준비가 되었습니다!

좋습니다! 이제 본론으로 들어가겠습니다. PDF에서 텍스트를 회전하는 것입니다. 코드를 단계별로 살펴보겠습니다.

## 1단계: 문서 초기화

첫 번째 단계는 PDF 문서의 새 인스턴스를 만드는 것입니다. 여기에 모든 노고가 보관됩니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // 문서 디렉토리를 지정하세요
Document pdfDocument = new Document(); // 문서 객체 초기화
```
여기서는 문서에 대한 디렉토리를 지정하고 새 Document 객체를 초기화합니다. 이 객체는 PDF의 컨테이너 역할을 합니다.

## 2단계: 특정 페이지 가져오기

이제 텍스트를 회전할 페이지를 추가해 보겠습니다.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add(); // 특정 페이지 가져오기
```
이 줄은 PDF에 새 페이지를 추가하고 여기에 콘텐츠를 추가할 수 있게 해줍니다.

## 3단계: 텍스트 문단 만들기

다음으로, 텍스트 조각을 추가할 문단을 만들어 보겠습니다.

```csharp
TextParagraph paragraph = new TextParagraph();
paragraph.Position = new Position(200, 600); // 문단의 위치를 설정하세요
```
여기서 TextParagraph를 초기화하고 페이지에서 위치를 설정합니다. 좌표(200, 600)는 페이지에서 문단이 시작되는 위치를 결정합니다.

## 4단계: 텍스트 조각 만들기 

이제 재밌는 부분, 텍스트 조각을 만드는 단계입니다! 세 개의 텍스트 조각을 만들 것입니다. 그 중 두 개는 회전됩니다.

### 4.1: 회전된 텍스트 조각 만들기

```csharp
TextFragment textFragment1 = new TextFragment("rotated text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.Rotation = 45; // 회전 설정
```
여기서, "회전된 텍스트"라고 하는 첫 번째 텍스트 조각을 만듭니다. 글꼴 크기, 글꼴 유형을 설정한 다음 45도 회전을 적용합니다.

### 4.2: 주요 텍스트 조각 만들기

다음으로, 본문 부분을 추가해 보겠습니다.

```csharp
TextFragment textFragment2 = new TextFragment("main text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```
이 부분은 회전되지 않고 문단의 주요 텍스트로 사용됩니다.

### 4.3: 다른 회전된 텍스트 조각 만들기

마지막으로, 회전된 텍스트 조각을 하나 더 만들어 보겠습니다.

```csharp
TextFragment textFragment3 = new TextFragment("another rotated text");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = -45; // 회전 설정
```
첫 번째와 마찬가지로 이 조각은 -45도 회전하여 흥미로운 시각적 대비를 더했습니다.

## 5단계: 문단에 텍스트 조각 추가

이제 앞서 만든 문단에 모든 텍스트 조각을 추가할 차례입니다.

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```
 우리는 단순히 각 텍스트 조각을 우리의 문단에 추가하고 있습니다.`AppendLine` 이 방법은 각 텍스트 조각이 수직으로 쌓이도록 보장합니다.

## 6단계: TextBuilder 객체 생성

다음으로, TextBuilder를 사용하여 PDF 페이지에 문단을 추가합니다.

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph); // PDF 페이지에 텍스트 문단 추가
```
TextBuilder 객체는 지정된 PDF 페이지에 문단을 적용하는 도구 역할을 합니다.

## 7단계: 문서 저장

힘겨운 작업을 마친 후에는 문서를 저장하고 무엇이 만들어졌는지 확인해 보세요!

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated2_out.pdf");
```
이 줄은 "TextFragmentTests_Rotated2_out.pdf"라는 이름으로 지정한 디렉토리에 문서를 저장합니다. 

그리고 보일라! 이제 회전된 텍스트가 있는 PDF 파일이 생겼습니다!

## 결론

PDF에서 텍스트를 회전하면 문서에 많은 창의성과 강조점을 더할 수 있습니다. Aspose.PDF for .NET을 사용하면 디자인 요구 사항에 맞게 구현하고 사용자 정의하는 것이 간단합니다. 이 단계별 가이드를 따르면 PDF 내에서 회전된 텍스트를 만드는 방법을 알게 되어 매력적인 방식으로 정보를 표현할 수 있는 새로운 가능성을 제공합니다. 

## 자주 묻는 질문

### .NET용 Aspose.PDF란 무엇인가요?
.NET용 Aspose.PDF는 개발자가 .NET 애플리케이션 내에서 직접 PDF 문서를 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다.

### 내 프로젝트에 Aspose.PDF를 어떻게 설치합니까?
 Visual Studio의 NuGet 패키지 관리자를 통해 Aspose.PDF를 설치하거나 다음에서 다운로드하여 설치할 수 있습니다.[Aspose 다운로드 페이지](https://releases.aspose.com/pdf/net/).

### Aspose.PDF를 무료로 사용할 수 있나요?
 네, Aspose.PDF는 무료 체험판을 제공합니다. 다음부터 시작할 수 있습니다.[무료 체험](https://releases.aspose.com/) 그 기능을 살펴보세요.

### Aspose.PDF에 대한 지원이 있나요?
 물론입니다! 연락할 수 있습니다.[Aspose 지원](https://forum.aspose.com/c/pdf/10) 문제가 발생하면 도움을 받으세요.

### Aspose.PDF에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 임시 라이센스를 구매할 수 있습니다[Aspose의 웹사이트](https://purchase.aspose.com/temporary-license/) 라이브러리의 모든 기능을 사용해 보세요.