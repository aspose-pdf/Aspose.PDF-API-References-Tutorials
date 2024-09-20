---
title: PDF 파일에서 정규 표현식 검색
linktitle: PDF 파일에서 정규 표현식 검색
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 튜토리얼에서 Aspose.PDF for .NET을 사용하여 PDF 파일에서 정규 표현식을 검색하는 방법을 알아보세요. 정규 표현식으로 생산성을 높이세요.
type: docs
weight: 440
url: /ko/net/programming-with-text/search-regular-expression/
---
## 소개

대용량 PDF 문서를 다룰 때 날짜, 전화번호 또는 기타 구조화된 데이터와 같은 특정 패턴이나 형식을 검색하게 될 수 있습니다. PDF를 수동으로 살펴보는 것은 지루할 수 있죠? 이때 정규 표현식(regex)을 사용하면 편리합니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일 내에서 정규 표현식 패턴을 검색하는 방법을 살펴보겠습니다. 이 가이드에서는 각 단계를 안내하여 .NET 애플리케이션에서 쉽게 구현할 수 있도록 합니다.

## 필수 조건

단계별 튜토리얼을 시작하기에 앞서, 먼저 무엇이 필요한지 살펴보겠습니다.

-  .NET용 Aspose.PDF: 이 라이브러리를 설치해야 합니다. 아직 설치하지 않았다면 다음을 수행할 수 있습니다.[여기서 다운로드하세요](https://releases.aspose.com/pdf/net/).
- IDE: Visual Studio 또는 기타 C# 호환 IDE.
- .NET Framework: 프로젝트가 적절한 버전의 .NET Framework로 설정되었는지 확인하세요.
- C#에 대한 기본 지식: 이 가이드는 자세한 내용을 설명하지만, C#에 대한 기본적인 이해가 도움이 될 것입니다.

### 패키지 가져오기

우선, Aspose.PDF for .NET에서 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이러한 패키지는 PDF 작업과 정규 표현식을 사용하여 검색 작업을 수행하는 데 필수적입니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

Aspose.PDF를 사용하여 PDF 파일에서 정규 표현식을 검색하는 과정을 여러 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉토리 설정

 모든 PDF 작업은 문서가 있는 위치를 지정하는 것으로 시작됩니다. PDF 파일에 대한 경로를 정의해야 합니다. 이 경로는 다음 위치에 저장됩니다.`dataDir` 변하기 쉬운.

### 1.1단계: 문서 경로 정의

```csharp
// PDF 문서 경로를 정의하세요
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 파일에 대한 실제 경로와 함께. 이 단계는 코드를 작업하려는 파일로 가리키기 때문에 중요합니다.

### 1.2단계: PDF 문서 열기

 다음으로, 다음을 사용하여 PDF 문서를 열어야 합니다.`Document` Aspose.PDF의 클래스입니다.

```csharp
// 문서를 엽니다
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

 여기,`"SearchRegularExpressionAll.pdf"` 정규식 검색을 수행할 샘플 PDF 파일입니다.

## 2단계: TextFragmentAbsorber 설정

 마법이 일어나는 곳은 바로 여기입니다!`TextFragmentAbsorber` 클래스는 특정 패턴이나 정규 표현식과 일치하는 텍스트 조각을 캡처하는 데 도움이 됩니다.

정규 표현식을 사용하여 패턴을 찾도록 흡수체를 설정해 보겠습니다. 이 경우, "1999-2000"과 같은 연도 패턴을 검색합니다.

```csharp
// 정규 표현식과 일치하는 모든 구문을 찾기 위해 TextAbsorber 객체를 생성합니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); // 1999-2000년처럼
```

 정규 표현식`\\d{4}-\\d{4}` 4자리 숫자 뒤에 하이픈과 4자리 숫자가 이어지는 패턴을 찾습니다. 이는 연도 범위에서 일반적인 패턴입니다.

## 3단계: 정규 표현식 검색 활성화

 검색 작업에서 패턴을 정규 표현식으로 해석하도록 하려면 다음을 사용하여 검색 옵션을 구성해야 합니다.`TextSearchOptions` 수업.

```csharp
// 정규 표현식 사용을 지정하기 위한 텍스트 검색 옵션 설정
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

 설정하기`TextSearchOptions` 에게`true` 흡수체가 일반 텍스트가 아닌 정규 표현식 기반 검색을 사용하도록 보장합니다.

## 4단계: 텍스트 흡수기 수락

 이 단계에서는 PDF 문서에 텍스트 흡수기를 적용하여 검색 작업을 수행할 수 있습니다. 이는 다음을 호출하여 수행됩니다.`Accept` 방법에 대한`Pages` PDF 문서의 객체.

```csharp
// 모든 페이지에 대한 흡수체 수용
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

이 명령은 PDF의 모든 페이지를 처리하여 정규 표현식과 일치하는 모든 텍스트를 찾습니다.

## 5단계: 결과 추출 및 표시

 검색이 완료되면 결과를 추출해야 합니다.`TextFragmentAbsorber` 이러한 결과를 저장합니다`TextFragmentCollection`이 컬렉션을 반복하여 일치하는 각 텍스트 조각에 액세스하여 표시할 수 있습니다.

### 5.1단계: 추출된 텍스트 조각 검색

```csharp
// 추출된 텍스트 조각을 가져옵니다
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

이제 조각을 수집했으니, 조각을 반복해서 살펴보고 텍스트, 위치, 글꼴 정보 등 관련 세부 정보를 표시할 차례입니다.

### 5.2단계: 조각을 반복합니다.

```csharp
// 조각을 반복합니다
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

 각각에 대하여`TextFragment`, 글꼴 크기, 글꼴 이름, 위치와 같은 세부 정보가 인쇄됩니다. 이는 텍스트를 찾는 데 도움이 될 뿐만 아니라 정확한 서식과 위치도 알려줍니다.

## 결론

이제 알겠습니다! 정규 표현식을 사용하여 PDF 파일에서 패턴을 검색하는 것은 매우 강력하며, 특히 날짜, 전화번호 및 유사한 패턴과 같은 구조화된 텍스트의 경우 더욱 그렇습니다. Aspose.PDF for .NET은 이러한 작업을 쉽게 수행할 수 있는 원활한 방법을 제공합니다. 이제 정규 표현식의 힘을 활용하여 PDF 텍스트 검색을 자동화하여 워크플로를 더욱 효율적으로 만들 수 있습니다.

## 자주 묻는 질문

### 하나의 PDF에서 여러 패턴을 검색할 수 있나요?
 네, 여러 개를 실행할 수 있습니다.`TextFragmentAbsorber` 동일한 PDF에서 각각 다른 정규식 패턴을 가진 객체가 있습니다.

### Aspose.PDF는 대소문자를 구분하지 않는 패턴 검색을 지원합니까?
 물론입니다! 다음을 구성할 수 있습니다.`TextSearchOptions` 대소문자를 구분하지 않고 검색하려면 다음을 사용합니다.

### 검색할 수 있는 PDF 크기에 제한이 있나요?
엄격한 제한은 없지만, PDF 크기와 정규식 패턴의 복잡성에 따라 성능이 달라질 수 있습니다.

### PDF에서 찾은 텍스트를 강조 표시할 수 있나요?
네, Aspose.PDF를 사용하면 흡수체를 사용하여 텍스트를 찾은 후 강조 표시하거나 바꿀 수도 있습니다.

### 패턴을 찾을 수 없을 경우 오류를 어떻게 처리합니까?
 일치하는 항목이 발견되지 않으면`TextFragmentCollection` 비어 있을 것입니다. 결과를 반복하기 전에 간단한 확인으로 이 시나리오를 처리할 수 있습니다.