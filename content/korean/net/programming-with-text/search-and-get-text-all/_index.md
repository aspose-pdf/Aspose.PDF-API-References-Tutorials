---
title: 검색 및 텍스트 모두 가져오기
linktitle: 검색 및 텍스트 모두 가져오기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서의 모든 페이지에서 텍스트를 검색하고 가져오는 방법을 알아보세요.
type: docs
weight: 420
url: /ko/net/programming-with-text/search-and-get-text-all/
---
## 소개

PDF에서 특정 텍스트를 추출해야 했지만 까다로웠던 적이 있나요? PDF는 때때로 잠긴 컨테이너처럼 느껴져 필요한 정보를 얻기 어려울 수 있습니다. 하지만 좋은 소식이 있습니다. Aspose.PDF for .NET을 사용하면 모든 PDF에서 텍스트를 쉽게 검색하고 검색할 수 있습니다. 이 강력한 라이브러리는 .NET 애플리케이션에서 PDF로 작업하는 데 필요한 모든 것을 제공하여 텍스트 추출을 쉽게 해줍니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 텍스트를 검색하고 추출하는 과정을 안내합니다. 텍스트 분석 도구를 빌드하든 PDF 보고서에서 데이터 추출을 자동화해야 하든, 여러분은 올바른 곳에 있습니다!

## 필수 조건

코드로 넘어가기 전에 모든 것이 설정되어 있는지 확인해 보겠습니다.

1. Aspose.PDF for .NET: Aspose.PDF for .NET을 다운로드하여 설치해야 합니다. 다운로드 페이지에서 받을 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
2. .NET 환경: 개발 컴퓨터에 .NET Framework 또는 .NET Core가 설치되어 있는지 확인하세요.
3. 기본 C## 지식: C#에 대한 지식과 .NET 프로젝트 작업에 대한 지식이 권장됩니다.
4.  PDF 문서: 텍스트를 추출할 샘플 PDF 파일입니다. 이 예에서는 다음을 사용합니다.`SearchAndGetTextFromAll.pdf`.

## 패키지 가져오기

코드를 작성하기 전에 Aspose.PDF에서 작업할 수 있도록 필요한 네임스페이스를 프로젝트로 가져와야 합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

이러한 네임스페이스는 PDF의 문서 개체 모델에 대한 액세스를 제공하고 파일 내의 텍스트를 조작할 수 있게 해줍니다.

쉽게 따라할 수 있도록 과정을 간단한 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉토리 설정

먼저, PDF가 있는 디렉토리 경로를 지정해야 합니다. 이렇게 하면 애플리케이션이 텍스트를 추출할 파일을 찾는 데 도움이 됩니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  그만큼`dataDir` 변수는 디렉토리를 가리켜야 합니다.`SearchAndGetTextFromAll.pdf` 파일이 저장되었습니다.
-  바꾸다`"YOUR DOCUMENT DIRECTORY"` 컴퓨터의 실제 경로와 일치합니다.

## 2단계: PDF 문서 열기

다음으로 Aspose.PDF를 사용하여 PDF 문서를 열어보겠습니다.`Document` 물체.

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

-  우리는 새로운 인스턴스를 생성합니다`Document` PDF의 전체 파일 경로를 전달하여 클래스를 만듭니다.
- 이렇게 하면 PDF가 메모리에 로드되어 처리할 수 있는 상태가 됩니다.

## 3단계: 텍스트 흡수기 만들기

 그만큼`TextFragmentAbsorber` object는 PDF 내에서 특정 텍스트를 검색하는 데 사용됩니다. 이 경우, 우리는 "text"라는 단어를 찾을 것입니다.

```csharp
// 입력 검색어의 모든 인스턴스를 찾기 위해 TextAbsorber 객체를 생성합니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

-  그만큼`TextFragmentAbsorber` 문자열로 초기화됩니다`"text"`. 즉, PDF 문서 내에서 "텍스트"라는 단어가 나타나는 곳을 찾습니다.

## 4단계: 모든 페이지에 대한 흡수체 수락

이제 PDF 문서에 흡수체를 적용하고 모든 페이지에서 텍스트를 검색하도록 지시하겠습니다.

```csharp
// 모든 페이지에 대한 흡수체를 수용합니다.
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

-  그만큼`Accept` 방법은 문서의 페이지에 적용됩니다. 이렇게 하면 지정된 텍스트에 대한 모든 페이지를 검색합니다.

## 5단계: 텍스트 조각 추출

흡수체가 문서를 스캔하면 추출된 텍스트 조각을 검색할 수 있습니다.

```csharp
// 추출된 텍스트 조각을 가져옵니다
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

-  그만큼`TextFragments` 의 속성`TextFragmentAbsorber` 검색어와 일치하는 모든 텍스트 조각의 컬렉션을 반환합니다.

## 6단계: 텍스트 조각을 반복합니다.

이제 텍스트 조각 컬렉션이 있으므로 이를 반복하여 세부 정보를 추출하겠습니다.

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

-  그만큼`foreach` 루프는 각각을 반복합니다.`TextFragment` 컬렉션에서.
- 각 조각의 실제 텍스트, 페이지에서의 위치, 글꼴 세부 정보, 글꼴 크기 등 다양한 속성을 인쇄합니다.
-  그만큼`XIndent` 그리고`YIndent` 속성은 PDF 내 텍스트 조각의 정확한 좌표를 제공합니다.

## 결론

이제 다 봤습니다! 몇 줄의 코드만으로 Aspose.PDF for .NET을 사용하여 PDF에서 텍스트를 검색하고 추출했습니다. Aspose.PDF의 유연성 덕분에 다양한 방식으로 PDF를 조작할 수 있어 .NET 환경에서 강력한 PDF 솔루션이 필요한 개발자에게 훌륭한 선택입니다. 이 예제를 쉽게 확장하여 다른 단어를 검색하고, 더 많은 세부 정보를 추출하거나, 필요에 따라 PDF 콘텐츠를 조작할 수도 있습니다. 이 가이드가 PDF 작업에 대한 명확하고 간단한 접근 방식을 제공했기를 바랍니다. 계속해서 여러분의 PDF로 시도해 보세요!

## 자주 묻는 질문

### 한 번에 여러 단어를 검색할 수 있나요?  
 네, 수정할 수 있습니다.`TextFragmentAbsorber` 검색 문자열을 적절히 조정하여 여러 구문을 검색합니다.

### 텍스트가 여러 줄에 걸쳐 있으면 어떻게 되나요?  
Aspose.PDF는 여러 줄에 걸쳐 있어도 텍스트를 인식하고 추출합니다. 이러한 조각을 개별적으로 처리할 수 있습니다.

### 추출된 텍스트를 파일로 저장하려면 어떻게 해야 하나요?  
 표준 C# 파일 I/O 작업(예: )을 사용하여 추출된 텍스트를 파일에 쓸 수 있습니다.`StreamWriter`.

### Aspose.PDF는 스캔한 PDF에서 텍스트를 추출하는 것을 지원하나요?  
Aspose.PDF는 OCR을 지원하지 않습니다. 스캔한 PDF의 경우 텍스트를 인식하려면 OCR 도구가 필요합니다.

### 암호화된 PDF를 어떻게 처리하나요?  
PDF가 암호로 보호되어 있는 경우 Aspose.PDF에서 문서를 로드할 때 암호를 입력하여 잠금을 해제할 수 있습니다.