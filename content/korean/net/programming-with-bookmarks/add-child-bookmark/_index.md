---
title: PDF 파일에 하위 북마크 추가
linktitle: PDF 파일에 하위 북마크 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하면 더욱 체계적으로 탐색할 수 있도록 PDF 파일에 하위 북마크를 쉽게 추가할 수 있습니다.
type: docs
weight: 20
url: /ko/net/programming-with-bookmarks/add-child-bookmark/
---
PDF 파일에 하위 북마크를 추가하면 보다 체계화된 구성과 탐색이 가능해집니다. .NET용 Aspose.PDF를 사용하면 다음 소스 코드에 따라 하위 북마크를 쉽게 추가할 수 있습니다.

## 1단계: 필수 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 import 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 하위 책갈피를 추가하려는 PDF 파일이 포함된 폴더의 경로를 지정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"`다음 코드에 문서 폴더의 실제 경로를 입력하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3단계: PDF 문서 열기

이제 다음 코드를 사용하여 하위 북마크를 추가하려는 PDF 문서를 엽니다.

```csharp
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
```

## 4단계: 상위 북마크 개체 만들기

 이 단계에서는 다음을 사용하여 상위 북마크 개체를 만듭니다.`OutlineItemCollection` 클래스를 선택하고 제목, 기울임꼴 속성, 굵은 속성과 같은 속성을 설정합니다. 해당 코드는 다음과 같습니다.

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent bookmark";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
```

## 5단계: 하위 북마크 개체 생성

이 단계에서는 다음을 사용하여 하위 북마크 개체를 다시 생성합니다.`OutlineItemCollection` 클래스를 선택하고 해당 속성을 설정합니다. 해당 코드는 다음과 같습니다.

```csharp
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Sub Bookmark";
pdfChildOutline. Italic = true;
pdfChildOutline. Bold = true;
```

## 6단계: 상위 북마크에 하위 북마크 추가

 마지막으로 생성된 하위 북마크를 다음을 사용하여 상위 북마크의 하위 북마크 컬렉션에 추가합니다.`Add` 상위 개체의 메서드입니다. 해당 코드는 다음과 같습니다.

```csharp
pdfOutline.Add(pdfChildOutline);
```

## 7단계: 문서의 북마크 컬렉션에 상위 북마크 추가

 마지막으로 다음을 사용하여 문서의 북마크 컬렉션에 상위 북마크를 추가합니다.`Add` 의 방법`Outlines` 재산. 해당 코드는 다음과 같습니다.

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### .NET용 Aspose.PDF를 사용하여 하위 책갈피 추가에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "AddChildBookmark.pdf");
// 상위 북마크 개체 만들기
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Parent Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;      
// 하위 북마크 개체 만들기
OutlineItemCollection pdfChildOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfChildOutline.Title = "Child Outline";
pdfChildOutline.Italic = true;
pdfChildOutline.Bold = true;
// 상위 북마크 컬렉션에 하위 북마크 추가
pdfOutline.Add(pdfChildOutline);
// 문서의 개요 컬렉션에 상위 책갈피를 추가합니다.
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddChildBookmark_out.pdf";
// 출력 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nChild bookmark added successfully.\nFile saved at " + dataDir);
```

## 결론

축하합니다! 이제 .NET용 Aspose.PDF를 사용하여 하위 책갈피를 추가하는 단계별 가이드가 있습니다. 이 코드를 사용하여 PDF 문서의 북마크를 구성하고 구조화할 수 있습니다.

고급 북마크 조작 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.

### PDF 파일에 하위 북마크 추가에 대한 FAQ

#### Q: PDF 파일의 하위 북마크란 무엇입니까?

A: 하위 북마크라고도 하는 하위 북마크는 상위 북마크 아래 계층적으로 구조화된 PDF 문서 내의 탐색 요소입니다. 이는 문서에 대한 보다 체계적이고 상세한 목차를 생성하는 방법을 제공합니다.

#### Q: C# 프로젝트에 필요한 라이브러리를 어떻게 가져오나요?

A: C# 프로젝트에 필요한 라이브러리를 가져오려면 다음 가져오기 지시문을 사용할 수 있습니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

이러한 라이브러리는 PDF 문서 작업 및 대화형 기능에 필요한 클래스와 기능을 제공합니다.

#### Q: 문서 폴더의 경로를 어떻게 지정합니까?

 A: 제공된 소스 코드에서`"YOUR DOCUMENT DIRECTORY"` 작업하려는 PDF 파일이 포함된 폴더의 실제 경로를 사용하세요. 이렇게 하면 코드가 대상 PDF 파일을 올바르게 찾을 수 있습니다.

#### Q: 여러 수준의 하위 북마크를 만들 수 있나요?

A: 예, 튜토리얼에 설명된 프로세스를 확장하여 여러 수준의 하위 북마크를 생성할 수 있습니다. 하위 책갈피가 포함된 상위 책갈피를 만들고 추가로 중첩하면 복잡한 PDF 문서에 대한 책갈피의 계층 구조를 만들 수 있습니다.

####  Q: 이 프로그램의 목적은 무엇입니까?`OutlineItemCollection` class?

 답:`OutlineItemCollection` .NET용 Aspose.PDF의 클래스는 기본적으로 PDF 문서의 북마크인 개요를 생성하고 관리하는 데 사용됩니다. 이 클래스를 사용하면 제목, 글꼴 스타일, 책갈피 작업과 같은 속성을 설정할 수 있습니다.

#### Q: 상위 북마크에 하위 북마크를 어떻게 추가하나요?

 A: 상위 북마크에 하위 북마크를 추가하려면 새 북마크를 생성하세요.`OutlineItemCollection` 하위 책갈피에 대한 개체를 지정하고 해당 속성을 설정합니다. 그런 다음`Add` 상위 북마크의 방법`OutlineItemCollection` 상위 컬렉션에 하위 북마크를 추가합니다.

#### 질문: 하위 북마크의 모양을 사용자 정의할 수 있나요?

A: 예, 상위 북마크와 유사하게 제목, 글꼴 스타일 및 기타 속성과 같은 속성을 설정하여 하위 북마크의 모양을 사용자 정의할 수 있습니다. 이를 통해 시각적으로 독특하고 유익한 북마크를 만들 수 있습니다.

#### Q: .NET용 Aspose.PDF는 다른 프로그래밍 언어와 호환됩니까?

A: .NET용 Aspose.PDF는 C# 및 .NET 환경을 위해 특별히 설계되었습니다. 그러나 Aspose는 Java 및 Android와 같은 다른 프로그래밍 언어에 대해 각각 해당 플랫폼에 맞게 조정된 유사한 라이브러리를 제공합니다.

#### Q: 하위 북마크는 PDF 탐색을 어떻게 개선합니까?

A: 하위 책갈피는 보다 구조화되고 정리된 목차를 제공하여 PDF 탐색을 개선합니다. 사용자는 계층적 북마크 구조를 통해 문서의 특정 섹션에 빠르게 액세스할 수 있습니다.