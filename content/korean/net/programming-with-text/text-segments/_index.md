---
title: PDF 파일의 텍스트 세그먼트
linktitle: PDF 파일의 텍스트 세그먼트
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF에서 정규식을 사용하여 PDF 파일에서 특정 텍스트 세그먼트를 검색하는 방법을 알아보세요.
type: docs
weight: 540
url: /ko/net/programming-with-text/text-segments/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 특정 텍스트 세그먼트를 검색하는 방법을 설명합니다. 제공된 C# 소스 코드는 정규식을 사용하는 다양한 시나리오를 보여줍니다.

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

## 3단계: 텍스트 검색에 TextFragmentAbsorber 사용

 만들기`TextFragmentAbsorber` 정규식을 사용하여 특정 텍스트 세그먼트를 검색하는 개체:

```csharp
TextFragmentAbsorber textFragmentAbsorber;
```

## 4단계: 정규식을 사용하여 텍스트 검색 수행

정규식을 사용하여 다양한 시나리오에 따라 텍스트 검색을 수행합니다. 다음은 몇 가지 예입니다.

- 정확한 단어 일치를 검색하려면 다음 단계를 따르세요. 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
```

- 대문자 또는 소문자로 된 문자열을 검색하려면 다음을 수행하십시오. 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
```

- PDF 문서 내의 모든 문자열을 검색하려면: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

- 줄 바꿈까지 특정 문자열 뒤의 텍스트를 찾으려면 다음을 수행하십시오. 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
```

- 정규식 일치 다음에 오는 텍스트를 찾으려면 다음을 수행하십시오. 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
```

- PDF 문서 내에서 하이퍼링크/URL을 검색하려면: 

```csharp
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```

정규식을 원하는 검색 패턴으로 바꾸세요.

## 5단계: 검색 수행 및 결과 처리

 생성된 것을 이용하여 검색을 수행합니다.`TextFragmentAbsorber` 귀하의 요구 사항에 따라 결과를 반대하고 처리하십시오.

### .NET용 Aspose.PDF를 사용하는 텍스트 세그먼트의 샘플 소스 코드 
```csharp
TextFragmentAbsorber textFragmentAbsorber;
// 정확히 일치하는 단어를 검색하려면 정규 표현식을 사용하는 것이 좋습니다.
textFragmentAbsorber = new TextFragmentAbsorber(@"\bWord\b", new TextSearchOptions(true));
// 대문자나 소문자로 문자열을 검색하려면 정규식을 사용하는 것이 좋습니다.
textFragmentAbsorber = new TextFragmentAbsorber("(?i)Line", new TextSearchOptions(true));
//PDF 문서 내의 모든 문자열을 검색(모든 문자열 구문 분석)하려면 다음 정규식을 사용해 보십시오.
textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
// 검색 문자열과 일치하는 항목을 찾고 줄 바꿈까지 문자열 뒤의 모든 항목을 가져옵니다.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?i)the ((.)*)");
// 정규 표현식과 일치하는 텍스트를 찾으려면 다음 정규 표현식을 사용하십시오.
textFragmentAbsorber = new TextFragmentAbsorber(@"(?<=word).*");
// PDF 문서 내부의 하이퍼링크/URL을 검색하려면 다음 정규식을 사용해 보십시오.
textFragmentAbsorber = new TextFragmentAbsorber(@"(http|ftp|https):\/\/([\w\-_]+(?:(?:\.[\w\-_]+)+))([\w\-\.,@?^=%&amp;:/~\+#]*[\w\-\@?^=%&amp;/~\+#])?");
```


## 결론

축하해요! .NET용 Aspose.PDF를 사용하여 PDF 문서 내에서 특정 텍스트 세그먼트를 검색하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 정규식을 사용한 다양한 검색 시나리오의 예를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일의 텍스트 세그먼트를 검색하고 처리할 수 있습니다.

### FAQ

#### Q: "PDF 파일의 텍스트 세그먼트" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일의 텍스트 세그먼트" 튜토리얼은 .NET용 Aspose.PDF를 사용하여 PDF 파일 내에서 특정 텍스트 세그먼트를 검색하는 방법을 사용자에게 안내하는 것을 목표로 합니다. 이 자습서에서는 정규식을 사용하여 다양한 시나리오에 따라 텍스트 검색을 수행하기 위한 단계별 지침과 C# 코드 샘플을 제공합니다.

#### 질문: 이 튜토리얼은 PDF 문서에서 텍스트 세그먼트를 검색하는 데 어떻게 도움이 됩니까?

A: 이 튜토리얼은 사용자가 .NET용 Aspose.PDF 라이브러리를 활용하여 PDF 문서 내의 특정 텍스트 세그먼트를 검색하는 방법을 이해하는 데 도움이 됩니다. 다양한 코드 예제와 정규식을 제공함으로써 사용자는 텍스트 검색 쿼리를 사용자 정의하여 PDF 파일 내에서 원하는 콘텐츠를 찾을 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 자습서를 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 시작하려면 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. 이를 통해 PDF 문서 및 텍스트 조각 작업에 라이브러리의 기능을 활용할 수 있습니다.

#### Q: PDF 파일 내에서 특정 텍스트 세그먼트를 검색하려면 어떻게 해야 합니까?

 A: 특정 텍스트 세그먼트를 검색하려면`TextFragmentAbsorber` 물체. 이 튜토리얼에서는 다양한 검색 시나리오를 보여주기 위해 정규식을 사용하는 다양한 코드 예제를 제공합니다. 정규식을 수정하여 원하는 검색 패턴을 정의할 수 있습니다.

#### Q: 튜토리얼에서는 어떤 유형의 검색 시나리오를 다룹니다.

A: 튜토리얼에서는 정확한 단어 일치, 대/소문자를 구분하지 않는 검색, 문서 내의 모든 문자열 검색, 특정 문자열 뒤의 텍스트 찾기, 하이퍼링크/URL 검색 등 정규식을 사용하는 다양한 검색 시나리오를 다룹니다. 제공된 코드 예제는 특정 검색 요구 사항에 맞게 사용자 정의할 수 있습니다.

#### Q: 텍스트 검색을 수행한 후 검색 결과를 어떻게 처리합니까?

 A: 생성한 후`TextFragmentAbsorber`개체를 검색하고 검색을 수행하면 요구 사항에 따라 검색 결과를 처리할 수 있습니다. 튜토리얼은 검색 프로세스 자체를 시연하는 데 중점을 두고 있으며, 검색 결과를 처리하고 활용하는 방법은 프로젝트 요구 사항에 따라 다릅니다.

#### Q: 제공된 코드 예제를 내 프로젝트에 사용할 수 있습니까?

A: 예, 제공된 코드 예제를 자신의 C# 프로젝트에서 참조로 사용할 수 있습니다. 예제에서는 검색을 설정하고, 정규식을 정의하고, 텍스트 검색을 수행하는 방법을 보여줍니다. 이 코드를 응용 프로그램에 적용하고 통합하여 PDF 파일 내의 특정 텍스트 세그먼트를 검색할 수 있습니다.

#### Q: 샘플 코드와 함께 전체 튜토리얼을 어디에서 찾을 수 있습니까?

 A: 다음 링크를 방문하면 전체 자습서에 액세스하고 제공된 샘플 C# 코드를 볼 수 있습니다.[https://bit.ly/TextSegmentsTutorial](https://bit.ly/TextSegmentsTutorial)