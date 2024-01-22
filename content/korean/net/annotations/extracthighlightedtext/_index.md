---
title: PDF 파일에서 강조 표시된 텍스트 추출
linktitle: PDF 파일에서 강조 표시된 텍스트 추출
second_title: .NET API 참조용 Aspose.PDF
description: 이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 강조 표시된 텍스트를 추출하는 방법을 알아보세요.
type: docs
weight: 60
url: /ko/net/annotations/extracthighlightedtext/
---
PDF 파일에서 강조 표시된 텍스트를 추출하려면 Aspose.PDF for .NET API를 사용할 수 있습니다. 이 API는 문서에서 강조 표시된 모든 텍스트를 검색하는 간단한 방법을 제공합니다.

## 1단계: PDF 문서 로드

 PDF 파일에서 강조 표시된 텍스트를 추출하는 첫 번째 단계는 .NET API용 Aspose.PDF를 사용하여 문서를 로드하는 것입니다. 이 작업은 새 인스턴스를 생성하여 수행할 수 있습니다.`Document` 클래스를 선택하고 PDF 문서의 경로를 매개변수로 전달합니다. 

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");
```

## 2단계: 모든 주석을 반복합니다.

 다음 단계는 PDF 문서의 모든 주석을 반복하는 것입니다. 다음을 사용하여 이 작업을 수행할 수 있습니다.`foreach` 루프는 다음과 같습니다:

```csharp
foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	// 코드는 여기에 표시됩니다.
}
```

## 3단계: 텍스트 마크업 주석 필터링

 내부`foreach` 루프를 실행하려면 텍스트 마크업 주석이 아닌 모든 주석을 필터링해야 합니다. 주석이 다음의 인스턴스인지 확인하면 됩니다.`TextMarkupAnnotation` 수업.

```csharp
if (annotation is TextMarkupAnnotation)
{
	// 코드는 여기에 표시됩니다.
}
```

## 4단계: 강조 표시된 텍스트 조각 검색

 모든 텍스트 마크업 주석을 필터링한 후에는 각 주석에 대해 강조 표시된 텍스트 조각을 검색할 수 있습니다. 이 작업은`GetMarkedTextFragments()` 에 대한 방법`TextMarkupAnnotation` 물체.

```csharp
TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
```

## 5단계: 강조 표시된 텍스트 표시

 마지막으로 강조 표시된 텍스트를 사용자에게 표시할 수 있습니다. 각 항목을 반복하여 이 작업을 수행할 수 있습니다.`TextFragment` 의 개체`TextFragmentCollection` 그리고 전화를`Text` 재산.

```csharp
foreach (TextFragment tf in collection)
{
	Console.WriteLine(tf.Text);
}
```

### .NET용 Aspose.PDF를 사용하여 강조 표시된 텍스트 추출에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir ="YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ExtractHighlightedText.pdf");

foreach (Annotation annotation in doc.Pages[1].Annotations)
{
	if (annotation is TextMarkupAnnotation)
	{
		TextMarkupAnnotation highlightedAnnotation = annotation as TextMarkupAnnotation;
		TextFragmentCollection collection = highlightedAnnotation.GetMarkedTextFragments();
		foreach (TextFragment tf in collection)
		{
			Console.WriteLine(tf.Text);
		}
	}
}
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 강조 표시된 텍스트를 추출하는 방법을 살펴보았습니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용하여 개발자는 PDF 문서에서 강조 표시된 텍스트를 쉽게 추출하고 관리할 수 있습니다.

### PDF 파일에서 강조 표시된 텍스트 추출에 대한 FAQ

#### Q: PDF 문서의 텍스트 마크업 주석이란 무엇입니까?

답변: 텍스트 마크업 주석은 PDF 문서의 특정 텍스트를 강조하거나 표시하는 주석입니다. 텍스트 마크업 주석의 예로는 강조 표시, 밑줄 및 취소선이 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 다른 유형의 주석에서 텍스트를 추출할 수 있습니까?

A: 예, .NET용 Aspose.PDF는 텍스트 마크업 주석, 자유 텍스트 주석 등을 포함하여 다양한 유형의 주석에서 텍스트를 추출하는 다양한 방법을 제공합니다.

#### Q: .NET용 Aspose.PDF는 비밀번호로 보호된 PDF 파일에서 텍스트 추출을 지원합니까?

 A: 예, .NET용 Aspose.PDF는 비밀번호로 보호된 PDF 파일에서 텍스트 추출을 지원합니다. PDF 문서를 로드할 때 올바른 비밀번호를 제공해야 합니다.`Document` 수업.

#### Q: 색상이나 작성자 등 다른 기준에 따라 강조 표시된 텍스트를 필터링할 수 있습니까?

A: 예, 색상, 작성자 또는 생성 날짜와 같은 다른 기준에 따라 강조 표시된 텍스트를 필터링할 수 있습니다. .NET용 Aspose.PDF는 해당 속성을 기반으로 주석에 액세스하고 필터링하는 방법을 제공합니다.

#### Q: 추출된 하이라이트 텍스트를 별도의 파일로 저장할 수 있나요?

A: 예, 추출된 강조 표시된 텍스트를 별도의 파일에 저장하거나 추가 처리 또는 분석을 위해 데이터 구조에 저장할 수 있습니다.
