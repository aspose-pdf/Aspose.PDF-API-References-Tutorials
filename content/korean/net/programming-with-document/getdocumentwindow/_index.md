---
title: 문서 가져오기 창
linktitle: 문서 가져오기 창
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF의 GetDocumentWindow 기능을 사용하여 PDF 문서의 창 속성에 대한 정보를 검색하는 방법을 알아보세요.
type: docs
weight: 170
url: /ko/net/programming-with-document/getdocumentwindow/
---
 .NET용 Aspose.PDF는 개발자가 .NET 애플리케이션에서 PDF 파일을 생성, 편집 및 변환할 수 있는 강력한 PDF 조작 라이브러리입니다. 이 라이브러리가 제공하는 기능 중 하나는 문서의 창 속성에 대한 정보를 검색하는 기능입니다. 이 튜토리얼에서는 다음을 사용하는 단계를 안내합니다.`GetDocumentWindow` PDF 문서의 창 속성에 대한 정보를 검색하는 .NET용 Aspose.PDF의 기능입니다.

## 1단계: .NET용 Aspose.PDF 설치

 .NET 애플리케이션에서 .NET용 Aspose.PDF를 사용하려면 먼저 라이브러리를 설치해야 합니다. 다음에서 최신 버전의 라이브러리를 다운로드할 수 있습니다.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net).

라이브러리를 다운로드한 후 ZIP 파일의 내용을 컴퓨터의 폴더에 추출합니다. 그런 다음 .NET 프로젝트에 Aspose.PDF for .NET DLL에 대한 참조를 추가해야 합니다.

## 2단계: PDF 문서 로드

.NET용 Aspose.PDF를 설치하고 .NET 프로젝트에 DLL에 대한 참조를 추가한 후에는 다음을 사용할 수 있습니다.`GetDocumentWindow` PDF 문서의 창 속성에 대한 정보를 검색하는 기능입니다.

이 기능을 사용하는 첫 번째 단계는 정보를 검색하려는 PDF 문서를 로드하는 것입니다. 이렇게 하려면 다음 코드를 사용할 수 있습니다.

```csharp
// PDF 문서의 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF 문서 열기
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

 위 코드에서`"YOUR DOCUMENT DIRECTORY"` PDF 문서가 있는 디렉토리의 경로를 사용하세요. 이 코드는 PDF 문서를`Document` 그런 다음 문서의 창 속성에 대한 정보를 검색하는 데 사용할 수 있습니다.

## 3단계: 문서의 창 속성 검색

PDF 문서의 창 속성에 대한 정보를 검색하려면 다음 코드를 사용할 수 있습니다.

```csharp
// 문서의 창 속성을 검색합니다.
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

위 코드에서 각 줄은 PDF 문서의 서로 다른 창 속성을 검색하여 콘솔에 출력합니다. 관심 있는 속성만 검색하도록 이 코드를 사용자 정의할 수 있습니다.

### .NET용 Aspose.PDF를 사용하여 PDF 파일의 문서 가져오기 창에 대한 예제 소스 코드 

 다음은 PDF 문서의 창 속성을 검색하는 전체 소스 코드입니다.`GetDocumentWindow` .NET용 Aspose.PDF의 기능:

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

// 다양한 문서 속성 가져오기
// 문서 창 위치 - 기본값: false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

// 주요 읽기 순서; 페이지의 위치를 결정합니다
// 나란히 표시되는 경우 - 기본값: L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

// 창의 제목 표시줄에 문서 제목을 표시할지 여부
// false인 경우 제목 표시줄에 PDF 파일 이름이 표시됩니다. 기본값: false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

// 문서의 창 크기를 문서 크기에 맞게 조정할지 여부
// 처음 표시되는 페이지 - 기본값: false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

// 뷰어 애플리케이션의 메뉴바를 숨길지 여부 - 기본값: false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//뷰어 애플리케이션의 툴바 숨기기 여부 - 기본값: false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

// 스크롤 막대와 같은 UI 요소를 숨길지 여부
// 페이지 내용만 표시되도록 둡니다. - 기본값: false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

// 문서의 페이지 모드. 전체 화면 모드 종료 시 문서를 표시하는 방법.
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

// 페이지 레이아웃(즉, 단일 페이지, 하나의 열)
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

// 문서를 열 때 표시되는 방법
// 예: 썸네일 표시, 전체 화면, 첨부 파일 표시
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 창 속성에 대한 정보를 검색하는 방법을 배웠습니다. PDF 문서를 로드하고 해당 창 속성에 액세스하면 뷰어 응용 프로그램에서 문서를 열 때 문서가 표시되는 방법에 대한 정보를 수집할 수 있습니다. .NET용 Aspose.PDF는 프로그래밍 방식으로 PDF 파일을 작업할 수 있는 강력한 기능 세트를 제공하므로 .NET 응용 프로그램에서 PDF를 조작하는 데 유용한 도구입니다.

### FAQ

#### Q: PDF 문서의 창 속성을 검색하는 목적은 무엇입니까?

답변: PDF 문서의 창 속성을 검색하면 뷰어 응용 프로그램에서 PDF 문서를 열 때 PDF 문서가 표시되는 방법에 대한 정보를 수집할 수 있습니다. 이러한 속성은 창 위치, 표시 모드, UI 요소의 가시성과 같은 다양한 측면을 제어합니다.

#### Q: 내 .NET 프로젝트에 .NET용 Aspose.PDF를 어떻게 설치할 수 있나요?

 A: .NET용 Aspose.PDF를 설치하려면 다음에서 라이브러리를 다운로드해야 합니다.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net). 다운로드한 후 ZIP 파일의 내용을 추출하고 .NET 프로젝트에 Aspose.PDF for .NET DLL에 대한 참조를 추가하세요.

#### Q: 특정 창 속성만 검색하도록 코드를 사용자 정의할 수 있습니까?

A: 예, 필요하지 않은 줄을 주석 처리하여 특정 창 속성을 검색하도록 코드를 사용자 정의할 수 있습니다. 코드의 각 줄은 특정 창 속성에 해당하므로 요구 사항에 따라 속성을 포함하거나 제외할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 어떤 유형의 창 속성을 검색할 수 있습니까?

A: .NET용 Aspose.PDF를 사용하면 창 중앙 정렬, 페이지 레이아웃 설정, 도구 모음 및 메뉴 표시줄 표시 제어 등을 포함하여 PDF 문서의 다양한 창 속성을 검색할 수 있습니다.