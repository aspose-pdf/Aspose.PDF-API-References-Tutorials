---
title: PDF 속성 가져오기
linktitle: PDF 속성 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 상자 크기 및 회전과 같은 PDF 속성을 얻는 단계별 가이드입니다.
type: docs
weight: 100
url: /ko/net/programming-with-pdf-pages/get-properties/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 속성을 가져오는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 .NET용 Aspose.PDF를 사용하여 아트 상자, 자르기 상자, 자르기 상자 등과 같은 PDF 페이지의 다양한 속성에 액세스하는 방법을 알게 됩니다.

## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 개발 환경에 설치된 .NET용 Aspose.PDF

## 1단계: 문서 디렉터리 설정
먼저 문서 디렉터리의 경로를 설정해야 합니다. 이는 가져오려는 속성이 있는 PDF 파일의 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: PDF 문서 열기
 다음으로, 다음을 사용하여 PDF 문서를 열어야 합니다.`Document` Aspose.PDF의 클래스입니다. PDF 파일의 올바른 경로를 지정하십시오.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## 3단계: 페이지 컬렉션에 액세스
 이제 다음을 사용하여 문서의 페이지 컬렉션에 액세스할 수 있습니다.`Pages` 의 재산`pdfDocument` 물체.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4단계: 특정 페이지로 이동
그런 다음 컬렉션에 있는 페이지의 색인을 사용하여 특정 페이지로 이동할 수 있습니다. 아래 예에서는 두 번째 페이지(색인 1)에 액세스합니다.

```csharp
Page pdfPage = pageCollection[1];
```

## 5단계: 페이지 속성 가져오기
 이제 아트 상자, 자르기 상자, 자르기 상자 등과 같은 PDF 페이지의 다양한 속성을 해당 속성을 사용하여 얻을 수 있습니다.`pdfPage` 물체.

```csharp
Console.WriteLine("ArtBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
Console.WriteLine("BleedBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.BleedBox.Height, pdf

Page.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
Console.WriteLine("CropBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
Console.WriteLine("MediaBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
Console.WriteLine("TrimBox: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
Console.WriteLine("Rect: Height={0}, Width={1}, LLX={2}, LLY={3}, URX={4}, URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
Console.WriteLine("Page number: {0}", pdfPage.Number);
Console.WriteLine("Rotate: {0}", pdfPage.Rotate);
```

