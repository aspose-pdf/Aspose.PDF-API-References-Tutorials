---
title: PDF 파일에서 텍스트 세그먼트 페이지 검색
linktitle: PDF 파일에서 텍스트 세그먼트 페이지 검색
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 자세한 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF 파일에서 텍스트 세그먼트를 검색하는 방법을 알아보세요. 텍스트 추출, 세그먼트 분석 등을 수행하세요.
type: docs
weight: 470
url: /ko/net/programming-with-text/search-text-segments-page/
---
## 소개

Aspose.PDF for .NET을 사용하여 PDF 문서 내에서 특정 텍스트 세그먼트를 찾는 방법을 궁금해하신 적이 있나요? 글쎄요, 운이 좋으시네요! 이 가이드에서는 간단한 단계별 형식으로 프로세스를 안내해 드리겠습니다. 정보를 추출하거나, 텍스트를 분석하거나, PDF 조작의 복잡한 부분을 탐색하든, Aspose.PDF for .NET이 도와드리겠습니다. 시작해 볼까요!

## 필수 조건

시작하기에 앞서, 필요한 모든 것이 있는지 확인해 보겠습니다.

-  .NET용 Aspose.PDF: 라이브러리가 설치되어 있는지 확인하세요. 다음에서 가져올 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
- .NET Framework: 컴퓨터에 .NET이 설치되어 있는지 확인하세요.
- 개발 환경: Visual Studio 또는 .NET을 지원하는 IDE를 권장합니다.
- PDF 문서: 텍스트 세그먼트를 검색할 PDF 파일입니다.

 아직 .NET용 Aspose.PDF가 없다면 걱정하지 마세요! 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/) 또는 구매하세요[여기](https://purchase.aspose.com/buy).

## 패키지 가져오기

코딩을 시작하기 전에 프로젝트에 필요한 패키지를 가져오는 것이 중요합니다. 이렇게 하면 PDF 조작 작업에 필요한 모든 클래스와 메서드를 사용할 수 있습니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

기본적인 사항을 파악했으니, 바로 단계별 가이드로 들어가보겠습니다.


## 1단계: PDF 문서 로드

프로세스의 첫 번째 단계는 PDF 파일을 프로그램에 로드하는 것입니다. 로드된 문서가 없으면 검색할 것이 없지 않나요? 방법은 다음과 같습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

- `dataDir` : 이 변수는 PDF 파일의 경로를 보관합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 파일이 저장된 실제 디렉토리와 동일합니다.
- `pdfDocument` : 사용`Document` 클래스에서 PDF를 메모리에 로드합니다.

## 2단계: 텍스트 검색 설정

 이제 문서가 로드되었으므로 다음 단계는 다음을 만드는 것입니다.`TextFragmentAbsorber` 문서 내에서 특정 텍스트를 검색할 수 있는 객체입니다.

```csharp
// 입력 검색어의 모든 인스턴스를 찾기 위해 TextAbsorber 객체를 생성합니다.
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

- `TextFragmentAbsorber` : 이 객체는 검색하는 텍스트의 모든 발생을 캡처하는 데 사용됩니다. 바꾸기`"text"` 검색하려는 실제 텍스트와 함께 사용합니다.

## 3단계: 특정 페이지에 대한 흡수 장치 수락

항상 PDF 문서 전체를 검색하고 싶지는 않을 수도 있습니다. 이 예에서 우리는 특정 페이지로 범위를 좁힙니다.

```csharp
// 모든 페이지에 대한 흡수체를 수용합니다.
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

- `pdfDocument.Pages[2]`: 이는 문서의 두 번째 페이지만 검색한다는 것을 나타냅니다. 인덱스를 수정하여 다른 페이지를 타겟으로 삼을 수 있습니다.
- `Accept()` : 이 방법을 사용하면`TextFragmentAbsorber` 지정된 페이지 내의 텍스트를 처리합니다.

## 4단계: 텍스트 조각 추출

페이지를 검색한 후, 발견된 텍스트 조각을 컬렉션으로 추출합니다.

```csharp
// 추출된 텍스트 조각을 가져옵니다
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`: 이 컬렉션은 검색 과정에서 발견된 모든 텍스트 조각 인스턴스를 보관합니다.

## 5단계: 텍스트 조각을 반복하고 데이터 추출

이제 각 텍스트 조각을 반복해서 살펴보고 위치, 글꼴, 색상 등의 세부 정보를 추출해 보겠습니다.

```csharp
// 조각을 반복합니다
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

- `foreach (TextFragment textFragment in textFragmentCollection)` : 각각을 반복합니다`TextFragment` 컬렉션에서.
- `foreach (TextSegment textSegment in textFragment.Segments)`: 각 조각 안에는 여러 개의 세그먼트가 있습니다. 우리는 그것들을 반복하여 모든 관련 정보를 수집합니다.
-  다양한 속성`textSegment`이는 텍스트의 위치(X 및 Y), 글꼴 정보, 크기 및 색상 등 텍스트에 대한 자세한 정보를 제공합니다.

## 6단계: 결과 출력

마지막으로 모든 정보를 추출한 후, 결과가 콘솔에 인쇄됩니다. 이를 통해 텍스트의 정확한 위치와 서식 세부 정보를 확인하는 데 도움이 됩니다.

명확성을 위해 샘플 출력을 보여드리겠습니다.

```
Text : text
Position : X: 45.0, Y: 75.0
XIndent : 45.0
YIndent : 75.0
Font - Name : Arial
Font - IsAccessible : True
Font - IsEmbedded : False
Font - IsSubset : False
Font Size : 12.0
Foreground Color : System.Drawing.Color [Black]
```

- 이 출력은 지정된 페이지에 있는 "text" 텍스트의 정확한 위치와 서식 정보를 제공합니다.

## 결론

이제 다 봤습니다! 방금 Aspose.PDF for .NET을 사용하여 PDF 문서 내에서 특정 텍스트 세그먼트를 검색하는 방법을 배웠습니다. 이 프로세스는 대용량 PDF를 처리할 때 매우 편리하여 핵심 텍스트를 효율적으로 정확하게 지정하고 추출할 수 있습니다. 데이터 분석, 정보 추출 또는 단순히 문서 탐색이든 Aspose.PDF는 작업을 완료하는 데 필요한 강력한 도구를 제공합니다.

## 자주 묻는 질문

### 여러 단어나 구문을 검색할 수 있나요?
 네, 수정할 수 있습니다.`TextFragmentAbsorber`입력 문자열을 변경하여 다른 텍스트를 검색합니다.

### 여러 페이지에서 검색이 가능합니까?
 물론입니다! PDF의 모든 페이지를 반복하여 순환할 수 있습니다.`pdfDocument.Pages`.

### 대소문자를 구분하지 않는 텍스트를 검색하려면 어떻게 해야 하나요?
 사용할 수 있습니다`TextSearchOptions` 대소문자를 구분하지 않고 검색을 수행할 수 있습니다.

### 텍스트를 찾은 후에 수정할 수 있나요?
 네, 당신이 찾은 후`TextFragment`, 텍스트 속성을 수정할 수 있습니다.

### 이 방법을 암호화된 PDF에도 적용할 수 있나요?
네, 올바른 비밀번호를 사용하여 PDF 잠금을 해제하면 됩니다.