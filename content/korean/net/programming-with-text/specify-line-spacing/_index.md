---
title: PDF 파일에서 줄 간격 지정
linktitle: PDF 파일에서 줄 간격 지정
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF에서 줄 간격을 지정하는 방법을 알아보세요. 정확한 텍스트 서식을 찾는 개발자에게 완벽합니다.
type: docs
weight: 510
url: /ko/net/programming-with-text/specify-line-spacing/
---
## 소개

PDF 파일에서 줄 간격을 제어하는 데 어려움을 겪은 적이 있습니까? 너무 빽빽하게 뭉쳐 보이거나 원하는 만큼 세련되지 않은 텍스트가 있었을 수도 있습니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF에서 줄 간격을 쉽게 지정하는 방법을 안내합니다. 간단한 단계별 가이드를 사용하여 빈 PDF에서 사용자 지정 줄 간격이 포함된 PDF로 안내합니다. 보고서, 송장 또는 인증서와 같은 문서의 텍스트 레이아웃에 정밀성이 필요한 경우에 적합합니다.

## 필수 조건

코드로 넘어가기 전에 먼저 필요한 모든 것이 있는지 확인해 보겠습니다.

1.  .NET용 Aspose.PDF가 설치되어 있습니다. 설치되어 있지 않으면 다음에서 가져오세요.[Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net/).
2. .NET 개발 환경(Visual Studio와 같음).
3. TrueType 글꼴 파일(`.ttf` ) 예제에서 사용할 것입니다. 어떤 글꼴이든 사용할 수 있지만 이 가이드에서는 다음을 사용합니다.`HPSimplified.TTF` 세례반.
4. C# 및 PDF 조작에 대한 기본 지식.

준비가 되었다면, 필요한 패키지를 가져오는 단계로 넘어가겠습니다.

## 패키지 가져오기

C# 프로젝트에서 PDF 기능을 사용하려면 Aspose.PDF 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using Aspose.Pdf.Text;
using System.IO;
```

이러한 네임스페이스를 사용하면 PDF 문서를 만들고 조작할 수 있고, 텍스트 서식 및 글꼴 옵션을 사용할 수도 있습니다.

이것을 한 입 크기의 단계로 나누어서 쉽게 따라할 수 있도록 하겠습니다. 각 단계는 PDF 설정에서 줄 간격 지정까지 프로세스의 핵심 부분에 초점을 맞춥니다.

## 1단계: 프로젝트 설정 및 문서 디렉토리 정의

우리가 해야 할 첫 번째 일은 파일이 어디에 있는지 정의하는 것입니다. 이렇게 하면 프로그램이 글꼴을 어디에서 찾을지, 결과 PDF를 어디에 저장할지 알 수 있습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string fontFile = dataDir + "HPSimplified.TTF";
```

 이 단계에서는 다음을 교체합니다.`"YOUR DOCUMENT DIRECTORY"` 파일을 저장하는 실제 경로와 함께. 여기에 글꼴 파일을 배치합니다(`HPSimplified.TTF`) 및 PDF가 저장될 위치입니다.

## 2단계: PDF 문서 로드

이제 새 PDF 문서를 만들어야 합니다. 이 가이드에서는 빈 문서로 시작하지만, 필요한 경우 기존 PDF를 로드할 수도 있습니다.

```csharp
Document doc = new Document();
```

이렇게 하면 새로운 빈 PDF 문서가 생성됩니다. 쉽죠?

## 3단계: 텍스트 서식 옵션 설정

 마법이 일어나는 곳은 바로 여기입니다. PDF에 추가하려는 텍스트의 줄 간격 모드를 지정합니다. Aspose.PDF는 여러 옵션을 제공하지만 이 가이드에서는 다음을 사용합니다.`LineSpacingMode.FullSize`이렇게 하면 줄 간격이 완벽하게 준수됩니다.

```csharp
TextFormattingOptions formattingOptions = new TextFormattingOptions();
formattingOptions.LineSpacing = TextFormattingOptions.LineSpacingMode.FullSize;
```

 이 코드는 줄 간격 모드를 설정합니다.`FullSize` , 텍스트가 적절한 간격으로 표시되도록 합니다. 다음과 같은 다른 옵션이 있습니다.`Proportional` 다른 간격 동작을 원하지만 지금은 다음을 고수하겠습니다.`FullSize`.

## 4단계: 텍스트 조각 만들기

