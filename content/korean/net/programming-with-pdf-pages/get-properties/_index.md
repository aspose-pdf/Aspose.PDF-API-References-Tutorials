---
title: PDF 속성 가져오기
linktitle: PDF 속성 가져오기
second_title: .NET API 참조를 위한 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 상자 크기 및 회전과 같은 PDF 속성을 가져오는 단계별 가이드입니다.
type: docs
weight: 100
url: /ko/net/programming-with-pdf-pages/get-properties/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF의 속성을 가져오는 단계별 프로세스를 안내합니다. 번들된 C# 소스 코드를 설명하고 이 기능을 이해하고 자신의 프로젝트에서 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼을 마치면 Aspose.PDF for .NET을 사용하여 아트 상자, 자르기 상자, 자르기 상자 등과 같은 PDF 페이지의 다양한 속성에 액세스하는 방법을 알게 됩니다.

## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 개발 환경에 설치된 .NET용 Aspose.PDF

## 1단계: 문서 디렉토리 설정
먼저, 문서 디렉토리 경로를 설정해야 합니다. 이는 속성을 가져오려는 PDF 파일의 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: PDF 문서 열기
 다음으로, 다음을 사용하여 PDF 문서를 열어야 합니다.`Document` Aspose.PDF 클래스. PDF 파일에 대한 올바른 경로를 지정해야 합니다.

```csharp
Document pdfDocument = new Document(dataDir + "GetProperties.pdf");
```

## 3단계: 페이지 컬렉션에 액세스
 이제 다음을 사용하여 문서의 페이지 컬렉션에 액세스할 수 있습니다.`Pages` 의 속성`pdfDocument` 물체.

```csharp
PageCollection pageCollection = pdfDocument.Pages;
```

## 4단계: 특정 페이지로 이동
그런 다음 컬렉션의 페이지 인덱스를 사용하여 특정 페이지로 이동할 수 있습니다. 아래 예에서 두 번째 페이지(인덱스 1)에 액세스합니다.

```csharp
Page pdfPage = pageCollection[1];
```

## 5단계: 페이지 속성 가져오기
 이제 해당 속성을 사용하여 아트 상자, 자르기 상자, 자르기 상자 등과 같은 PDF 페이지의 다양한 속성을 가져올 수 있습니다.`pdfPage` 물체.

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

### .NET용 Aspose.PDF를 사용하여 속성 가져오기 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
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
축하합니다! Aspose.PDF for .NET을 사용하여 PDF의 속성을 성공적으로 얻었습니다. PDF 문서를 열고, 특정 페이지로 이동하고, 치수 상자 및 회전과 같은 다양한 페이지 속성을 가져오는 방법을 배웠습니다. 이제 이 정보를 사용하여 속성에 따라 PDF 파일 처리를 사용자 정의할 수 있습니다.

고급 기능과 사용자 정의 가능성에 대한 자세한 내용은 .NET용 공식 Aspose.PDF 문서를 확인하세요.

### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 PDF의 속성을 가져오려면 어떻게 해야 합니까?

답변: Aspose.PDF for .NET을 사용하여 PDF의 속성을 가져오려면 다음 단계를 따르세요.

1. 속성을 검색하려는 PDF 파일의 경로를 지정하여 문서 디렉토리를 설정합니다.
2.  PDF 문서를 열려면 다음을 사용하세요.`Document` Aspose.PDF 클래스는 PDF 파일에 대한 올바른 경로를 제공합니다.
3.  다음을 사용하여 문서의 페이지 컬렉션에 액세스하세요.`Pages` 의 속성`pdfDocument` 물체.
4. 컬렉션의 페이지 인덱스를 사용하여 특정 페이지로 이동합니다(인덱싱은 1부터 시작합니다).
5.  ArtBox, BleedBox, CropBox, MediaBox, TrimBox, Rect, Page Number, Rotation 등 PDF 페이지의 다양한 속성을 해당 속성을 사용하여 가져옵니다.`pdfPage` 물체.

#### 질문: Aspose.PDF for .NET을 사용하여 검색할 수 있는 PDF 페이지의 다양한 속성은 무엇입니까?

A: Aspose.PDF for .NET을 사용하면 다음과 같은 PDF 페이지의 다양한 속성을 검색할 수 있습니다.

- ArtBox: 페이지 아트워크의 크기를 나타냅니다.
- BleedBox: 페이지의 여백 크기를 나타냅니다.
- CropBox: 잘라낸 후 페이지에 표시되는 콘텐츠의 크기를 나타냅니다.
- 미디어 상자: 페이지의 물리적 미디어의 크기를 나타냅니다.
- TrimBox: 페이지에서 잘린 콘텐츠의 크기를 나타냅니다.
- 사각형: 페이지 경계 상자의 크기를 나타냅니다.
- 페이지 번호: 문서의 페이지 번호를 나타냅니다.
- 회전: 페이지의 회전 각도를 나타냅니다.

#### 질문: PDF 문서의 특정 페이지에 접근하여 속성을 검색하려면 어떻게 해야 합니까?

 A: PDF 문서의 특정 페이지에 액세스하고 해당 속성을 검색하려면 다음을 사용할 수 있습니다.`Pages` 의 속성`pdfDocument` 문서의 페이지 컬렉션에 액세스하기 위한 객체입니다. 그런 다음 컬렉션의 페이지 인덱스를 사용하여 원하는 페이지로 이동할 수 있습니다. 예를 들어 두 번째 페이지에 액세스하려면 다음을 사용할 수 있습니다.`pdfDocument.Pages[1]` (인덱싱은 1부터 시작합니다).

#### 질문: 검색된 속성에 대해 페이지 상자를 수정하거나 크기를 조정하는 등 작업을 수행할 수 있나요?

A: 네, Aspose.PDF for .NET을 사용하여 PDF 페이지의 속성을 검색하면 해당 페이지에서 다양한 작업을 수행할 수 있습니다. 예를 들어, 페이지 상자의 크기를 수정하거나, 페이지를 회전하거나, 검색된 정보를 사용하여 PDF 문서의 사용자 정의 처리 및 조작을 수행할 수 있습니다.

#### 질문: .NET용 Aspose.PDF는 암호화되거나 암호로 보호된 PDF 파일에서 속성을 추출하는 것을 지원합니까?

A: 네, Aspose.PDF for .NET은 암호화되거나 암호로 보호된 PDF 파일에서 속성을 추출하는 것을 지원합니다. PDF 문서를 열기 위한 올바른 암호를 제공하는 한, 튜토리얼에서 설명한 것과 동일한 접근 방식을 사용하여 해당 속성에 액세스하고 검색할 수 있습니다.