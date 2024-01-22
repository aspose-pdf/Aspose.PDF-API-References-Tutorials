---
title: PDF 페이지 크기 가져오기
linktitle: PDF 페이지 크기 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: 이 튜토리얼에서는 PDF 페이지 크기를 얻고 .NET용 Aspose.PDF를 사용하여 조작을 수행하는 방법을 설명합니다. 프로세스를 안내하는 자세한 단계가 제공됩니다.
type: docs
weight: 60
url: /ko/net/programming-with-pdf-pages/get-dimensions/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 페이지 크기를 가져오는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.PDF for .NET을 사용하여 PDF 파일의 페이지 크기를 얻는 방법을 알게 됩니다.

## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 개발 환경에 설치된 .NET용 Aspose.PDF

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. PDF 파일이 있는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: PDF 문서 열기
 그런 다음 다음을 사용하여 PDF 파일을 열 수 있습니다.`Document` Aspose.PDF의 클래스입니다. PDF 파일의 올바른 경로를 지정하십시오.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3단계: 빈 페이지 추가(필요한 경우)
 PDF 문서에 이미 페이지가 포함되어 있는 경우 색인을 사용하여 기존 페이지로 이동할 수 있습니다.`1` (첫 번째 페이지의 인덱스는 1입니다.) 그렇지 않으면 문서에 새 페이지를 추가할 수 있습니다.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## 4단계: 페이지 크기 가져오기
 이제 다음을 사용하여 페이지 크기를 얻을 수 있습니다.`GetPageRect()` 의 방법`Page` 물체. 이 메소드는`Rectangle` 페이지의 크기를 포함하는 개체입니다. 다음을 사용하여 너비와 높이에 액세스할 수 있습니다.`Width` 그리고`Height` 속성.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## 5단계: 페이지 회전
 페이지를 회전하려면`Rotate` 의 재산`Page`물체. 이 예에서는 페이지가 90도 회전됩니다.

```csharp
page. Rotate = Rotate. on90;
```

## 6단계: 페이지 크기 다시 가져오기
 페이지 회전 후 다음을 사용하여 페이지 크기를 다시 얻을 수 있습니다.`GetPageRect()` 방법.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### .NET용 Aspose.PDF를 사용하여 치수 가져오기의 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// PDF 문서에 빈 페이지를 추가합니다.
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// 페이지 높이 및 너비 정보 가져오기
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// 페이지를 90도 각도로 회전
page.Rotate = Rotation.on90;
// 페이지 높이 및 너비 정보 가져오기
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 페이지 크기를 얻는 방법을 배웠습니다. 제공된 단계를 따르면 쉽게 페이지 크기를 추출하고 기타 PDF 조작 작업을 수행할 수 있습니다. .NET용 Aspose.PDF는 PDF 파일 작업에 탁월한 유연성을 제공하며 강력하고 맞춤화된 솔루션을 개발할 수 있도록 해줍니다.

이 라이브러리에서 제공하는 모든 기능을 알아보려면 Aspose.PDF 문서를 더 자세히 살펴보세요.

### PDF 페이지 크기 가져오기에 대한 FAQ

#### Q: PDF 파일에서 특정 페이지의 크기를 어떻게 알 수 있나요?

답변: PDF 파일에서 특정 페이지의 크기를 얻으려면 다음을 사용할 수 있습니다.`GetPageRect()` 의 방법`Page` .NET용 Aspose.PDF의 개체입니다. 이 메소드는`Rectangle` 페이지의 크기(너비 및 높이)를 포함하는 개체입니다.

####  Q: 무엇을 하는가?`GetPageRect(true)` method do in the provided C# source code?

 답:`GetPageRect(true)` 제공된 C# 소스 코드의 메서드는 회전을 적용한 후 페이지의 크기를 반환합니다. 페이지가 회전되면 메서드는 회전된 페이지의 크기를 반환하며 이는 원래 크기와 다를 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서의 모든 페이지 크기를 얻을 수 있습니까?

 A: 예. PDF 문서의 모든 페이지 크기를 반복하여 얻을 수 있습니다.`Pages` 의 컬렉션`Document` 객체를 사용하고`GetPageRect(true)` 각 페이지에 대한 방법입니다.

#### Q: 크기에 따라 페이지 방향(세로 또는 가로)을 어떻게 결정할 수 있습니까?

A: 크기를 기준으로 페이지 방향을 결정하려면 페이지의 너비와 높이를 비교할 수 있습니다. 너비가 높이보다 크면 페이지는 가로 방향이고, 높이가 너비보다 크면 페이지는 세로 방향입니다.

#### Q: .NET용 Aspose.PDF를 사용하여 페이지 크기를 수정할 수 있습니까?

 A: 예, .NET용 Aspose.PDF에서 페이지 크기를 수정할 수 있습니다. 받은 후`Rectangle` 페이지 크기를 나타내는 개체의 경우 요구 사항에 따라 너비와 높이를 조정한 다음 변경 사항을 페이지에 적용할 수 있습니다.