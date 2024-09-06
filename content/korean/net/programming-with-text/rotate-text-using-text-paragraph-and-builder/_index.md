---
title: PDF 파일에서 텍스트 단락 및 빌더를 사용하여 텍스트 회전
linktitle: PDF 파일에서 텍스트 단락 및 빌더를 사용하여 텍스트 회전
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 텍스트 문단과 빌더를 사용하여 텍스트를 회전하는 방법을 알아보세요.
type: docs
weight: 410
url: /ko/net/programming-with-text/rotate-text-using-text-paragraph-and-builder/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일에서 텍스트 단락과 빌더를 사용하여 텍스트를 회전하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

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
using Aspose.Pdf.Text.TextBuilder;
```

## 3단계: PDF 문서 만들기

 초기화`Document` 새 PDF 문서를 만드는 객체:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document();
```

 교체를 꼭 해주세요`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

## 4단계: 페이지 추가

 문서에서 특정 페이지를 가져오려면 다음을 사용합니다.`Pages.Add()` 방법:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 5단계: 텍스트 단락 만들기 및 회전

 생성하다`for` 다양한 회전을 사용하여 여러 텍스트 문단을 생성하는 루프:

```csharp
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	paragraph.Rotation = i * 90 + 45;
```

요구 사항에 맞게 위치 및 회전 값을 조정하세요.

## 6단계: 텍스트 조각 만들기 및 구성

 여러개 생성`TextFragment` 객체, 텍스트 및 속성 설정:

```csharp
TextFragment textFragment1 = new TextFragment("Paragraph Text");
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment2 = new TextFragment("Second line of text");
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;

TextFragment textFragment3 = new TextFragment("And some more text...");
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
textFragment3.TextState.Underline = true;
```

원하는 대로 텍스트와 다른 속성을 조정합니다.

## 7단계: 문단에 텍스트 조각 추가

 생성된 텍스트 조각을 다음을 사용하여 문단에 추가합니다.`AppendLine` 방법:

```csharp
paragraph.AppendLine(textFragment1);
paragraph.AppendLine(textFragment2);
paragraph.AppendLine(textFragment3);
```

## 8단계: TextBuilder를 생성하고 문단을 추가합니다.

 생성하다`TextBuilder` 객체를 사용하여`pdfPage` 그리고 PDF 페이지에 텍스트 문단을 추가합니다.

```csharp
TextBuilder textBuilder = new TextBuilder(pdfPage);
textBuilder.AppendParagraph(paragraph);
}
```

## 9단계: PDF 문서 저장

 수정된 PDF 문서를 파일로 저장하려면 다음을 사용합니다.`Save` 방법:

```csharp
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

 교체를 꼭 해주세요`"TextFragmentTests_Rotated4_out.pdf"` 원하는 출력 파일 이름을 입력합니다.

