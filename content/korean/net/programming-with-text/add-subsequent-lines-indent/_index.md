---
title: PDF 파일에 후속 줄 들여쓰기 추가
linktitle: PDF 파일에 후속 줄 들여쓰기 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 후속 줄 들여쓰기를 추가하는 방법을 알아보세요. 전문적인 텍스트 서식 지정을 위한 이 자세한 단계별 가이드를 따르세요.
type: docs
weight: 60
url: /ko/net/programming-with-text/add-subsequent-lines-indent/
---
## 소개

시각적으로 매력적인 PDF를 만드는 데는 종종 페이지에 텍스트를 배치하는 것 이상이 포함됩니다. PDF 문서 내에서 후속 줄에 들여쓰기를 추가하여 보다 전문적으로 보이게 하는 방법에 대해 생각해 본 적이 있습니까? 보고서, 전자책 또는 레이아웃이 중요한 문서를 작성하든 텍스트 흐름을 제어하는 것이 중요합니다. 오늘은 Aspose.PDF for .NET을 사용하여 PDF 파일에 후속 줄 들여쓰기를 추가하는 방법을 살펴보겠습니다. 이 기능은 특히 가독성과 미학을 개선하는 들여쓰기가 필요한 문단에 유용할 수 있습니다. 그럼 바로 시작해 볼까요!

## 필수 조건

시작하기 전에 몇 가지 준비해야 할 사항이 있습니다.

