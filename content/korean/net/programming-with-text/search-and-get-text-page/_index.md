---
title: PDF 파일에서 텍스트 페이지 검색 및 가져오기
linktitle: PDF 파일에서 텍스트 페이지 검색 및 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 특정 페이지에서 텍스트를 검색하고 가져오는 방법을 알아보세요.
type: docs
weight: 430
url: /ko/net/programming-with-text/search-and-get-text-page/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 특정 페이지에서 텍스트를 검색하고 가져오는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

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

## 3단계: PDF 문서 로드

 PDF 문서 디렉토리의 경로를 설정하고 다음을 사용하여 문서를 로드합니다.`Document` 수업:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
```

 꼭 교체하세요`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 4단계: 페이지에서 텍스트 검색 및 추출

 만들기`TextFragmentAbsorber`특정 페이지에서 입력 검색 문구의 모든 인스턴스를 찾는 개체:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
```

 바꾸다`"Figure"` 검색하려는 실제 텍스트를 사용하세요.

## 5단계: 특정 페이지에서 검색

문서의 특정 페이지에 대한 흡수체를 수락합니다.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 6단계: 추출된 텍스트 조각 가져오기

다음을 사용하여 추출된 텍스트 조각을 가져옵니다.`TextFragments` 의 재산`TextFragmentAbsorber` 물체:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 7단계: 텍스트 조각과 세그먼트를 반복합니다.

가져온 텍스트 조각과 해당 세그먼트를 반복하고 해당 속성에 액세스합니다.

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

루프 내의 코드를 수정하여 각 텍스트 세그먼트에 대해 추가 작업을 수행할 수 있습니다.

### .NET용 Aspose.PDF를 사용하여 검색 및 텍스트 가져오기 페이지의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "SearchAndGetTextPage.pdf");
// 입력된 검색 문구의 모든 인스턴스를 찾기 위해 TextAbsorber 개체를 만듭니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("Figure");
// 모든 페이지에 대한 흡수체를 수락합니다.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// 추출된 텍스트 조각 가져오기
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// 조각을 통해 반복
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

## 결론

축하해요! .NET용 Aspose.PDF를 사용하여 PDF 문서의 특정 페이지에서 텍스트를 검색하고 가져오는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 문서 로드부터 추출된 텍스트 세그먼트에 액세스하는 것까지 단계별 가이드를 제공했습니다. 이제 통합할 수 있습니다.

### FAQ

#### Q: "텍스트 페이지 검색 및 가져오기" 튜토리얼의 목적은 무엇입니까?

A: "텍스트 페이지 검색 및 가져오기" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일 내의 특정 페이지에서 텍스트를 검색하고 가져오는 방법을 설명하기 위해 설계되었습니다. 자습서에서는 프로세스를 보여주기 위한 자세한 지침과 샘플 C# 코드를 제공합니다.

#### Q: 이 튜토리얼은 PDF 문서의 특정 페이지에서 텍스트를 추출하는 데 어떻게 도움이 됩니까?

A: 이 튜토리얼은 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 특정 페이지에서 텍스트를 추출하는 과정을 안내합니다. 필요한 단계를 간략하게 설명하고 선택한 페이지에서 지정된 텍스트 구문을 검색하고 연결된 텍스트 세그먼트를 검색하는 C# 코드를 제공합니다.

#### Q: 이 튜토리얼을 따르기 위한 전제 조건은 무엇입니까?

A: 이 자습서를 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 통합할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 시작하려면 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. 이를 통해 프로젝트에서 라이브러리의 기능을 활용할 수 있습니다.

#### Q: PDF 문서의 특정 페이지에 있는 텍스트를 검색할 수 있나요?

A: 예, 이 튜토리얼에서는 PDF 문서의 특정 페이지에서 텍스트를 검색하는 방법을 보여줍니다. 여기에는`TextFragmentAbsorber` 선택한 페이지에서 특정 텍스트 문구의 인스턴스를 찾는 클래스입니다.

#### Q: 특정 페이지에서 추출된 텍스트 세그먼트에 어떻게 액세스합니까?

 A: 지정된 페이지에서 텍스트를 검색한 후 추출된 텍스트 세그먼트에 접근할 수 있습니다.`TextSegments` 의 재산`TextFragment` 물체. 이 속성은 다음 컬렉션에 대한 액세스를 제공합니다.`TextSegment` 추출된 텍스트와 관련 정보가 포함된 개체입니다.

#### Q: 추출된 텍스트 세그먼트에서 어떤 정보를 검색할 수 있나요?

A: 텍스트 내용, 위치(X 및 Y 좌표), 글꼴 정보(이름, 크기, 색상 등) 등을 포함하여 추출된 텍스트 세그먼트에서 다양한 세부 정보를 검색할 수 있습니다. 튜토리얼의 샘플 코드는 각 텍스트 세그먼트에 대한 이러한 세부 정보에 액세스하고 인쇄하는 방법을 보여줍니다.

#### Q: 추출된 텍스트 세그먼트에 대해 사용자 지정 작업을 수행할 수 있습니까?

답: 물론이죠. 추출된 텍스트 세그먼트가 있으면 루프 내의 코드를 사용자 정의하여 각 세그먼트에 대해 추가 작업을 수행할 수 있습니다. 여기에는 추출된 텍스트 저장, 텍스트 패턴 분석 또는 서식 변경 적용이 포함될 수 있습니다.