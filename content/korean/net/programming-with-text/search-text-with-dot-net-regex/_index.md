---
title: Dot Net Regex로 텍스트 검색
linktitle: Dot Net Regex로 텍스트 검색
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 .NET 정규식을 사용하여 텍스트를 검색하는 방법을 알아보세요.
type: docs
weight: 480
url: /ko/net/programming-with-text/search-text-with-dot-net-regex/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 .NET 정규식을 사용하여 텍스트를 검색하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

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

## 4단계: .NET Regex 개체 만들기

 만들기`.NET Regex` 검색 패턴을 정의하는 객체:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 바꾸다`@"[\S]+"` 원하는 정규식 패턴으로.

## 5단계: PDF 문서 로드

 다음을 사용하여 PDF 문서를 로드합니다.`Document` 수업:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 바꾸다`"SearchTextRegex.pdf"` PDF 파일의 실제 이름으로.

## 6단계: 특정 페이지 가져오기

문서의 원하는 페이지를 가져옵니다.

```csharp
Page page = document.Pages[1];
```

 바꾸다`1` 원하는 페이지 번호(1부터 시작하는 색인)로

## 7단계: TextFragmentAbsorber 만들기

 만들기`TextFragmentAbsorber` 입력 정규식의 모든 인스턴스를 찾는 개체:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## 8단계: 페이지에 대한 흡수체 수락

페이지의 흡수체를 수락합니다.

```csharp
page.Accept(textFragmentAbsorber);
```

## 9단계: 추출된 텍스트 조각 검색

다음을 사용하여 추출된 텍스트 조각을 가져옵니다.`TextFragments` 의 재산`TextFragmentAbsorber` 물체:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 10단계: 텍스트 조각 반복

검색된 텍스트 조각을 반복하고 원하는 작업을 수행합니다.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

필요한 경우 루프 내의 코드를 수정하여 각 텍스트 조각에 추가 작업을 수행합니다.

### .NET용 Aspose.PDF를 사용하여 Dot Net Regex로 텍스트 검색을 위한 샘플 소스 코드 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 모든 단어를 찾으려면 Regex 개체를 만드세요.
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// 문서 열기
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// 특정 페이지 가져오기
Page page = document.Pages[1];
// 입력 정규식의 모든 인스턴스를 찾기 위해 TextAbsorber 개체를 만듭니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// 페이지의 흡수체를 수락합니다.
page.Accept(textFragmentAbsorber);
// 추출된 텍스트 조각 가져오기
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// 조각을 통해 반복
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## 결론

축하해요! .NET용 Aspose.PDF를 사용하여 PDF 문서에서 .NET 정규식을 사용하여 텍스트를 검색하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 프로젝트 설정부터 추출된 텍스트 조각에 액세스하는 것까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 고급 텍스트 검색을 수행할 수 있습니다.

### FAQ

#### Q: "Dot Net Regex를 사용하여 텍스트 검색" 튜토리얼의 목적은 무엇입니까?

A: "Dot Net Regex로 텍스트 검색" 튜토리얼의 목적은 .NET 정규식을 사용하여 PDF 문서 내에서 텍스트를 검색하기 위해 .NET용 Aspose.PDF 라이브러리를 사용하는 방법을 사용자에게 안내하는 것입니다. 이 자습서에서는 프로세스를 보여주기 위한 단계별 지침과 C# 코드 샘플을 제공합니다.

#### Q: PDF에서 .NET 정규식을 사용하여 텍스트를 검색하는 데 이 튜토리얼이 어떻게 도움이 됩니까?

A: 이 튜토리얼은 사용자가 .NET용 Aspose.PDF의 기능을 활용하여 PDF 문서 내에서 .NET 정규식을 사용하여 텍스트를 검색하는 방법을 이해하는 데 도움이 됩니다. 제공된 단계와 코드 예제를 따르면 사용자는 지정된 정규식과 일치하는 텍스트 패턴을 효과적으로 검색할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 자습서를 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 시작하려면 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. 이를 통해 PDF 문서 검색 및 작업에 라이브러리 기능을 활용할 수 있습니다.

#### Q: 이 자습서를 사용하여 .NET 정규식을 사용하여 특정 유형의 텍스트를 검색할 수 있습니까?

 A: 예, 이 튜토리얼에서는 PDF 문서 내에서 .NET 정규식을 사용하여 텍스트를 검색하는 방법에 대한 지침을 제공합니다. 당신은`.NET Regex` 사용하려는 특정 검색 패턴을 정의하는 개체입니다.

#### Q: 이 자습서에서 검색할 .NET 정규식 패턴을 지정하려면 어떻게 해야 합니까?

 A: 검색하려는 .NET 정규식 패턴을 지정하려면`.NET Regex` 적절한 정규식 구문을 사용하여 개체의 패턴을 설정합니다. 기본값 바꾸기`@"[\S]+"` 원하는 정규 표현식을 사용하여 튜토리얼 코드에 추가하세요.

#### Q: 추출된 텍스트 조각의 속성을 어떻게 검색합니까?

 A: 수락한 후`TextFragmentAbsorber` PDF의 특정 페이지에 대해 다음을 사용하여 추출된 텍스트 조각을 검색할 수 있습니다.`TextFragments` 흡수체의 속성. 이는 지정된 .NET 정규식과 일치하는 텍스트 조각 컬렉션에 대한 액세스를 제공합니다.

#### Q: 추출된 각 텍스트 조각에 대해 추가 작업을 수행하도록 코드를 사용자 정의할 수 있습니까?

답: 물론이죠. 튜토리얼의 샘플 코드에는 검색된 텍스트 조각을 반복하는 루프가 포함되어 있습니다. 이 루프 내의 코드를 사용자 정의하여 프로젝트 요구 사항에 따라 추출된 각 텍스트 조각에 추가 작업을 수행할 수 있습니다.

#### Q: 텍스트 조각을 추출한 후 수정된 PDF 문서를 어떻게 저장합니까?

A: 이 자습서에서는 주로 .NET 정규식을 사용하여 텍스트를 검색하고 텍스트 조각을 검색하는 데 중점을 둡니다. PDF를 수정하려는 경우 다른 Aspose.PDF 문서를 참조하여 특정 요구 사항에 따라 문서를 조작하고 저장하는 방법을 알아볼 수 있습니다.