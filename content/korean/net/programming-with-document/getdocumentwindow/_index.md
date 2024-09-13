---
title: 문서 가져오기 창
linktitle: 문서 가져오기 창
second_title: .NET API 참조를 위한 Aspose.PDF
description: .NET용 Aspose.PDF의 GetDocumentWindow 기능을 사용하여 PDF 문서의 창 속성에 대한 정보를 검색하는 방법을 알아보세요.
type: docs
weight: 170
url: /ko/net/programming-with-document/getdocumentwindow/
---
# 소개

PDF로 작업하고 있으며 PDF를 열 때 표시되는 방식을 더 많이 제어하고 싶으신가요? 메뉴 막대를 숨기거나 첫 페이지에 맞게 창 크기를 조정하든 Aspose.PDF for .NET은 뷰어에서 열 때 PDF가 작동하는 방식을 사용자 지정하는 데 필요한 모든 도구를 제공합니다. 이 튜토리얼에서는 Aspose.PDF for .NET에서 문서 창 설정을 검색하고 조작하는 방법을 알아보겠습니다.


# 필수 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 개발 환경에 .NET용 Aspose.PDF가 설치되어 있습니다.
  - [.NET용 Aspose.PDF 다운로드](https://releases.aspose.com/pdf/net/)
-  Aspose.PDF에 대한 유효한 라이센스 또는 다음을 얻을 수 있습니다.[무료 체험](https://releases.aspose.com/) 또는[임시 면허](https://purchase.aspose.com/temporary-license/).
- .NET과 C#에 대한 기본적인 이해.
- Visual Studio나 다른 적합한 IDE.

# 패키지 가져오기

코드를 작성하기 전에 필요한 패키지를 가져와야 합니다. 프로젝트를 열고 C# 파일의 맨 위에 다음 네임스페이스를 추가합니다.

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

이렇게 하면 Aspose.PDF for .NET을 사용하여 PDF 문서를 조작하는 데 필요한 모든 클래스와 메서드에 액세스할 수 있습니다.

 이제 다양한 문서 창 설정을 검색하는 프로세스를 분석해 보겠습니다. 이 예에서는 샘플 PDF 파일을 사용합니다.`GetDocumentWindow.pdf`.

## 1단계: 문서 디렉토리 경로 설정

우선, PDF 파일의 경로를 정의해야 합니다. 실행 중에 오류가 발생하지 않도록 올바른 파일 경로를 갖는 것이 중요합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 여기서 교체하세요`"YOUR DOCUMENT DIRECTORY"` PDF 파일이 있는 실제 디렉토리와 함께. 이것은 PDF 문서를 로드할 작업 디렉토리입니다.

## 2단계: PDF 문서 열기

이제 파일 경로가 설정되었으므로 다음 단계는 Aspose.PDF를 사용하여 PDF 문서를 여는 것입니다. 이렇게 하면 문서가 메모리에 로드되어 속성을 검색할 수 있습니다.

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

이 간단한 코드 줄을 사용하면 PDF 파일을 성공적으로 로드할 수 있습니다.`pdfDocument` 이제 모든 속성에 접근할 수 있는 객체가 생겼습니다.

## 3단계: 창 중앙 정렬 상태 검색

 다음으로, 문서 창을 열 때 가운데에 배치해야 하는지 확인해 보겠습니다. 이에 대한 기본값은 다음과 같습니다.`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

 출력이`true`, 문서의 창이 화면 중앙에 열립니다. 그렇지 않으면 기본 위치에서 열립니다.

## 4단계: 텍스트 방향 확인

PDF의 모양에서 또 다른 중요한 측면은 텍스트 방향인데, 이는 텍스트를 왼쪽에서 오른쪽(L2R)으로 읽을지 오른쪽에서 왼쪽(R2L)으로 읽을지 결정합니다. 다음 코드를 사용하여 이 정보를 검색할 수 있습니다.

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

 출력은 다음과 같습니다`L2R` 왼쪽에서 오른쪽으로 텍스트를 쓰는 경우`R2L` 오른쪽에서 왼쪽으로 텍스트를 위한 설정입니다. 이 설정은 아랍어나 히브리어와 같은 언어로 된 문서에 특히 유용합니다.

## 5단계: 창에 문서 제목 표시

다음 속성을 사용하면 창의 제목 표시줄에 문서 제목 또는 파일 이름을 표시할지 여부를 제어할 수 있습니다. 기본적으로 이것은 다음으로 설정됩니다.`false`즉, 파일 이름이 표시됩니다.

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

파일 이름 대신 문서 제목이 표시되도록 하려면 이 설정을 활성화해야 합니다.

## 6단계: 첫 번째 페이지에 맞게 창 크기 조정

때로는 PDF를 열 때 문서 창이 자동으로 크기를 조정하여 첫 번째 페이지에 맞게 조정되기를 원할 수 있습니다. 해당 기능이 활성화되어 있는지 확인하는 방법은 다음과 같습니다.

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

 기본적으로 이것은 다음과 같이 설정됩니다.`false`즉, 첫 번째 페이지 크기에 관계없이 창 크기가 그대로 유지됩니다.

## 7단계: 메뉴 막대 숨기기

더 집중적인 독서 경험을 위해 뷰어 애플리케이션의 메뉴 막대를 숨기고 싶을 수 있습니다. 다음 줄을 사용하여 이 설정을 검색할 수 있습니다.

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

 이것은 반환됩니다`true` 메뉴 표시줄이 숨겨져 있는 경우`false` 그렇지 않으면.

## 8단계: 도구 모음 숨기기

마찬가지로, 더 깔끔한 사용자 인터페이스를 위해 PDF 뷰어에서 툴바를 숨기고 싶을 수도 있습니다. 이 설정은 다음과 같이 검색할 수 있습니다.

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

이 설정을 활성화하면 PDF를 열 때 도구 모음이 숨겨집니다.

## 9단계: 스크롤 막대 및 UI 요소 숨기기

스크롤 바와 같은 추가 UI 요소 없이 페이지 콘텐츠만 표시하려는 경우 이 설정은 해당 동작을 제어합니다.

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

 설정 시`true`PDF 뷰어는 스크롤 막대와 다른 사용자 인터페이스 요소를 숨기고 문서 내용만 남겨둡니다.

## 10단계: 전체 화면이 아닌 페이지 모드 설정

 전체 화면 모드를 종료할 때 문서가 나타나는 방식을 제어할 수 있습니다.`NonFullScreenPageMode` 속성. 이 설정은 사용자가 전체 화면 모드가 아닌 모드에서 문서와 상호 작용하는 방법을 정의하는 데 유용합니다.

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

출력은 썸네일, 개요 또는 첨부 패널 등 다양한 모드로 설정할 수 있습니다.

## 11단계: 페이지 레이아웃 정의

이 설정을 사용하면 문서 페이지가 배치되는 방식을 제어할 수 있습니다. 예를 들어, 단일 페이지 보기 또는 연속 열 보기를 선택할 수 있습니다.

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

이를 통해 사용자는 문서 내용을 읽거나 보는 방식에 있어 유연성을 얻을 수 있습니다.

## 12단계: 페이지 모드 지정

 마지막으로,`PageMode` 속성은 문서를 열 때 어떻게 표시할지 정의합니다. 옵션에는 축소판 그림 표시, 전체 화면 모드로 전환 또는 첨부 파일 패널 표시가 있습니다.

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

사용자의 요구 사항에 따라 PDF 목적에 맞는 모드로 설정할 수 있습니다.

## 결론

보시다시피, Aspose.PDF for .NET은 다양한 PDF 뷰어에서 PDF 문서가 표시되는 방식을 조작하는 포괄적인 도구를 제공합니다. 툴바를 숨기거나, 창을 가운데에 배치하거나, 텍스트 방향을 제어하든 Aspose.PDF는 사용자의 시청 경험을 향상시키는 유연성을 제공합니다.

# 자주 묻는 질문

### PDF의 초기 확대 수준을 사용자 정의할 수 있나요?
네, Aspose.PDF를 사용하면 문서를 열 때 확대/축소 수준을 설정할 수 있습니다.

### PDF 창 크기를 잠그려면 어떻게 해야 하나요?
 설정할 수 있습니다`FitWindow` 창 크기가 조정되는 것을 방지하는 속성입니다.

### Aspose.PDF는 다양한 읽기 모드를 지원합니까?
네, 전체 화면, 썸네일, 첨부 파일 등 다양한 모드를 지원합니다.

### PDF 뷰어에서 스크롤바를 숨길 수 있나요?
 물론, 스크롤 막대를 설정하여 숨길 수 있습니다.`HideWindowUI` 재산에`true`.

### 문서 창을 열 때 가운데에 정렬할 수 있나요?
 네, 이를 설정하여 제어할 수 있습니다.`CenterWindow` 재산.