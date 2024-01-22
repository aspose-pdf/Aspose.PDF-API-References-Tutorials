---
title: PDF 파일에 북마크 추가
linktitle: PDF 파일에 북마크 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 향상된 탐색을 위해 PDF 파일에 책갈피를 쉽게 추가할 수 있습니다.
type: docs
weight: 10
url: /ko/net/programming-with-bookmarks/add-bookmark/
---
PDF 파일에 북마크를 추가하면 쉽고 빠르게 탐색할 수 있습니다. .NET용 Aspose.PDF를 사용하면 다음 소스 코드에 따라 PDF 파일에 북마크를 쉽게 추가할 수 있습니다.

## 1단계: 필수 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 import 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 북마크를 추가하려는 PDF 파일이 포함된 폴더의 경로를 지정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"`다음 코드에 문서 폴더의 실제 경로를 입력하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3단계: PDF 문서 열기

이제 다음 코드를 사용하여 북마크를 추가하려는 PDF 문서를 엽니다.

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## 4단계: 북마크 개체 만들기

 이 단계에서는 다음을 사용하여 북마크 개체를 만듭니다.`OutlineItemCollection` 클래스를 선택하고 제목, 기울임꼴 속성, 굵은 속성, 클릭 시 수행할 작업 등의 속성을 설정합니다. 해당 코드는 다음과 같습니다.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## 5단계: 문서에 북마크 추가

 마지막으로 생성된 북마크를 다음을 사용하여 문서의 북마크 컬렉션에 추가합니다.`Add` 의 방법`Outlines` 재산. 해당 코드는 다음과 같습니다.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### .NET용 Aspose.PDF를 사용하여 책갈피 추가에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
// 북마크 개체 만들기
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
// 대상 페이지 번호 설정
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
// 문서의 개요 컬렉션에 북마크를 추가합니다.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
// 출력 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## 결론

축하합니다! 이제 .NET용 Aspose.PDF를 사용하여 북마크를 추가하는 단계별 가이드가 제공됩니다. 이 코드를 사용하면 사용자 정의 책갈피를 추가하여 PDF 문서 탐색을 개선할 수 있습니다.

고급 북마크 조작 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.


### PDF 파일에 북마크 추가에 대한 FAQ

#### Q: PDF 파일의 북마크란 무엇입니까?

답변: 개요라고도 알려진 북마크는 PDF 문서 내에서 탐색 및 구조를 제공하는 대화형 요소입니다. 이를 통해 사용자는 특정 섹션이나 페이지로 빠르게 이동할 수 있습니다.

#### Q: PDF 파일에 북마크를 추가해야 하는 이유는 무엇입니까?

A: PDF 파일에 책갈피를 추가하면 사용자 경험이 향상되고 독자가 문서 내용을 더 쉽게 탐색할 수 있습니다. 북마크는 목차 역할을 하거나 중요한 섹션에 대한 빠른 액세스를 제공할 수 있습니다.

#### Q: C# 프로젝트에 필요한 라이브러리를 어떻게 가져오나요?

A: C# 프로젝트에 필요한 라이브러리를 가져오려면 다음 가져오기 지시문을 포함하세요.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

이러한 지시어를 사용하면 PDF 문서 및 책갈피 작업에 필요한 클래스와 메서드에 액세스할 수 있습니다.

#### Q: 문서 폴더의 경로를 어떻게 지정합니까?

 답: 교체하다`"YOUR DOCUMENT DIRECTORY"` 북마크를 추가하려는 PDF 파일이 포함된 폴더의 실제 경로와 함께 제공된 소스 코드에.

#### Q: 북마크를 추가하기 위해 PDF 문서를 어떻게 열 수 있나요?

A: 북마크를 추가하기 위해 PDF 문서를 열려면 다음 코드를 사용하십시오.

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

 바꾸다`"AddBookmark.pdf"` 실제 파일 이름으로.

#### Q: 북마크 개체를 어떻게 생성합니까?

 A: 북마크 개체를 생성하려면`OutlineItemCollection` 수업. 제목, 기울임체 스타일, 굵은 스타일, 클릭 시 수행할 동작 등의 속성을 사용자 정의합니다.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

####  Q: 이 프로그램의 목적은 무엇입니까?`Action` property in a bookmark?

 답:`Action` 속성은 책갈피를 클릭할 때 수행할 작업을 지정합니다. 이 예에서는`GoToAction`특정 페이지(이 경우 2페이지)로 이동하는 클래스입니다.

#### Q: 문서에 북마크를 어떻게 추가하나요?

 답변:`Add` 의 방법`Outlines` 생성된 북마크를 문서의 북마크 컬렉션에 추가하는 속성입니다.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### Q: 이 방법을 사용하여 여러 북마크를 추가할 수 있나요?

A: 예, 4~8단계를 반복하여 문서에 여러 개의 북마크를 추가할 수 있습니다. 필요에 따라 각 북마크의 속성과 작업을 사용자 정의합니다.

#### Q: 업데이트된 PDF 파일을 어떻게 저장합니까?

 A: 다음을 사용하여 업데이트된 PDF 파일을 저장합니다.`Save` 의 방법`pdfDocument` 물체:

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### Q: 북마크가 추가되었는지 어떻게 확인할 수 있나요?

A: 생성된 PDF 파일을 열어 지정된 책갈피가 문서에 추가되었는지 확인하세요.

#### Q: 추가할 수 있는 북마크 수에 제한이 있나요?

A: 일반적으로 추가할 수 있는 북마크 수에는 엄격한 제한이 없지만 최적의 성능을 위해서는 문서의 크기와 복잡성을 고려하십시오.

#### 질문: 북마크 모양을 사용자 정의할 수 있나요?

A: 예, Aspose.PDF 기능을 사용하여 북마크 모양, 색상, 스타일 및 기타 속성을 추가로 사용자 정의할 수 있습니다.