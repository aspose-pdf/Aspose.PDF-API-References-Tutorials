---
title: PDF 파일에서 텍스트 세그먼트 페이지 검색
linktitle: PDF 파일에서 텍스트 세그먼트 페이지 검색
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 페이지에서 텍스트 세그먼트를 검색하고 해당 속성을 가져오는 방법을 알아보세요.
type: docs
weight: 470
url: /ko/net/programming-with-text/search-text-segments-page/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일 페이지에서 특정 텍스트 세그먼트를 검색하고 해당 속성을 검색하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

## 필수 조건

튜토리얼을 진행하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- .NET 라이브러리용 Aspose.PDF가 설치되었습니다. Aspose 웹사이트에서 얻을 수 있거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

## 1단계: 프로젝트 설정

선호하는 통합 개발 환경(IDE)에서 새 C# 프로젝트를 만들고 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기

필요한 네임스페이스를 가져오려면 C# 파일의 시작 부분에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉토리 경로 설정

 다음을 사용하여 문서 디렉토리 경로를 설정하세요.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

## 4단계: PDF 문서 로드

 PDF 문서를 로드하려면 다음을 사용합니다.`Document` 수업:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 바꾸다`"SearchTextSegmentsPage.pdf"` PDF 파일의 실제 이름을 입력하세요.

## 5단계: TextFragmentAbsorber 만들기

 생성하다`TextFragmentAbsorber` 입력 검색어의 모든 인스턴스를 찾는 객체:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 바꾸다`"text"` 원하는 검색어를 입력하세요.

## 6단계: 특정 페이지에 대한 흡수체 수락

원하는 문서 페이지에 대한 흡수체를 수락하세요.

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 바꾸다`2` 원하는 페이지 번호(1부터 시작하는 인덱스)

## 7단계: 추출된 텍스트 세그먼트 검색

 다음을 사용하여 추출된 텍스트 세그먼트를 가져옵니다.`TextFragments` 의 속성`TextFragmentAbsorber` 물체:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 8단계: 텍스트 세그먼트 반복

검색된 텍스트 세그먼트를 반복하고 해당 속성에 액세스합니다.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

필요한 경우 각 텍스트 세그먼트에서 추가 작업을 수행하도록 루프 내의 코드를 수정합니다.

### .NET용 Aspose.PDF를 사용한 Search Text Segments Page의 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// 입력 검색어의 모든 인스턴스를 찾기 위해 TextAbsorber 객체를 생성합니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// 모든 페이지에 대한 흡수체를 수용합니다.
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// 추출된 텍스트 조각을 가져옵니다
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// 조각을 반복합니다
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지에서 특정 텍스트 세그먼트를 검색하는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 문서 로드부터 추출된 텍스트 세그먼트에 액세스하는 것까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 고급 텍스트 세그먼트 검색을 수행할 수 있습니다.

### 자주 묻는 질문

#### 질문: "PDF 파일에서 텍스트 세그먼트 페이지 검색" 튜토리얼의 목적은 무엇인가요?

A: "PDF 파일에서 텍스트 세그먼트 페이지 검색" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 특정 페이지에서 특정 텍스트 세그먼트를 검색하는 방법에 대한 포괄적인 가이드를 제공합니다. 프로젝트 설정, PDF 문서 로드, 텍스트 세그먼트 검색 및 C# 코드를 사용하여 해당 속성을 검색하는 프로세스를 다룹니다.

#### 질문: 이 튜토리얼은 PDF 문서에서 특정 텍스트 세그먼트를 검색하는 데 어떻게 도움이 되나요?

A: 이 튜토리얼은 PDF 문서의 특정 페이지에서 특정 텍스트 세그먼트를 찾아 추출하는 과정을 보여줍니다. 제공된 단계와 코드 샘플을 따르면 사용자는 원하는 텍스트 세그먼트를 효과적으로 검색하고 해당 속성에 대한 정보를 검색할 수 있습니다.

#### 질문: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 튜토리얼을 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 Aspose.PDF for .NET 라이브러리를 설치해야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### 질문: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 하나요?

A: 시작하려면 선호하는 통합 개발 환경(IDE)에서 새 C# 프로젝트를 만들고 Aspose.PDF for .NET 라이브러리에 대한 참조를 추가합니다. 이렇게 하면 라이브러리의 기능을 활용하여 PDF 문서를 검색하고 작업할 수 있습니다.

#### 질문: 이 튜토리얼을 사용하면 PDF의 모든 페이지에서 특정 텍스트 세그먼트를 검색할 수 있나요?

A: 네, 이 튜토리얼은 PDF 문서의 선택한 페이지에서 특정 텍스트 세그먼트를 검색하는 방법에 대한 지침을 제공합니다. 이 튜토리얼은 사용자에게 프로젝트 설정, PDF 로드, Aspose.PDF 라이브러리를 사용하여 원하는 텍스트 세그먼트의 속성을 찾고 검색하는 방법을 안내합니다.

#### 질문: 이 튜토리얼에서 검색하려는 텍스트를 어떻게 지정합니까?

 A: 검색하려는 텍스트를 지정하려면 다음을 만드십시오.`TextFragmentAbsorber` 객체를 만들고 검색 매개변수를 설정합니다.`Text` 속성. 기본값을 대체합니다.`"text"` 튜토리얼의 코드에 원하는 검색어를 넣으세요.

#### 질문: 추출된 텍스트 세그먼트의 속성을 어떻게 검색합니까?

수락 후`TextFragmentAbsorber` PDF의 특정 페이지에 대해 추출된 텍스트 세그먼트를 다음을 사용하여 검색할 수 있습니다.`TextFragments` 흡수체 객체의 속성입니다. 이는 각각 여러 텍스트 세그먼트를 포함하는 텍스트 조각 모음에 대한 액세스를 제공합니다.

#### 질문: 각 텍스트 세그먼트에서 추가 작업을 수행하도록 코드를 사용자 정의할 수 있나요?

A: 물론입니다. 튜토리얼의 샘플 코드는 검색된 텍스트 세그먼트를 반복하는 루프를 제공합니다. 프로젝트 요구 사항에 따라 이 루프 내의 코드를 사용자 지정하여 각 텍스트 세그먼트에서 추가 작업을 수행할 수 있습니다.

#### 질문: 텍스트 세그먼트를 추출한 후 수정된 PDF 문서를 저장하려면 어떻게 해야 합니까?

A: 이 튜토리얼은 주로 텍스트 세그먼트를 검색하고 해당 속성을 검색하는 데 중점을 둡니다. PDF를 수정하려는 경우 다른 Aspose.PDF 문서를 참조하여 특정 요구 사항에 따라 문서를 조작하고 저장하는 방법을 알아볼 수 있습니다.