### .NET용 Aspose.PDF를 사용하여 텍스트 단락 및 빌더를 사용하여 텍스트 회전을 위한 샘플 소스 코드 
```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 객체 초기화
Document pdfDocument = new Document();
// 특정 페이지 가져오기
Page pdfPage = (Page)pdfDocument.Pages.Add();
for (int i = 0; i < 4; i++)
{
	TextParagraph paragraph = new TextParagraph();
	paragraph.Position = new Position(200, 600);
	// 회전 지정
	paragraph.Rotation = i * 90 + 45;
	// 텍스트 조각 만들기
	TextFragment textFragment1 = new TextFragment("Paragraph Text");
	// 텍스트 조각 만들기
	textFragment1.TextState.FontSize = 12;
	textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment1.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment1.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// 텍스트 조각 만들기
	TextFragment textFragment2 = new TextFragment("Second line of text");
	// 텍스트 속성 설정
	textFragment2.TextState.FontSize = 12;
	textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment2.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment2.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	// 텍스트 조각 만들기
	TextFragment textFragment3 = new TextFragment("And some more text...");
	// 텍스트 속성 설정
	textFragment3.TextState.FontSize = 12;
	textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
	textFragment3.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
	textFragment3.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	textFragment3.TextState.Underline = true;
	paragraph.AppendLine(textFragment1);
	paragraph.AppendLine(textFragment2);
	paragraph.AppendLine(textFragment3);
	// TextBuilder 객체를 생성합니다
	TextBuilder textBuilder = new TextBuilder(pdfPage);
	// PDF 페이지에 텍스트 조각 추가
	textBuilder.AppendParagraph(paragraph);
}
// 문서 저장
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated4_out.pdf");
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서에서 텍스트 단락과 빌더를 사용하여 텍스트를 회전하는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 문서 생성부터 수정된 버전 저장까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일에서 텍스트 회전을 조작할 수 있습니다.

### 자주 묻는 질문

#### 질문: "텍스트 문단과 빌더를 사용하여 텍스트 회전" 튜토리얼의 목적은 무엇입니까?

A: "텍스트 단락 및 빌더를 사용하여 텍스트 회전" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내에서 텍스트 단락 및 빌더를 사용하여 텍스트를 회전하는 방법에 대한 포괄적인 가이드를 제공합니다. 이 튜토리얼은 단계별 지침을 보여주고 단락 및 사용자 지정 서식을 사용하여 텍스트 회전을 달성하기 위한 샘플 C# 코드를 포함합니다.

#### 질문: 이 튜토리얼은 이전 텍스트 회전 튜토리얼과 어떻게 다릅니까?

A: 이전 튜토리얼과 달리 이 튜토리얼은 텍스트 문단, 빌더, 회전 각도를 결합하여 더욱 진보된 텍스트 회전 효과를 구현합니다. 다양한 회전 각도로 여러 텍스트 문단을 생성하고 개별 텍스트 조각에 사용자 지정 서식을 적용하는 방법을 보여줍니다.

#### 질문: 텍스트 회전을 위해 텍스트 문단과 빌더를 사용하는 것의 중요성은 무엇인가요?

A: 텍스트 단락과 빌더를 사용하면 텍스트 회전 및 서식에 대한 제어가 향상됩니다. 텍스트 단락은 텍스트 조각을 구성하는 구조화된 방법을 제공하는 반면 빌더는 PDF 문서 내에서 텍스트 콘텐츠의 생성 및 조작을 용이하게 합니다.

#### 질문: 각 텍스트 단락에 다른 회전 각도를 적용할 수 있나요?

 A: 예, 각 텍스트 단락에 다른 회전 각도를 적용할 수 있습니다.`Rotation` 의 속성`TextParagraph` 객체. 이를 통해 PDF 문서 내에서 다양하고 역동적인 텍스트 회전 효과를 만들 수 있습니다.

#### 질문: 텍스트 문단 내 텍스트 조각의 서식을 사용자 지정하려면 어떻게 해야 합니까?

 A: 다양한 속성을 설정하여 텍스트 조각의 서식을 사용자 정의할 수 있습니다.`TextState` 각각 내에서`TextFragment` 객체. 글꼴 크기, 글꼴 유형, 전경색과 배경색, 밑줄과 같은 속성을 조정하여 원하는 시각적 효과를 얻을 수 있습니다.

#### 질문: 이 방법을 사용해 더 복잡한 텍스트 회전 효과를 만들 수 있나요?

A: 물론입니다. 다양한 회전 각도와 서식 옵션을 사용하여 여러 텍스트 단락을 반복적으로 생성하면 복잡하고 시각적으로 매력적인 텍스트 회전 효과를 얻을 수 있으며, 이를 통해 PDF 문서의 가독성과 미학을 향상시킬 수 있습니다.

#### 질문: 텍스트 회전을 다른 텍스트 조작 기술과 결합하는 것이 가능할까요?

A: 네, Aspose.PDF 라이브러리에서 제공하는 다른 텍스트 조작 기술과 텍스트 회전을 결합할 수 있습니다. 여기에는 풍부하고 유익한 PDF 문서를 만들기 위해 표, 이미지, 하이퍼링크 등을 추가하는 것이 포함됩니다.

#### 질문: 프로젝트에서 Aspose.PDF 라이브러리를 사용하려면 특별 라이선스가 필요합니까?

A: 네, 프로젝트에서 Aspose.PDF 라이브러리를 사용하려면 유효한 Aspose 라이선스가 필요합니다. Aspose 웹사이트에서 라이선스를 얻을 수 있으며, 이를 통해 라이브러리를 효과적으로 통합하고 사용하는 데 필요한 자격 증명을 얻을 수 있습니다.