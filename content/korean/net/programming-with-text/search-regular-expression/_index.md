---
title: PDF 파일에서 정규식 검색
linktitle: PDF 파일에서 정규식 검색
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 정규식을 사용하여 텍스트를 검색하고 가져오는 방법을 알아보세요.
type: docs
weight: 440
url: /ko/net/programming-with-text/search-regular-expression/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 정규 표현식과 일치하는 텍스트를 검색하고 검색하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

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
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 꼭 교체하세요`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 4단계: 정규식으로 검색

 만들기`TextFragmentAbsorber` 개체를 지정하고 정규식 패턴을 설정하여 패턴과 일치하는 모든 구문을 찾습니다.

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999~2000년처럼
```

 바꾸다`"\\d{4}-\\d{4}"` 원하는 정규식 패턴으로.

## 5단계: 텍스트 검색 옵션 설정

 만들기`TextSearchOptions` 개체를 설정하고`TextSearchOptions` 의 재산`TextFragmentAbsorber` 정규식 사용을 활성화하는 객체:

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## 6단계: 모든 페이지에서 검색

문서의 모든 페이지에 대해 흡수체를 적용합니다.

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 7단계: 추출된 텍스트 조각 검색

다음을 사용하여 추출된 텍스트 조각을 가져옵니다.`TextFragments` 의 재산`TextFragmentAbsorber` 물체:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 8단계: 텍스트 조각 반복

검색된 텍스트 조각을 반복하고 해당 속성에 액세스합니다.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

루프 내의 코드를 수정하여 각 텍스트 조각에 대해 추가 작업을 수행할 수 있습니다.

### .NET용 Aspose.PDF를 사용하여 정규식 검색을 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
// 정규식과 일치하는 모든 구문을 찾기 위해 TextAbsorber 개체를 만듭니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999~2000년처럼
// 정규식 사용을 지정하려면 텍스트 검색 옵션을 설정하세요.
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
// 모든 페이지에 대한 흡수체를 수락합니다.
pdfDocument.Pages.Accept(textFragmentAbsorber);
// 추출된 텍스트 조각 가져오기
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// 조각을 통해 반복
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## 결론

축하해요! .NET용 Aspose.PDF를 사용하여 PDF 문서에서 정규식과 일치하는 텍스트를 검색하고 가져오는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 문서 로드부터 추출된 텍스트 조각에 액세스하는 것까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 고급 텍스트 검색을 수행할 수 있습니다.

### FAQ

#### Q: "PDF 파일에서 정규식 검색" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일에서 정규식 검색" 튜토리얼의 목적은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일 내에서 지정된 정규식 패턴과 일치하는 텍스트를 검색하고 추출하는 방법을 보여주는 것입니다. 이 자습서에서는 프로세스를 보여주기 위한 포괄적인 지침과 샘플 C# 코드를 제공합니다.

#### 질문: 이 튜토리얼은 PDF 문서에서 정규식을 사용하여 텍스트를 검색하는 데 어떻게 도움이 됩니까?

A: 이 튜토리얼에서는 Aspose.PDF 라이브러리를 사용하여 정규식 패턴을 기반으로 PDF 문서에서 텍스트 검색을 수행하는 단계별 접근 방식을 제공합니다. 프로젝트를 설정하고, PDF 문서를 로드하고, 정규식 패턴을 정의하고, 일치하는 텍스트 조각을 검색하는 방법을 자세히 설명합니다.

#### Q: 이 튜토리얼을 따르기 위한 전제 조건은 무엇입니까?

A: 이 자습서를 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 통합할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 시작하려면 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. 이를 통해 프로젝트 내에서 라이브러리의 기능을 활용할 수 있습니다.

#### Q: 정규식을 사용하여 PDF 문서에서 텍스트를 검색할 수 있습니까?

 A: 예, 이 튜토리얼에서는 정규식을 사용하여 PDF 문서에서 텍스트를 검색하고 추출하는 방법을 보여줍니다. 여기에는`TextFragmentAbsorber` 클래스를 지정하고 정규식 패턴을 지정하여 제공된 패턴과 일치하는 구문을 찾습니다.

#### Q: 텍스트 검색을 위한 정규식 패턴을 어떻게 정의합니까?

 A: 텍스트 검색을 위한 정규식 패턴을 정의하려면`TextFragmentAbsorber` 객체를 선택하고 다음을 사용하여 패턴을 설정합니다.`Text` 매개변수. 기본 패턴 바꾸기`"\\d{4}-\\d{4}"` 튜토리얼의 코드에서 원하는 정규식 패턴을 사용하세요.

#### Q: 텍스트 검색에 정규식 사용을 활성화하려면 어떻게 해야 합니까?

 A: 정규식 사용은 다음을 생성하여 활성화됩니다.`TextSearchOptions` 개체를 설정하고 해당 값을 다음으로 설정합니다.`true` . 이 개체를`TextSearchOptions` 의 재산`TextFragmentAbsorber` 사례. 이렇게 하면 텍스트 검색 중에 정규식 패턴이 적용됩니다.

#### Q: 정규식 패턴과 일치하는 텍스트 조각을 검색할 수 있습니까?

 답: 물론이죠. PDF 문서에 정규식 검색을 적용한 후 다음을 사용하여 추출된 텍스트 조각을 검색할 수 있습니다.`TextFragments` 의 재산`TextFragmentAbsorber` 물체. 이러한 텍스트 조각에는 지정된 정규식 패턴과 일치하는 텍스트 세그먼트가 포함되어 있습니다.

#### Q: 검색된 텍스트 조각에서 무엇에 액세스할 수 있나요?

A: 검색된 텍스트 조각에서 일치하는 텍스트 내용, 위치(X 및 Y 좌표), 글꼴 정보(이름, 크기, 색상) 등과 같은 다양한 속성에 액세스할 수 있습니다. 튜토리얼 루프 내의 샘플 코드는 이러한 속성에 액세스하고 표시하는 방법을 보여줍니다.

#### Q: 추출된 텍스트 조각에 대한 작업을 어떻게 사용자 정의할 수 있습니까?

A: 추출된 텍스트 조각이 있으면 루프 내의 코드를 사용자 정의하여 각 텍스트 조각에 추가 작업을 수행할 수 있습니다. 여기에는 추출된 텍스트 저장, 패턴 분석 또는 요구 사항에 따른 서식 변경 구현이 포함될 수 있습니다.