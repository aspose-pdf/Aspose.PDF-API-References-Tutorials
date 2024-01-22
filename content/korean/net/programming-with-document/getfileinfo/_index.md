---
title: PDF 파일로 파일 정보 가져오기
linktitle: PDF 파일로 파일 정보 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF의 PDF 파일 기능에서 GetFileInfo를 사용하여 PDF 문서에 대한 메타데이터 정보를 검색하는 방법을 알아보세요.
type: docs
weight: 180
url: /ko/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET은 개발자가 .NET 애플리케이션에서 PDF 파일을 생성, 편집 및 변환할 수 있도록 하는 널리 사용되는 PDF 조작 라이브러리입니다. 이 라이브러리가 제공하는 기능 중 하나는 PDF 문서의 메타데이터에 대한 정보를 검색하는 기능입니다. 이 튜토리얼에서는 다음을 사용하는 단계를 안내합니다.`GetFileInfo` PDF 문서의 메타데이터에 대한 정보를 검색하는 .NET용 Aspose.PDF의 기능입니다.

## 1단계: .NET용 Aspose.PDF 설치

 .NET 애플리케이션에서 .NET용 Aspose.PDF를 사용하려면 먼저 라이브러리를 설치해야 합니다. 다음에서 최신 버전의 라이브러리를 다운로드할 수 있습니다.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net).

라이브러리를 다운로드한 후 ZIP 파일의 내용을 컴퓨터의 폴더에 추출합니다. 그런 다음 .NET 프로젝트에 Aspose.PDF for .NET DLL에 대한 참조를 추가해야 합니다.

## 2단계: PDF 문서 로드

.NET용 Aspose.PDF를 설치하고 .NET 프로젝트에 DLL에 대한 참조를 추가한 후에는 다음을 사용할 수 있습니다.`GetFileInfo` PDF 문서의 메타데이터에 대한 정보를 검색하는 기능입니다.

이 기능을 사용하는 첫 번째 단계는 정보를 검색하려는 PDF 문서를 로드하는 것입니다. 이렇게 하려면 다음 코드를 사용할 수 있습니다.

```csharp
// PDF 문서의 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF 문서 열기
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

 위 코드에서`"YOUR DOCUMENT DIRECTORY"` PDF 문서가 있는 디렉토리의 경로를 사용하세요. 이 코드는 PDF 문서를`Document` 그런 다음 문서의 메타데이터에 대한 정보를 검색하는 데 사용할 수 있습니다.

## 3단계: 문서의 메타데이터 검색

PDF 문서의 메타데이터에 대한 정보를 검색하려면 다음 코드를 사용할 수 있습니다.

```csharp
// 문서 정보 가져오기
DocumentInfo docInfo = pdfDocument.Info;

// 문서 정보 표시
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

위 코드에서 각 줄은 PDF 문서의 다양한 메타데이터 속성을 검색하여 콘솔에 출력합니다. 관심 있는 속성만 검색하도록 이 코드를 사용자 정의할 수 있습니다.

### 예제 소스 코드는 .NET용 Aspose.PDF를 사용하여 PDF 파일 정보를 얻습니다.

 다음은 PDF 문서의 메타데이터를 검색하는 전체 소스 코드입니다.`GetFileInfo` .NET용 Aspose.PDF의 기능:

```csharp
// PDF 문서의 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

//PDF 문서 열기
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

// 문서 정보 가져오기
DocumentInfo docInfo = pdfDocument.Info;

// 문서 정보 표시
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 메타데이터에 대한 정보를 검색하는 방법을 논의했습니다. PDF 문서를 로드하고 해당 메타데이터 속성에 액세스하면 문서의 특성과 속성에 대한 정보를 수집할 수 있습니다. .NET용 Aspose.PDF는 메타데이터 정보 검색을 포함하여 PDF 문서 작업을 위한 간단하고 사용하기 쉬운 API를 제공하므로 .NET 응용 프로그램에서 PDF 조작을 위한 유용한 도구입니다.

### FAQ

#### Q: PDF 문서의 메타데이터란 무엇입니까?

A: PDF 문서의 메타데이터는 문서의 속성과 특성을 설명하는 정보를 의미합니다. 이 정보에는 일반적으로 문서 제목, 작성자, 주제, 키워드, 작성 날짜, 수정 날짜 등이 포함됩니다.

#### Q: 내 .NET 프로젝트에 .NET용 Aspose.PDF를 어떻게 설치할 수 있나요?

 A: .NET용 Aspose.PDF를 설치하려면 다음에서 라이브러리를 다운로드해야 합니다.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net). 다운로드한 후 ZIP 파일의 내용을 추출하고 .NET 프로젝트에 Aspose.PDF for .NET DLL에 대한 참조를 추가하세요.

#### Q: 특정 메타데이터 속성만 검색하도록 코드를 사용자 정의할 수 있습니까?

A: 예, 필요하지 않은 줄을 주석 처리하여 특정 메타데이터 속성을 검색하도록 코드를 사용자 정의할 수 있습니다. 코드의 각 줄은 특정 메타데이터 속성에 해당하므로 요구 사항에 따라 속성을 포함하거나 제외할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 어떤 유형의 메타데이터 속성을 검색할 수 있습니까?

A: .NET용 Aspose.PDF를 사용하면 작성자, 제목, 주제, 키워드, 생성 날짜 및 수정 날짜를 포함하여 PDF 문서의 다양한 메타데이터 속성을 검색할 수 있습니다.