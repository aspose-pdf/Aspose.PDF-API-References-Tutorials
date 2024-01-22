---
title: PDF 파일에서 북마크 확장
linktitle: PDF 파일에서 북마크 확장
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하면 향상된 탐색을 위해 PDF 파일의 북마크를 쉽게 확장할 수 있습니다.
type: docs
weight: 50
url: /ko/net/programming-with-bookmarks/expand-bookmarks/
---
PDF 파일에서 북마크를 확장하면 기본적으로 열려 있는 모든 북마크가 표시됩니다. .NET용 Aspose.PDF를 사용하면 다음 소스 코드에 따라 북마크를 쉽게 확장할 수 있습니다.

## 1단계: 필수 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 import 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 책갈피를 확장하려는 PDF 파일이 포함된 폴더의 경로를 지정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"`다음 코드에 문서 폴더의 실제 경로를 입력하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3단계: PDF 문서 열기

이제 다음 코드를 사용하여 북마크를 확장하려는 PDF 문서를 엽니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 4단계: 페이지 표시 모드 설정

이 단계에서는 기본적으로 북마크를 표시하도록 페이지 표시 모드를 설정합니다. 우리는`PageMode` 의 재산`doc` 원하는 페이지 모드를 설정하는 개체입니다. 해당 코드는 다음과 같습니다.

```csharp
doc.PageMode = PageMode.UseOutlines;
```

## 5단계: 북마크 탐색 및 확장

 이제 문서의 북마크 컬렉션에 있는 각 북마크 항목을 반복하고 각 항목의 열린 상태를 다음으로 설정하겠습니다.`true` 기본적으로 확장합니다. 해당 코드는 다음과 같습니다.

```csharp
foreach(OutlineItemCollection item in doc.Outlines)
{
     item. Open = true;
}
```

## 6단계: 업데이트된 파일 저장

 마지막으로 업데이트된 PDF 파일을 다음을 사용하여 저장합니다.`Save` 의 방법`doc` 물체. 해당 코드는 다음과 같습니다.

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 책갈피 확장을 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document doc = new Document(dataDir + "input.pdf");
// 페이지 보기 모드 설정(예: 썸네일 표시, 전체 화면, 첨부 파일 패널 표시)
doc.PageMode = PageMode.UseOutlines;
// PDF 파일의 개요 컬렉션에서 각 Ouline 항목을 탐색합니다.
foreach (OutlineItemCollection item in doc.Outlines)
{
	// 개요 항목의 미결 상태 설정
	item.Open = true;
}
dataDir = dataDir + "ExpandBookmarks_out.pdf";
// 출력 저장
doc.Save(dataDir);
Console.WriteLine("\nBookmarks expanded successfully.\nFile saved at " + dataDir);
```

## 결론

축하합니다! 이제 Aspose.PDF for .NET을 사용하여 북마크를 개발하는 단계별 가이드가 제공됩니다. 이 코드를 사용하여 PDF 문서의 모든 기본 책갈피를 표시할 수 있습니다.

고급 북마크 조작 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.

### PDF 파일의 북마크 확장에 대한 FAQ

#### Q: PDF 파일의 북마크란 무엇입니까?

A: PDF 파일의 북마크는 사용자가 문서 내의 특정 섹션이나 페이지로 빠르게 이동할 수 있는 탐색 보조 도구입니다. 문서의 다른 부분에 액세스할 수 있는 편리한 방법을 제공합니다.

#### Q: PDF 파일에서 북마크를 확장하려는 이유는 무엇입니까?

A: 북마크를 확장하면 기본적으로 모든 북마크가 확장된 상태로 표시되어 사용자 경험을 향상시킬 수 있습니다. 이를 통해 사용자는 문서 구조에 대한 명확한 개요를 볼 수 있으며 다른 섹션으로 쉽게 이동할 수 있습니다.

#### Q: C# 프로젝트에 필요한 라이브러리를 어떻게 가져오나요?

A: C# 프로젝트에 필요한 라이브러리를 가져오려면 다음 가져오기 지시문을 사용하세요.

```csharp
using Aspose.Pdf;
```

이 지시문을 사용하면 Aspose.PDF for .NET에서 제공하는 클래스와 메서드를 활용할 수 있습니다.

#### Q: 문서 폴더의 경로를 어떻게 지정합니까?

 A: 제공된 소스 코드에서`"YOUR DOCUMENT DIRECTORY"` 작업하려는 PDF 파일이 포함된 폴더의 실제 경로를 사용하세요. 이렇게 하면 코드가 대상 PDF 파일을 찾을 수 있습니다.

#### Q: PDF 문서를 열어 책갈피를 확장하려면 어떻게 해야 합니까?

A: 북마크 확장을 위해 PDF 문서를 열려면 다음 코드를 사용하십시오.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

 바꾸다`"input.pdf"` 실제 파일 이름으로.

#### Q: 기본적으로 북마크를 표시하도록 페이지 표시 모드를 설정하려면 어떻게 해야 합니까?

A: 기본적으로 책갈피를 표시하도록 페이지 표시 모드를 설정하려면`PageMode` 의 재산`doc` 물체:

```csharp
doc.PageMode = PageMode.UseOutlines;
```

#### Q: PDF 문서의 모든 책갈피를 확장하려면 어떻게 해야 합니까?

 A: 모든 북마크를 확장하려면 문서의 개요 컬렉션에 있는 각 북마크 항목을 반복하고`Open` 재산`true`:

```csharp
foreach (OutlineItemCollection item in doc.Outlines)
{
    item.Open = true;
}
```

#### Q: 북마크에 하위 북마크가 중첩되어 있으면 어떻게 되나요?

A: 북마크에 중첩된 하위 북마크가 있는 경우 상위 북마크를 확장하면 하위 북마크도 확장되어 문서 구조에 대한 포괄적인 보기를 제공합니다.

#### Q: 북마크를 확장한 후 업데이트된 PDF 파일을 어떻게 저장합니까?

A: 북마크를 확장한 후 업데이트된 PDF 파일을 저장하려면 다음 코드를 사용하십시오.

```csharp
dataDir = dataDir + "ExpandBookmarks_out.pdf";
doc.Save(dataDir);
```

#### 질문: 확장된 북마크의 모양을 사용자 정의할 수 있나요?

A: 이 튜토리얼은 기본적으로 북마크 확장에 중점을 두고 있지만 Aspose.PDF의 다른 기능과 속성을 사용하여 북마크의 모양을 사용자 정의할 수 있습니다.