### .NET용 Aspose.PDF를 사용하여 속성 가져오기에 대한 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
// 페이지 컬렉션 가져오기
PageCollection pageCollection = pdfDocument.Pages;
// 특정 페이지 가져오기
Page pdfPage = pageCollection[1];
// 페이지 속성 가져오기
System.Console.WriteLine("ArtBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.ArtBox.Height, pdfPage.ArtBox.Width, pdfPage.ArtBox.LLX, pdfPage.ArtBox.LLY, pdfPage.ArtBox.URX, pdfPage.ArtBox.URY);
System.Console.WriteLine("BleedBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.BleedBox.Height, pdfPage.BleedBox.Width, pdfPage.BleedBox.LLX, pdfPage.BleedBox.LLY, pdfPage.BleedBox.URX, pdfPage.BleedBox.URY);
System.Console.WriteLine("CropBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.CropBox.Height, pdfPage.CropBox.Width, pdfPage.CropBox.LLX, pdfPage.CropBox.LLY, pdfPage.CropBox.URX, pdfPage.CropBox.URY);
System.Console.WriteLine("MediaBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.MediaBox.Height, pdfPage.MediaBox.Width, pdfPage.MediaBox.LLX, pdfPage.MediaBox.LLY, pdfPage.MediaBox.URX, pdfPage.MediaBox.URY);
System.Console.WriteLine("TrimBox : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.TrimBox.Height, pdfPage.TrimBox.Width, pdfPage.TrimBox.LLX, pdfPage.TrimBox.LLY, pdfPage.TrimBox.URX, pdfPage.TrimBox.URY);
System.Console.WriteLine("Rect : Height={0},Width={1},LLX={2},LLY={3},URX={4},URY={5}", pdfPage.Rect.Height, pdfPage.Rect.Width, pdfPage.Rect.LLX, pdfPage.Rect.LLY, pdfPage.Rect.URX, pdfPage.Rect.URY);
System.Console.WriteLine("Page Number : {0}", pdfPage.Number);
System.Console.WriteLine("Rotate : {0}", pdfPage.Rotate);

```

## 결론
축하합니다! .NET용 Aspose.PDF를 사용하여 PDF 속성을 성공적으로 얻었습니다. PDF 문서를 열고, 특정 페이지로 이동하고, 치수 상자 및 회전과 같은 다양한 페이지 속성을 가져오는 방법을 배웠습니다. 이제 이 정보를 사용하여 해당 속성에 따라 PDF 파일 처리를 사용자 정의할 수 있습니다.

고급 기능 및 사용자 정의 가능성에 대한 자세한 내용은 .NET용 공식 Aspose.PDF 문서를 확인하세요.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 속성을 어떻게 얻을 수 있나요?

A: .NET용 Aspose.PDF를 사용하여 PDF 속성을 얻으려면 다음 단계를 따르세요.

1. 검색하려는 속성이 있는 PDF 파일의 경로를 지정하여 문서 디렉터리를 설정합니다.
2.  다음을 사용하여 PDF 문서를 엽니다.`Document` PDF 파일에 대한 올바른 경로를 제공하는 Aspose.PDF의 클래스입니다.
3.  다음을 사용하여 문서의 페이지 컬렉션에 액세스합니다.`Pages` 의 재산`pdfDocument` 물체.
4. 컬렉션에 있는 페이지의 인덱스를 사용하여 특정 페이지로 이동합니다(인덱싱은 1부터 시작).
5.  ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number 및 Rotation과 같은 PDF 페이지의 다양한 속성을 해당 속성을 사용하여 가져옵니다.`pdfPage` 물체.

#### Q: .NET용 Aspose.PDF를 사용하여 검색할 수 있는 PDF 페이지의 다양한 속성은 무엇입니까?

A: .NET용 Aspose.PDF를 사용하여 다음과 같은 PDF 페이지의 다양한 속성을 검색할 수 있습니다.

- ArtBox: 페이지 아트웍의 크기를 나타냅니다.
- BleedBox: 페이지 도련의 크기를 나타냅니다.
- CropBox: 자른 후 페이지에 표시되는 콘텐츠의 크기를 나타냅니다.
- MediaBox: 페이지의 물리적 미디어 크기를 나타냅니다.
- TrimBox: 페이지의 잘린 콘텐츠 크기를 나타냅니다.
- Rect: 페이지 경계 상자의 크기를 나타냅니다.
- 페이지 번호: 문서의 페이지 번호를 나타냅니다.
- 회전: 페이지의 회전 각도를 나타냅니다.

#### Q: PDF 문서의 특정 페이지에 액세스하여 속성을 검색하려면 어떻게 해야 합니까?

 답변: PDF 문서의 특정 페이지에 액세스하고 해당 속성을 검색하려면 다음을 사용할 수 있습니다.`Pages` 의 재산`pdfDocument` 문서의 페이지 컬렉션에 액세스하는 개체입니다. 그런 다음 컬렉션의 페이지 색인을 사용하여 원하는 페이지로 이동할 수 있습니다. 예를 들어, 두 번째 페이지에 액세스하려면 다음을 사용할 수 있습니다.`pdfDocument.Pages[1]` (인덱싱은 1부터 시작합니다).

#### Q: 페이지 상자 수정 또는 크기 조정과 같은 검색된 속성에 대한 작업을 수행할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하여 PDF 페이지의 속성을 검색하면 다양한 작업을 수행할 수 있습니다. 예를 들어, 페이지 상자의 크기를 수정하거나, 페이지를 회전하거나, PDF 문서의 사용자 정의 처리 및 조작을 위해 검색된 정보를 사용할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 암호화되거나 비밀번호로 보호된 PDF 파일에서 속성 추출을 지원합니까?

A: 예, .NET용 Aspose.PDF는 암호화되거나 비밀번호로 보호된 PDF 파일에서 속성 추출을 지원합니다. PDF 문서를 열 때 올바른 비밀번호를 제공하기만 하면 튜토리얼에서 설명한 것과 동일한 접근 방식을 사용하여 해당 속성에 액세스하고 검색할 수 있습니다.