-  .NET용 Aspose.PDF: 이 라이브러리를 설치해야 합니다. 아직 설치하지 않았다면 다음을 수행할 수 있습니다.[여기서 다운로드하세요](https://releases.aspose.com/pdf/net/).
- 개발 환경: C# 및 Visual Studio와 같은 IDE에 대한 기본 지식이 있으면 좋습니다.
- .NET Framework: 이 튜토리얼에서는 사용자가 .NET 환경에서 작업하고 있다고 가정합니다.
-  임시 라이센스: Aspose.PDF에 대한 전체 라이센스가 없는 경우 다음을 요청할 수 있습니다.[임시 면허](https://purchase.aspose.com/temporary-license/).

이제 준비가 되었으니 코딩 섹션으로 넘어가보죠!

## 네임스페이스 가져오기

우선, Aspose.PDF 라이브러리를 프로젝트에서 사용할 수 있도록 필요한 네임스페이스를 가져와야 합니다. 간단한 단계이지만 작업을 진행하는 데 필수적입니다.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이러한 파일을 가져오면 Aspose.PDF가 제공하는 강력한 도구를 사용하여 작업할 준비가 된 것입니다.

## 1단계: 문서 및 페이지 설정

들여쓰기를 추가하기 전에 새 PDF 문서를 만들고 페이지를 추가해야 합니다. 이것은 우리가 텍스트 서식을 적용할 캔버스가 될 것입니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 새 문서 객체 생성
Aspose.Pdf.Document document = new Aspose.Pdf.Document();

//문서에 새 페이지 추가
Aspose.Pdf.Page page = document.Pages.Add();
```

여기서 PDF 문서를 초기화하고 빈 페이지를 추가합니다. 지금까지는 꽤 간단하죠? 콘텐츠를 추가하기 전에 무대를 설정하는 것으로 생각하세요.

## 2단계: 텍스트 조각 만들기

 다음으로, 다음을 생성해야 합니다.`TextFragment` PDF에 표시할 텍스트를 보관할 개체입니다. 이 텍스트는 나중에 필요한 들여쓰기로 서식이 지정됩니다.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment(
    "A quick brown fox jumped over the lazy dog. " +
    "A quick brown fox jumped over the lazy dog. " +
    "A quick brown fox jumped over the lazy dog. " +
    "A quick brown fox jumped over the lazy dog. " +
    "A quick brown fox jumped over the lazy dog."
);
```

이것은 페이지의 공간을 채우기 위해 여러 번 반복된 간단한 예시 텍스트일 뿐입니다. 이것을 프로젝트와 관련된 모든 텍스트로 바꿀 수 있습니다.

## 3단계: 텍스트 서식 옵션 초기화

 마법이 일어나는 곳은 바로 여기입니다! 이제 당신은 당신의`TextFragment` , 텍스트 서식 옵션을 초기화하여 지정해야 합니다.`SubsequentLinesIndent`이 설정은 첫 번째 줄을 제외한 모든 줄에 들여쓰기를 적용합니다.

```csharp
// 텍스트 조각에 대한 TextFormattingOptions를 초기화하고 subsequentlyLinesIndent 값을 지정합니다.
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

이 예에서 들여쓰기를 20단위로 설정했습니다. 즉, 첫 번째 줄 이후의 모든 줄이 20단위로 들여쓰기되어 시각적으로 뚜렷한 매달린 들여쓰기가 생성됩니다.

## 4단계: 페이지에 텍스트 추가

 이제 필요한 서식을 적용했으므로 페이지에 텍스트를 추가할 차례입니다. 이는 다음을 추가하여 수행됩니다.`TextFragment` 해당 페이지의 문단 모음에.

```csharp
page.Paragraphs.Add(text);
```

이 시점에서 페이지에는 들여쓰기가 된 후속 줄이 있는 텍스트가 있습니다. 하지만 왜 거기서 멈추나요? 문서를 더 완벽하게 느끼게 하기 위해 줄을 더 추가해 보겠습니다.

## 5단계: 추가 텍스트 조각 추가

여러 텍스트 조각이 동일한 문서에 어떻게 나타날 수 있는지 보여주기 위해 몇 줄을 더 추가할 수 있습니다. 이러한 각 줄은 독립적으로 서식을 지정하거나 이전 단계와 동일한 서식을 사용할 수 있습니다.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);

text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);

text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);

text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

페이지에 새로운 텍스트 조각을 추가할 때마다 문서가 형태를 갖추기 시작합니다. 긴 문서나 짧은 형식의 콘텐츠를 작성하든 다양한 시나리오에서 이것을 어떻게 사용할 수 있을지 쉽게 상상할 수 있습니다.

## 6단계: 문서 저장

모든 텍스트를 추가하고 원하는 서식을 적용했으면 이제 문서를 저장할 차례입니다. 다음 코드 줄은 바로 그렇게 하여 지정된 디렉토리에 파일을 저장합니다.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

그게 다입니다! 이제 PDF 파일에는 후속 줄이 들여쓰기된 텍스트가 들어 있습니다.

## 결론

이제 다 봤습니다! 방금 Aspose.PDF for .NET을 사용하여 PDF에 후속 줄 들여쓰기를 추가하는 방법을 배웠습니다. 이 방법은 문서에 전문적인 터치를 더하고 텍스트가 표시되는 방식을 제어할 수 있는 유연성을 제공하는 데 적합합니다. 비즈니스 보고서, 법률 문서 또는 거의 모든 유형의 PDF 파일을 준비하든 들여쓰기는 가독성을 향상시키는 작지만 강력한 도구입니다. 이 튜토리얼이 마음에 들었다면 Aspose.PDF가 제공하는 다른 기능을 살펴보는 건 어떨까요?

## 자주 묻는 질문

### 문단마다 다른 들여쓰기를 적용할 수 있나요?  
 네, 각각 다른 들여쓰기 설정을 적용할 수 있습니다.`TextFragment` 각자의 개성을 수정하여`TextState.FormattingOptions`.

###  어떤 단위가 사용됩니까?`SubsequentLinesIndent` property?  
들여쓰기는 포인트로 측정되며, 이는 PDF 문서의 표준 측정 단위입니다.

### 이미 있는 PDF에도 적용할 수 있나요?  
물론입니다! 기존 PDF를 로드하고 새 문서와 같은 방식으로 이러한 변경 사항을 적용할 수 있습니다.

### 이후 줄의 들여쓰기에 제한이 있나요?  
명확한 제한은 없지만, 가독성을 위해 들여쓰기를 적당한 한도 내에서 유지하는 것이 좋습니다.

### 다른 텍스트 서식 옵션과 결합할 수 있나요?  
 네! 결합할 수 있습니다`SubsequentLinesIndent` 글꼴 크기, 색상, 정렬 등의 다른 텍스트 서식 옵션을 사용하여 텍스트를 더욱 세부적으로 사용자 지정할 수 있습니다.