이제 PDF에 배치될 실제 텍스트를 만들 것입니다. 이 텍스트는 우리가 정의한 줄 간격을 존중합니다.

```csharp
TextFragment textFragment = new TextFragment("Hello world");
```

 우리는 문자열을 사용하여 텍스트 조각을 생성했습니다.`"Hello world"`물론, 이 텍스트를 원하는 대로 사용자 정의할 수 있습니다.

## 5단계: 사용자 정의 글꼴 로드 및 적용

텍스트를 돋보이게 하기 위해 파일에서 사용자 지정 TrueType 글꼴을 로드합니다. 이 단계는 선택 사항이지만 PDF에 전문적인 터치를 더할 수 있습니다.

```csharp
if (fontFile != "")
{
    using (FileStream fontStream = System.IO.File.OpenRead(fontFile))
    {
        textFragment.TextState.Font = FontRepository.OpenFont(fontStream, FontTypes.TTF);
```

여기서, 우리는 글꼴 파일을 로드하고 그것을 텍스트 조각에 적용합니다. 파일 경로가 유효하면 글꼴이 사용됩니다. 그렇지 않으면 기본 글꼴이 적용됩니다.

## 6단계: 텍스트 위치 및 서식 설정

다음으로, PDF에 텍스트를 배치해야 합니다. 또한 이전에 만든 서식 옵션을 적용합니다.

```csharp
textFragment.Position = new Position(100, 600);
textFragment.TextState.FormattingOptions = formattingOptions;
```

 그만큼`Position` 방법은 텍스트가 페이지에 나타날 좌표를 설정합니다(이 경우 왼쪽에서 100단위, 아래쪽에서 600단위). 줄 간격 모드를 포함한 서식 옵션이 여기에 적용됩니다.

## 7단계: PDF 페이지에 텍스트 추가

이제 텍스트의 서식과 위치가 정해졌으므로 PDF 문서에 추가할 차례입니다.

```csharp
var page = doc.Pages.Add();
page.Paragraphs.Add(textFragment);
```

이 코드는 PDF 문서에 새 페이지를 만들고 텍스트 조각을 추가합니다.

## 8단계: PDF 저장

마지막 단계에 도달했습니다! 이제 모든 것이 설정되었으니 PDF를 저장해 보겠습니다.

```csharp
dataDir = dataDir + "SpecifyLineSpacing_out.pdf";
doc.Save(dataDir);
```

이렇게 하면 지정된 줄 간격으로 PDF가 저장되고 파일이 준비됩니다!

## 결론

그리고 그게 전부입니다! 방금 Aspose.PDF for .NET을 사용하여 사용자 정의 줄 간격이 있는 PDF 문서를 만들었습니다. PDF 파일의 모든 측면을 제어할 수 있는 강력한 도구이며, 이것은 여러분이 달성할 수 있는 것의 한 예일 뿐입니다. 텍스트 배치에서 서식 지정까지 가능성은 무한합니다.

PDF 조작에 대해 더 깊이 파고들고 싶다면 Aspose.PDF는 탐험할 수 있는 풍부한 기능을 제공합니다. 주저하지 말고 실험하고 문서로 할 수 있는 일의 한계를 넓혀보세요!

## 자주 묻는 질문

### 다른 모드에서 줄 간격을 조정할 수 있나요?  
 네, 다음과 같은 다른 모드를 사용할 수 있습니다.`Proportional` 또는`Fixed` 귀하의 요구 사항에 따라 다릅니다.

### 파일 대신 시스템에서 글꼴을 로드하는 것이 가능합니까?  
 예, 다음을 사용하여 시스템에 설치된 글꼴을 로드할 수 있습니다.`FontRepository`.

### Aspose.PDF for .NET을 다른 파일 형식과 함께 사용할 수 있나요?  
물론입니다! Aspose.PDF for .NET은 XML, HTML 등 다양한 형식을 지원합니다.

### Aspose.PDF for .NET을 사용하려면 라이선스가 필요합니까?  
네, 모든 기능을 사용하려면 라이센스가 필요합니다. 라이센스는 다음과 같이 얻을 수 있습니다.[여기](https://purchase.aspose.com/buy).

### 여러 문단의 줄 간격을 어떻게 설정합니까?  
 신청하실 수 있습니다`TextFormattingOptions` 각자에게`TextFragment` 또는`TextParagraph` 여러 줄이나 문단의 간격을 제어합니다.