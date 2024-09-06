---
title: 페이지에서 모든 주석 가져오기
linktitle: 페이지에서 모든 주석 가져오기
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드에서 Aspose.PDF for .NET을 사용하여 PDF 파일에서 주석을 추출하는 방법을 알아보세요. 모든 레벨의 개발자에게 완벽합니다.
type: docs
weight: 70
url: /ko/net/annotations/getallannotationsfrompage/
---
## 소개

.NET용 Aspose.PDF 세계에 오신 것을 환영합니다! PDF 문서를 프로그래밍 방식으로 조작하려는 경우 올바른 곳에 왔습니다. Aspose.PDF는 개발자가 PDF 파일을 쉽게 만들고, 편집하고, 관리할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 PDF 페이지에서 주석을 추출하는 특정 기능에 대해 자세히 알아보겠습니다. 노련한 개발자이든 방금 시작한 개발자이든 이 가이드는 단계별로 프로세스를 안내하여 모든 세부 사항을 이해할 수 있도록 합니다.

## 필수 조건

코드로 넘어가기 전에 시작하는 데 필요한 모든 것이 있는지 확인해 보겠습니다.

1. Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요. 여기서 코드를 작성하고 실행합니다.
2. .NET Framework: .NET framework에 대한 지식이 필수적입니다. 처음이라면 걱정하지 마세요. 간단하게 설명해 드리겠습니다.
3.  .NET용 Aspose.PDF: Aspose.PDF 라이브러리를 다운로드하여 설치해야 합니다. 찾을 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
4. 샘플 PDF 파일: 이 튜토리얼에서는 주석이 있는 PDF 파일이 필요합니다. 직접 만들거나 인터넷에서 샘플을 다운로드할 수 있습니다.

## 패키지 가져오기

시작하려면 필요한 패키지를 가져와야 합니다. Visual Studio 프로젝트를 열고 Aspose.PDF 라이브러리에 대한 참조를 추가합니다. NuGet 패키지 관리자를 사용하여 이를 수행할 수 있습니다.

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
```

## 1단계: 문서 디렉토리 설정

주석을 추출하기 전에 PDF 문서가 어디에 있는지 지정해야 합니다. 이는 문서 디렉토리 경로를 정의하여 수행됩니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 파일이 저장된 실제 경로와 함께. 이것은 프로그램이 파일을 찾을 위치를 알아야 하기 때문에 중요합니다.

## 2단계: PDF 문서 열기

 이제 문서 디렉토리가 설정되었으므로 PDF 파일을 열 차례입니다.`Document` 이를 위해 Aspose.PDF 라이브러리의 클래스를 사용합니다.

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

 이 줄에서 우리는 새로운 인스턴스를 생성합니다.`Document` 클래스를 만들고 PDF 파일의 경로를 전달합니다. 이를 통해 PDF의 내용과 상호 작용할 수 있습니다.

## 3단계: 주석 반복

문서를 열면 이제 주석에 액세스할 수 있습니다. 주석은 PDF에 추가된 주석, 강조 표시 또는 메모입니다. 문서의 첫 번째 페이지에 있는 모든 주석을 반복합니다.

```csharp
// 모든 주석을 반복합니다
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // 주석 속성 가져오기
    Console.WriteLine("Title : {0} ", annotation.Title);
    Console.WriteLine("Subject : {0} ", annotation.Subject);
    Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```

 이 코드 조각에서는 다음을 사용합니다.`foreach` 첫 번째 페이지의 각 주석을 반복하기 위한 루프입니다. 각 주석에 대해 제목, 주제 및 내용을 콘솔에 인쇄합니다. 여기서 마법이 일어나는 것을 볼 수 있습니다!

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서에서 주석을 추출하는 방법을 성공적으로 배웠습니다. 이 강력한 라이브러리는 PDF 파일을 프로그래밍 방식으로 작업할 수 있는 가능성의 세계를 열어줍니다. 보고서를 만들거나, 문서를 관리하거나, 단순히 정보를 추출하든 Aspose.PDF가 해결해 드립니다.

## 자주 묻는 질문

### .NET용 Aspose.PDF란 무엇인가요?
.NET용 Aspose.PDF는 개발자가 프로그래밍 방식으로 PDF 문서를 만들고, 조작하고, 관리할 수 있는 라이브러리입니다.

### Aspose.PDF를 어떻게 설치하나요?
Visual Studio의 NuGet 패키지 관리자를 통해 Aspose.PDF를 설치하거나 다음에서 직접 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/pdf/net/).

### 여러 페이지에서 주석을 추출할 수 있나요?
네, 문서의 모든 페이지를 탐색하여 각 페이지에서 주석을 추출할 수 있습니다.

### 무료 체험판이 있나요?
 예, Aspose.PDF를 무료로 사용해 보려면 여기에서 평가판을 다운로드하세요.[여기](https://releases.aspose.com/).

### Aspose.PDF에 대한 지원은 어디에서 찾을 수 있나요?
 지원을 받고 질문할 수 있습니다.[Aspose 포럼](https://forum.aspose.com/c/pdf/10).