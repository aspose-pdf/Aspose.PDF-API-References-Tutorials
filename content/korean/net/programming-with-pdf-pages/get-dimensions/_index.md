---
title: PDF 페이지 크기 가져오기
linktitle: PDF 페이지 크기 가져오기
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 페이지 치수를 가져오고 조작을 수행하는 방법을 설명합니다. 자세한 단계를 제공하여 프로세스를 안내합니다.
type: docs
weight: 60
url: /ko/net/programming-with-pdf-pages/get-dimensions/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 페이지 크기를 가져오는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 이 기능을 이해하고 자신의 프로젝트에서 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼을 마치면 Aspose.PDF for .NET을 사용하여 PDF 파일에서 페이지 크기를 가져오는 방법을 알게 됩니다.

## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 개발 환경에 설치된 .NET용 Aspose.PDF

## 1단계: 문서 디렉토리 정의
먼저, 문서 디렉토리 경로를 설정해야 합니다. 이는 PDF 파일이 있는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: PDF 문서 열기
 그런 다음 다음을 사용하여 PDF 파일을 열 수 있습니다.`Document` Aspose.PDF 클래스. PDF 파일에 대한 올바른 경로를 지정해야 합니다.

```csharp
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
```

## 3단계: 빈 페이지 추가(필요한 경우)
 PDF 문서에 이미 페이지가 포함되어 있는 경우 인덱스를 사용하여 기존 페이지로 이동할 수 있습니다.`1` (첫 번째 페이지의 인덱스는 1입니다). 그렇지 않으면 문서에 새 페이지를 추가할 수 있습니다.

```csharp
Page page = pdfDocument.Pages.Count > 0? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
```

## 4단계: 페이지 크기 가져오기
 이제 다음을 사용하여 페이지 크기를 얻을 수 있습니다.`GetPageRect()` 의 방법`Page` 객체입니다. 이 메서드는 다음을 반환합니다.`Rectangle` 페이지의 크기를 포함하는 개체입니다. 다음을 사용하여 너비와 높이에 액세스할 수 있습니다.`Width` 그리고`Height` 속성.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

## 5단계: 페이지 회전
 페이지를 회전하려면 다음을 사용할 수 있습니다.`Rotate` 의 속성`Page`객체. 이 예에서 페이지는 90도 회전됩니다.

```csharp
page. Rotate = Rotate. on90;
```

## 6단계: 페이지 크기 다시 가져오기
 페이지 회전 후 다음을 사용하여 페이지 크기를 다시 가져올 수 있습니다.`GetPageRect()` 방법.

```csharp
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
```

### .NET용 Aspose.PDF를 사용하여 차원 가져오기 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "UpdateDimensions.pdf");
// PDF 문서에 빈 페이지를 추가합니다
Page page = pdfDocument.Pages.Count > 0 ? pdfDocument.Pages[1] : pdfDocument.Pages.Add();
// 페이지 높이 및 너비 정보 가져오기
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);
// 페이지를 90도 각도로 회전
page.Rotate = Rotation.on90;
// 페이지 높이 및 너비 정보 가져오기
Console.WriteLine(page.GetPageRect(true).Width.ToString() + ":" + page.GetPageRect(true).Height);

```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 페이지의 크기를 가져오는 방법을 알아보았습니다. 제공된 단계를 따르면 페이지 크기를 쉽게 추출하고 다른 PDF 조작 작업을 수행할 수 있습니다. Aspose.PDF for .NET은 PDF 파일 작업에 큰 유연성을 제공하며 강력하고 사용자 정의된 솔루션을 개발할 수 있습니다.

Aspose.PDF 문서를 더 탐색해 이 라이브러리가 제공하는 모든 기능을 알아보세요.

### PDF 페이지 크기를 얻기 위한 FAQ

#### 질문: PDF 파일에서 특정 페이지의 크기를 어떻게 얻을 수 있나요?

A: PDF 파일에서 특정 페이지의 크기를 얻으려면 다음을 사용할 수 있습니다.`GetPageRect()` 의 방법`Page` .NET용 Aspose.PDF의 개체입니다. 이 메서드는 다음을 반환합니다.`Rectangle` 페이지의 크기(너비와 높이)를 포함하는 객체입니다.

####  Q: 무슨 일이야?`GetPageRect(true)` method do in the provided C# source code?

 A: 그`GetPageRect(true)` 제공된 C# 소스 코드의 메서드는 회전을 적용한 후 페이지의 크기를 반환합니다. 페이지가 회전된 경우 메서드는 회전된 페이지의 크기를 반환하며, 이는 원래 크기와 다를 수 있습니다.

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서의 모든 페이지의 크기를 얻을 수 있나요?

 A: 예, PDF 문서의 모든 페이지의 크기를 얻으려면 다음을 반복할 수 있습니다.`Pages` 의 컬렉션`Document` 객체 및 사용`GetPageRect(true)` 각 페이지에 대한 방법입니다.

#### 질문: 페이지의 크기에 따라 방향(세로 또는 가로)을 어떻게 결정할 수 있나요?

A: 치수에 따라 페이지의 방향을 확인하려면 페이지의 너비와 높이를 비교하면 됩니다. 너비가 높이보다 크면 페이지가 가로 방향이고, 높이가 너비보다 크면 페이지가 세로 방향입니다.

#### 질문: Aspose.PDF for .NET을 사용하여 페이지의 크기를 수정할 수 있나요?

 A: 네, Aspose.PDF for .NET에서 페이지의 크기를 수정할 수 있습니다.`Rectangle` 페이지 크기를 나타내는 개체로, 요구 사항에 맞게 너비와 높이를 조정한 후 페이지에 변경 사항을 적용할 수 있습니다.