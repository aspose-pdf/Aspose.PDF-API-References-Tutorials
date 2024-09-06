---
title: Dot Net Regex로 텍스트 검색
linktitle: Dot Net Regex로 텍스트 검색
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에서 .NET 정규 표현식을 사용하여 텍스트를 검색하는 방법을 알아보세요.
type: docs
weight: 480
url: /ko/net/programming-with-text/search-text-with-dot-net-regex/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 .NET 정규 표현식을 사용하여 텍스트를 검색하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

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

## 4단계: .NET 정규식 개체 만들기

 생성하다`.NET Regex` 검색 패턴을 정의하는 객체:

```csharp
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
```

 바꾸다`@"[\S]+"` 원하는 정규 표현식 패턴을 사용합니다.

## 5단계: PDF 문서 로드

 PDF 문서를 로드하려면 다음을 사용합니다.`Document` 수업:

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
```

 바꾸다`"SearchTextRegex.pdf"` PDF 파일의 실제 이름을 입력하세요.

## 6단계: 특정 페이지 가져오기

원하는 문서 페이지를 가져오세요:

```csharp
Page page = document.Pages[1];
```

 바꾸다`1` 원하는 페이지 번호(1부터 시작하는 인덱스)

## 7단계: TextFragmentAbsorber 만들기

 생성하다`TextFragmentAbsorber` 입력 정규 표현식의 모든 인스턴스를 찾는 객체:

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
```

## 8단계: 페이지에 대한 흡수체 수락

해당 페이지에 대한 흡수체를 수락합니다:

```csharp
page.Accept(textFragmentAbsorber);
```

## 9단계: 추출된 텍스트 조각 검색

다음을 사용하여 추출된 텍스트 조각을 가져옵니다.`TextFragments` 의 속성`TextFragmentAbsorber` 물체:

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 10단계: 텍스트 조각을 반복합니다.

검색된 텍스트 조각을 반복하고 원하는 작업을 수행합니다.

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

필요한 경우 루프 내의 코드를 수정하여 각 텍스트 조각에 대해 추가 작업을 수행합니다.

### .NET용 Aspose.PDF를 사용하여 Dot Net Regex로 텍스트 검색을 위한 샘플 소스 코드 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 모든 단어를 찾기 위해 정규식 객체를 생성합니다.
System.Text.RegularExpressions.Regex regex = new System.Text.RegularExpressions.Regex(@"[\S]+");
// 문서 열기
Aspose.Pdf.Document document = new Aspose.Pdf.Document(dataDir + "SearchTextRegex.pdf");
// 특정 페이지를 가져옵니다
Page page = document.Pages[1];
// 입력 정규식의 모든 인스턴스를 찾기 위해 TextAbsorber 객체를 생성합니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(regex);
textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
// 페이지에 대한 흡수체를 수락합니다
page.Accept(textFragmentAbsorber);
// 추출된 텍스트 조각을 가져옵니다
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
// 조각을 반복합니다
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine(textFragment.Text);
}
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서에서 .NET 정규 표현식을 사용하여 텍스트를 검색하는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 프로젝트 설정부터 추출된 텍스트 조각에 액세스하는 것까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 고급 텍스트 검색을 수행할 수 있습니다.

### 자주 묻는 질문

#### 질문: "Dot Net Regex로 텍스트 검색" 튜토리얼의 목적은 무엇인가요?

A: "Dot Net 정규 표현식으로 텍스트 검색" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 .NET 정규 표현식을 사용하여 PDF 문서 내에서 텍스트를 검색하는 방법을 사용자에게 안내하는 것을 목표로 합니다. 이 튜토리얼은 프로세스를 보여주기 위한 단계별 지침과 C# 코드 샘플을 제공합니다.

#### 질문: 이 튜토리얼은 PDF에서 .NET 정규 표현식을 사용하여 텍스트를 검색하는 데 어떻게 도움이 되나요?

A: 이 튜토리얼은 사용자가 Aspose.PDF for .NET의 기능을 활용하여 PDF 문서 내에서 .NET 정규 표현식을 사용하여 텍스트를 검색하는 방법을 이해하는 데 도움이 됩니다. 제공된 단계와 코드 예제를 따르면 사용자는 지정된 정규 표현식과 일치하는 텍스트 패턴을 효과적으로 검색할 수 있습니다.

#### 질문: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 튜토리얼을 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 Aspose.PDF for .NET 라이브러리를 설치해야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### 질문: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 하나요?

A: 시작하려면 선호하는 통합 개발 환경(IDE)에서 새 C# 프로젝트를 만들고 Aspose.PDF for .NET 라이브러리에 대한 참조를 추가합니다. 이렇게 하면 라이브러리의 기능을 활용하여 PDF 문서를 검색하고 작업할 수 있습니다.

#### 질문: 이 튜토리얼을 사용하면 .NET 정규 표현식을 사용하여 특정 유형의 텍스트를 검색할 수 있나요?

 A: 네, 이 튜토리얼은 PDF 문서 내에서 .NET 정규 표현식을 사용하여 텍스트를 검색하는 방법에 대한 지침을 제공합니다. 사용자 정의할 수 있습니다.`.NET Regex` 사용하고자 하는 구체적인 검색 패턴을 정의하기 위한 객체입니다.

#### 질문: 이 튜토리얼에서 검색할 .NET 정규 표현식 패턴을 어떻게 지정합니까?

 A: 검색하려는 .NET 정규 표현식 패턴을 지정하려면 다음을 만듭니다.`.NET Regex` 객체를 만들고 적절한 정규 표현식 구문을 사용하여 패턴을 설정합니다. 기본값을 바꿉니다.`@"[\S]+"` 튜토리얼의 코드에 원하는 정규 표현식을 추가합니다.

#### 질문: 추출된 텍스트 조각의 속성을 어떻게 검색합니까?

 A: 수락 후`TextFragmentAbsorber` PDF의 특정 페이지에 대해 추출된 텍스트 조각을 다음을 사용하여 검색할 수 있습니다.`TextFragments` 흡수기 객체의 속성입니다. 이는 지정된 .NET 정규 표현식과 일치하는 텍스트 조각 컬렉션에 대한 액세스를 제공합니다.

#### 질문: 추출된 각 텍스트 조각에 대해 추가 작업을 수행하도록 코드를 사용자 정의할 수 있나요?

A: 물론입니다. 튜토리얼의 샘플 코드에는 검색된 텍스트 조각을 반복하는 루프가 포함되어 있습니다. 이 루프 내의 코드를 사용자 지정하여 프로젝트 요구 사항에 따라 추출된 각 텍스트 조각에 대해 추가 작업을 수행할 수 있습니다.

#### 질문: 텍스트 조각을 추출한 후 수정된 PDF 문서를 저장하려면 어떻게 해야 합니까?

A: 이 튜토리얼은 주로 .NET 정규 표현식을 사용하여 텍스트를 검색하고 텍스트 조각을 검색하는 데 중점을 둡니다. PDF를 수정하려는 경우 다른 Aspose.PDF 문서를 참조하여 특정 요구 사항에 따라 문서를 조작하고 저장하는 방법을 알아볼 수 있습니다.