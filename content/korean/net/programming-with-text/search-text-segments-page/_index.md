---
title: PDF 파일의 텍스트 세그먼트 페이지 검색
linktitle: PDF 파일의 텍스트 세그먼트 페이지 검색
second_title: .NET API 참조용 Aspose.PDF
description: PDF 파일의 페이지에서 텍스트 세그먼트를 검색하고 .NET용 Aspose.PDF를 사용하여 해당 속성을 검색하는 방법을 알아보세요.
type: docs
weight: 470
url: /ko/net/programming-with-text/search-text-segments-page/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일 페이지에서 특정 텍스트 세그먼트를 검색하고 해당 속성을 검색하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

## 전제조건

튜토리얼을 진행하기 전에 다음 사항을 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- .NET 라이브러리용 Aspose.PDF가 설치되었습니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

## 1단계: 프로젝트 설정

선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 생성하고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하는 것으로 시작하세요.

## 2단계: 필요한 네임스페이스 가져오기

필수 네임스페이스를 가져오려면 C# 파일 시작 부분에 다음 using 지시문을 추가하세요.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉터리 경로 설정

 다음을 사용하여 문서 디렉토리의 경로를 설정하십시오.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 4단계: PDF 문서 로드

 다음을 사용하여 PDF 문서를 로드합니다.`Document` 수업:

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

 바꾸다`"SearchTextSegmentsPage.pdf"` PDF 파일의 실제 이름으로.

## 5단계: TextFragmentAbsorber 만들기

 만들기`TextFragmentAbsorber` 입력 검색 문구의 모든 인스턴스를 찾는 개체:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

 바꾸다`"text"` 원하는 검색어로

## 6단계: 특정 페이지에 대한 흡수체 수락

문서의 원하는 페이지에 대한 흡수체를 수락합니다.

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

 바꾸다`2` 원하는 페이지 번호(1부터 시작하는 색인)로

## 7단계: 추출된 텍스트 세그먼트 검색

 다음을 사용하여 추출된 텍스트 세그먼트를 가져옵니다.`TextFragments` 의 재산`TextFragmentAbsorber` 물체:

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

필요한 경우 루프 내의 코드를 수정하여 각 텍스트 세그먼트에 대해 추가 작업을 수행합니다.

### .NET용 Aspose.PDF를 사용하는 텍스트 세그먼트 검색 페이지의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
// 입력된 검색 문구의 모든 인스턴스를 찾기 위해 TextAbsorber 개체를 만듭니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
// 모든 페이지에 대한 흡수체를 수락합니다.
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
// 추출된 텍스트 조각 가져오기
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// 조각을 통해 반복
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

축하해요! .NET용 Aspose.PDF를 사용하여 PDF 문서 페이지에서 특정 텍스트 세그먼트를 검색하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 문서 로드부터 추출된 텍스트 세그먼트에 액세스하는 것까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 고급 텍스트 세그먼트 검색을 수행할 수 있습니다.

### FAQ

#### Q: "PDF 파일에서 텍스트 세그먼트 페이지 검색" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일에서 텍스트 세그먼트 페이지 검색" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 활용하여 PDF 문서의 특정 페이지에서 특정 텍스트 세그먼트를 검색하는 방법에 대한 포괄적인 가이드를 제공합니다. 프로젝트 설정, PDF 문서 로드, 텍스트 세그먼트 검색 및 C# 코드를 사용하여 해당 속성 검색 프로세스를 다룹니다.

#### 질문: 이 튜토리얼은 PDF 문서에서 특정 텍스트 세그먼트를 검색하는 데 어떻게 도움이 됩니까?

답변: 이 튜토리얼에서는 PDF 문서의 특정 페이지에서 특정 텍스트 세그먼트를 찾고 추출하는 과정을 보여줍니다. 제공된 단계와 코드 샘플을 따르면 사용자는 원하는 텍스트 세그먼트를 효과적으로 검색하고 해당 속성에 대한 정보를 검색할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 자습서를 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 시작하려면 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. 이를 통해 PDF 문서 검색 및 작업에 라이브러리 기능을 활용할 수 있습니다.

#### 질문: 이 튜토리얼을 사용하여 PDF의 모든 페이지에서 특정 텍스트 세그먼트를 검색할 수 있습니까?

A: 예, 이 튜토리얼은 PDF 문서의 선택한 페이지에서 특정 텍스트 세그먼트를 검색하는 방법에 대한 지침을 제공합니다. 사용자에게 프로젝트 설정, PDF 로드 및 Aspose.PDF 라이브러리를 사용하여 원하는 텍스트 세그먼트의 속성을 찾고 검색하는 방법을 안내합니다.

#### Q: 이 튜토리얼에서 검색하려는 텍스트를 어떻게 지정합니까?

 A: 검색하려는 텍스트를 지정하려면`TextFragmentAbsorber` 개체를 선택하고 다음을 사용하여 검색 매개변수를 설정합니다.`Text` 재산. 기본값 바꾸기`"text"` 원하는 검색 문구를 튜토리얼 코드에 입력하세요.

#### Q: 추출된 텍스트 세그먼트의 속성을 어떻게 검색합니까?

수락한 후`TextFragmentAbsorber` PDF의 특정 페이지에 대해 다음을 사용하여 추출된 텍스트 세그먼트를 검색할 수 있습니다.`TextFragments` 흡수체의 속성. 이를 통해 각 텍스트 조각에는 여러 텍스트 세그먼트가 포함된 텍스트 조각 모음에 대한 액세스가 제공됩니다.

#### Q: 각 텍스트 세그먼트에 추가 작업을 수행하도록 코드를 사용자 정의할 수 있습니까?

답: 물론이죠. 튜토리얼의 샘플 코드는 검색된 텍스트 세그먼트를 반복하는 루프를 제공합니다. 이 루프 내의 코드를 사용자 정의하여 프로젝트 요구 사항에 따라 각 텍스트 세그먼트에 추가 작업을 수행할 수 있습니다.

#### Q: 텍스트 세그먼트를 추출한 후 수정된 PDF 문서를 어떻게 저장합니까?

A: 이 튜토리얼에서는 주로 텍스트 세그먼트를 검색하고 해당 속성을 검색하는 데 중점을 둡니다. PDF를 수정하려는 경우 다른 Aspose.PDF 문서를 참조하여 특정 요구 사항에 따라 문서를 조작하고 저장하는 방법을 알아볼 수 있습니다.