---
title: 문서 가져오기 창
linktitle: 문서 가져오기 창
second_title: .NET API 참조를 위한 Aspose.PDF
description: .NET용 Aspose.PDF의 GetDocumentWindow 기능을 사용하여 PDF 문서의 창 속성에 대한 정보를 검색하는 방법을 알아보세요.
type: docs
weight: 170
url: /ko/net/programming-with-document/getdocumentwindow/
---
.NET용 Aspose.PDF는 개발자가 .NET 애플리케이션에서 PDF 파일을 만들고, 편집하고, 변환할 수 있는 강력한 PDF 조작 라이브러리입니다. 이 라이브러리가 제공하는 기능 중 하나는 문서의 창 속성에 대한 정보를 검색하는 기능입니다. 이 튜토리얼은 다음을 사용하는 단계를 안내합니다.`GetDocumentWindow` .NET용 Aspose.PDF 기능을 사용하면 PDF 문서의 창 속성에 대한 정보를 검색할 수 있습니다.

## 1단계: .NET용 Aspose.PDF 설치

 .NET 애플리케이션에서 Aspose.PDF for .NET을 사용하려면 먼저 라이브러리를 설치해야 합니다. 라이브러리의 최신 버전은 다음에서 다운로드할 수 있습니다.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net).

라이브러리를 다운로드한 후 ZIP 파일의 내용을 컴퓨터의 폴더로 추출합니다. 그런 다음 .NET 프로젝트에서 Aspose.PDF for .NET DLL에 대한 참조를 추가해야 합니다.

## 2단계: PDF 문서 로드

 .NET용 Aspose.PDF를 설치하고 .NET 프로젝트의 DLL에 대한 참조를 추가하면 다음을 사용할 수 있습니다.`GetDocumentWindow`PDF 문서의 창 속성에 대한 정보를 검색하는 기능입니다.

이 기능을 사용하는 첫 번째 단계는 정보를 검색하려는 PDF 문서를 로드하는 것입니다. 이를 위해 다음 코드를 사용할 수 있습니다.

```csharp
// PDF 문서로 가는 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF 문서를 엽니다
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 위 코드에서 다음을 바꾸세요.`"YOUR DOCUMENT DIRECTORY"` PDF 문서가 있는 디렉토리 경로와 함께. 이 코드는 PDF 문서를 로드합니다.`Document` 그러면 이 객체를 사용하여 문서의 창 속성에 대한 정보를 검색할 수 있습니다.

## 3단계: 문서의 창 속성 검색

PDF 문서의 창 속성에 대한 정보를 검색하려면 다음 코드를 사용할 수 있습니다.

```csharp
// 문서의 창 속성을 검색합니다
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

위의 코드에서 각 줄은 PDF 문서의 다른 창 속성을 검색하여 콘솔에 출력합니다. 이 코드를 사용자 지정하여 관심 있는 속성만 검색할 수 있습니다.

### Aspose.PDF for .NET을 사용하여 PDF 파일의 문서 창을 가져오기 위한 예제 소스 코드 

 다음은 PDF 문서의 창 속성을 검색하기 위한 전체 소스 코드입니다.`GetDocumentWindow` .NET용 Aspose.PDF의 기능:

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// 다양한 문서 속성 가져오기
// 문서 창의 위치 - 기본값: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// 주요 읽기 순서; 페이지의 위치를 결정합니다.
// 나란히 표시될 때 - 기본값: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// 창 제목 표시줄에 문서 제목을 표시할지 여부
// false이면 제목 표시줄에 PDF 파일 이름이 표시됩니다. 기본값: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// 문서 창의 크기를 크기에 맞게 조정할지 여부
// 첫 번째로 표시되는 페이지 - 기본값: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// 뷰어 애플리케이션의 메뉴 막대를 숨길지 여부 - 기본값: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

// 뷰어 애플리케이션의 도구 모음을 숨길지 여부 - 기본값: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// 스크롤바와 같은 UI 요소를 숨길지 여부
// 그리고 페이지 내용만 표시되도록 둡니다. - 기본값: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//문서의 페이지 모드. 전체 화면 모드를 종료할 때 문서를 표시하는 방법.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// 페이지 레이아웃은 단일 페이지, 1열입니다.
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// 문서를 열었을 때 표시되어야 하는 방식
// 즉, 축소판 그림 표시, 전체 화면 표시, 첨부 파일 패널 표시
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 창 속성에 대한 정보를 검색하는 방법을 알아보았습니다. PDF 문서를 로드하고 창 속성에 액세스하면 뷰어 애플리케이션에서 열 때 문서를 표시하는 방법에 대한 정보를 수집할 수 있습니다. Aspose.PDF for .NET은 PDF 파일을 프로그래밍 방식으로 작업하기 위한 강력한 기능 세트를 제공하여 .NET 애플리케이션에서 PDF를 조작하는 데 유용한 도구가 됩니다.

### 자주 묻는 질문

#### 질문: PDF 문서의 창 속성을 검색하는 목적은 무엇입니까?

A: PDF 문서의 창 속성을 검색하면 뷰어 애플리케이션에서 열 때 PDF 문서를 어떻게 표시해야 하는지에 대한 정보를 수집할 수 있습니다. 이러한 속성은 창 위치, 표시 모드, UI 요소의 가시성과 같은 다양한 측면을 제어합니다.

#### 질문: .NET 프로젝트에 Aspose.PDF for .NET을 어떻게 설치할 수 있나요?

 A: .NET용 Aspose.PDF를 설치하려면 라이브러리를 다운로드해야 합니다.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net)다운로드 후 ZIP 파일의 내용을 추출하고 .NET 프로젝트의 .NET DLL용 Aspose.PDF에 대한 참조를 추가합니다.

#### 질문: 특정 창 속성만 검색하도록 코드를 사용자 정의할 수 있나요?

A: 네, 필요 없는 줄을 주석 처리하여 특정 창 속성을 검색하도록 코드를 사용자 지정할 수 있습니다. 코드의 각 줄은 특정 창 속성에 해당하므로 요구 사항에 따라 속성을 포함하거나 제외할 수 있습니다.

#### 질문: Aspose.PDF for .NET을 사용하여 어떤 유형의 창 속성을 검색할 수 있습니까?

답변: .NET용 Aspose.PDF를 사용하면 PDF 문서의 다양한 창 속성을 검색할 수 있습니다. 여기에는 창 가운데 정렬, 페이지 레이아웃 설정, 도구 모음 및 메뉴 막대 표시 제어 등이 포함됩니다.