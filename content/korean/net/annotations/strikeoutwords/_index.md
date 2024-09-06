---
title: 단어를 삭제하다
linktitle: 단어를 삭제하다
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 포괄적인 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF에서 단어를 취소선으로 표시하는 방법을 알아보세요. 문서 편집 기술을 향상시키세요.
type: docs
weight: 150
url: /ko/net/annotations/strikeoutwords/
---
## 소개

PDF에서 특정 텍스트를 강조하기 위해 취소선을 그어야 했던 적이 있나요? 문서를 검토하든, 텍스트를 마크업하든, 단순히 특정 섹션을 강조해야 하든, 단어를 취소선으로 긋는 것은 귀중한 도구가 될 수 있습니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 바로 그 작업을 하는 방법을 살펴보겠습니다. 이 포괄적인 가이드는 각 단계를 안내하여 .NET 애플리케이션에서 이 기능을 효과적으로 구현하는 데 필요한 모든 정보를 제공합니다. 

## 필수 조건

코드로 들어가기 전에 이 튜토리얼을 따라가려면 꼭 충족해야 할 몇 가지 전제 조건이 있습니다.

1.  Aspose.PDF for .NET 라이브러리: Aspose.PDF for .NET 라이브러리가 설치되어 있는지 확인하세요.[여기서 다운로드하세요](https://releases.aspose.com/pdf/net/).

2. .NET Framework: 컴퓨터에 .NET Framework가 설치되어 있는지 확인하세요. 이 튜토리얼은 .NET 애플리케이션을 위해 설계되었습니다.

3. 개발 환경: 코드를 작성하고 실행하려면 Visual Studio와 같은 IDE가 필요합니다.

4. PDF 문서: 작업할 샘플 PDF 파일을 준비하세요. 이 문서에서 텍스트를 지울 것입니다.

5. 기본 C# 지식: 이 튜토리얼의 단계를 이해하고 구현하려면 C# 프로그래밍에 대한 지식이 필요합니다.

## 패키지 가져오기

코딩을 시작하기 전에 .NET 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. 이렇게 하면 Aspose.PDF를 사용하여 PDF 파일을 조작하는 데 필요한 클래스와 메서드에 액세스할 수 있습니다.

```csharp
using System;
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
```

이러한 네임스페이스는 PDF 문서 작업, 텍스트 처리, 취소선과 같은 주석 추가에 필수적입니다.

이 섹션에서는 PDF 문서에서 단어를 지우는 과정을 간단하고 관리하기 쉬운 단계로 나누어 설명합니다. 각 단계에는 모든 것이 어떻게 작동하는지 이해할 수 있도록 자세한 설명이 함께 제공됩니다.

## 1단계: PDF 문서 로드

첫 번째 단계는 편집하려는 PDF 문서를 로드하는 것입니다. 이 문서는 특정 단어나 구문을 삭제할 문서입니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF 문서를 엽니다
Document document = new Document(dataDir + "input.pdf");
```

- `dataDir` : 이 변수는 문서 디렉토리 경로를 보관합니다.`"YOUR DOCUMENT DIRECTORY"` PDF 파일이 위치한 실제 경로를 포함합니다.
- `Document` : 그`Document` 클래스는 PDF 문서를 나타냅니다. 생성자에 파일 경로를 전달하여 PDF 파일을 열어 처리합니다.

## 2단계: 특정 텍스트를 찾기 위한 TextFragment Absorber 생성

 다음으로 인스턴스를 생성하겠습니다.`TextFragmentAbsorber` PDF 문서에서 특정 텍스트 조각을 검색합니다. 이를 통해 지우고 싶은 텍스트를 찾을 수 있습니다.

```csharp
// 특정 텍스트 조각을 검색하기 위해 TextFragment Absorber 인스턴스를 생성합니다.
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

- `TextFragmentAbsorber`이 클래스는 PDF 문서 내에서 특정 텍스트 조각을 찾고 작업하는 데 사용됩니다. 이 예에서 우리는 "Estoque"라는 단어를 검색하고 있습니다. "Estoque"를 문서에서 찾고자 하는 단어나 구문으로 바꾸세요.

## 3단계: PDF 문서 페이지 반복

 이제 우리는 우리의`TextFragmentAbsorber`, PDF 문서의 각 페이지를 반복해서 검색하여 지정된 텍스트를 찾아야 합니다.

```csharp
// PDF 문서의 페이지를 반복합니다.
for (int i = 1; i <= document.Pages.Count; i++)
{
    // PDF 문서의 현재 페이지를 가져옵니다
    Page page = document.Pages[i];
    page.Accept(textFragmentAbsorber);
}
```

- `for (int i = 1; i <= document.Pages.Count; i++)`: 이 루프는 PDF 문서의 각 페이지를 반복합니다.
- `document.Pages[i]`: 현재 처리 중인 페이지를 검색합니다.
- `page.Accept(textFragmentAbsorber)` : 이 방법은 다음에 적용됩니다.`TextFragmentAbsorber` 현재 페이지로 이동하여 지정된 텍스트를 검색합니다.

## 4단계: 텍스트 조각 수집 및 처리

페이지를 반복한 후, 발견된 텍스트 조각을 수집하여 추가 처리를 위해 준비합니다.

```csharp
// 흡수된 텍스트 조각 모음을 만듭니다.
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

- `TextFragmentCollection`이 컬렉션은 문서에서 발견된 모든 텍스트 조각을 저장합니다. 다음 단계에서 이 컬렉션을 사용하여 텍스트를 취소합니다.

## 5단계: 텍스트 조각을 반복하고 취소합니다.

이 단계에서는 컬렉션의 각 텍스트 조각을 반복하여 취소선 주석을 적용합니다.

```csharp
// 텍스트 조각 컬렉션을 반복합니다.
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

    // TextFragment 객체의 직사각형 크기를 가져옵니다.
    Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
        (float)textFragment.Position.XIndent,
        (float)textFragment.Position.YIndent,
        (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width,
        (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

    // StrikeOut Annotation 인스턴스를 인스턴스화합니다.
    StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);

    // 취소선 주석의 속성 설정
    strikeOut.Opacity = .80f;
    strikeOut.Border = new Border(strikeOut);
    strikeOut.Color = Aspose.Pdf.Color.Red;

    // 텍스트 조각 페이지의 주석 컬렉션에 주석을 추가합니다.
    textFragment.Page.Annotations.Add(strikeOut);
}
```

- `TextFragment textFragment = textFragmentCollection[j]`: 이 줄은 현재 텍스트 조각을 검색합니다.
- `Aspose.Pdf.Rectangle`: 텍스트 조각의 직사각형 크기를 계산하여 취소선을 적용할 위치를 결정합니다.
- `StrikeOutAnnotation`: 이 클래스는 취소선 주석을 나타냅니다. 계산된 사각형과 현재 페이지로 인스턴스화합니다.
- `strikeOut.Opacity`: 이 속성은 취소선의 불투명도를 설정하여 80%가 보이게 만듭니다.
- `strikeOut.Color`우리는 취소선의 색상을 빨간색으로 설정했습니다. 원하는 색상으로 변경할 수 있습니다.
- `textFragment.Page.Annotations.Add(strikeOut)`: 이렇게 하면 페이지에 취소선 주석이 추가됩니다.

## 6단계: 수정된 PDF 문서 저장

마지막 단계는 취소선을 적용하여 수정된 PDF 문서를 저장하는 것입니다.

```csharp
// 업데이트된 PDF 문서를 저장합니다.
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

- `dataDir + "StrikeOutWords_out.pdf"`: 수정된 문서에 대한 새 파일 이름을 만듭니다. 원본 파일은 변경되지 않습니다.
- `document.Save(dataDir)`: 취소선이 포함된 PDF 문서를 지정된 위치에 저장합니다.

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서에서 특정 단어를 성공적으로 취소선으로 표시했습니다. 이 단계별 가이드를 따르면 이제 텍스트를 강조 표시하거나 취소선으로 표시하여 PDF 문서를 사용자 정의하여 더욱 역동적이고 필요에 맞게 만들 수 있습니다. 법률 문서에 주석을 달거나, 보고서를 준비하거나, 검토를 위해 텍스트에 마크업을 하든, 이 튜토리얼은 효율적으로 그렇게 할 수 있는 기술을 제공합니다.

## 자주 묻는 질문

### 취소선의 색깔을 바꿀 수 있나요?

 네, 색상을 수정하여 변경할 수 있습니다.`strikeOut.Color`속성. 예를 들어, 다음과 같이 설정할 수 있습니다.`Aspose.Pdf.Color.Blue` 블루 스트라이크아웃을 위해.

### 한 번에 여러 단어를 취소선으로 칠 수 있나요?

 물론입니다!`TextFragmentAbsorber` 문서에서 모든 단어나 구문을 검색하는 데 사용할 수 있습니다. 여러 인스턴스에 취소선을 적용하려면 다음을 반복합니다.`TextFragmentCollection`.

### 특정 페이지의 텍스트만 취소선으로 표시하고 싶다면 어떻게 해야 하나요?

 페이지를 반복하는 루프를 수정하여 수정하려는 페이지만 포함하도록 할 수 있습니다. 예를 들어,`for (int i = 1; i <= 3; i++)` 첫 세 페이지에만 취소선을 적용합니다.

### 취소선의 두께는 어떻게 조정할 수 있나요?

 취소선의 두께는 다음과 같이 조정 가능합니다.`Border` 의 속성`StrikeOutAnnotation`이를 통해 취소선 모양을 사용자 정의할 수 있습니다.

### 문서를 저장한 후에 취소선을 취소할 방법이 있나요?

문서가 저장되면 취소선은 영구적으로 적용됩니다. 취소선 없이 원본 텍스트를 유지해야 하는 경우 수정 사항을 적용하기 전에 원본 문서의 백업을 저장하는 것을 고려하세요.