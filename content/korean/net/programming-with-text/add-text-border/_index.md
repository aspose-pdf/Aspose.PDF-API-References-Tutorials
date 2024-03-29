---
title: PDF 파일에 텍스트 테두리 추가
linktitle: PDF 파일에 텍스트 테두리 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 텍스트 테두리를 추가하는 방법을 알아보세요.
type: docs
weight: 70
url: /ko/net/programming-with-text/add-text-border/
---
이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 PDF 파일에 텍스트 테두리를 추가하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio 또는 기타 C# 컴파일러가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필수 네임스페이스 가져오기
텍스트 테두리를 추가하려는 코드 파일에서 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉터리 설정
 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리의 경로를 사용하세요.

## 4단계: 새 문서 개체 만들기
 새 인스턴스화`Document` 다음 코드 줄을 추가하여 객체를 생성합니다.

```csharp
Document pdfDocument = new Document();
```

## 5단계: 문서에 페이지 추가
 다음을 사용하여 문서에 새 페이지를 추가합니다.`Add` 의 방법`Pages`수집. 제공된 코드에서 새 페이지는 변수에 할당됩니다.`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 6단계: TextFragment 만들기
 만들기`TextFragment` 개체를 선택하고 원하는 텍스트를 제공하세요. 다음을 사용하여 텍스트 조각의 위치를 설정합니다.`Position` 재산. 제공된 코드에서 텍스트는 "main text"로 설정되고 페이지의 (100, 600)에 위치합니다.

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## 7단계: 텍스트 속성 설정
글꼴 크기, 글꼴 유형, 배경색, 전경색 등과 같은 텍스트 속성을 사용자 정의합니다. 제공된 코드에서는 텍스트 조각에 대해 글꼴 크기, 글꼴, 배경색, 전경색 및 스트로크 색상과 같은 속성이 설정됩니다.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## 8단계: 텍스트 테두리 활성화
 텍스트 테두리를 활성화하려면`DrawTextRectangleBorder`텍스트 조각의 속성`TextState` 에게`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## 9단계: 페이지에 TextFragment 추가
 사용`TextBuilder` 추가할 클래스`TextFragment` 페이지에 반대합니다.

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## 10단계: PDF 문서 저장
 다음을 사용하여 PDF 문서를 저장합니다.`Save` 의 방법`Document` 물체. 3단계에서 설정한 출력 파일 경로를 지정합니다.

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 텍스트 테두리 추가에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 새 문서 개체 만들기
Document pdfDocument = new Document();
// 특정 페이지 가져오기
Page pdfPage = (Page)pdfDocument.Pages.Add();
// 텍스트 조각 만들기
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
// 텍스트 속성 설정
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// 텍스트 사각형 주위의 그리기 테두리(획)에 대한 StrokingColor 속성을 설정합니다.
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
// DrawTextRectangleBorder 속성 값을 true로 설정합니다.
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
// 문서 저장
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## 결론
.NET용 Aspose.PDF를 사용하여 PDF 문서에 텍스트 테두리를 성공적으로 추가했습니다. 이제 결과 PDF 파일을 지정된 출력 파일 경로에서 찾을 수 있습니다.

### FAQ

#### Q: 이 튜토리얼의 주요 초점은 무엇입니까?

A: 이 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에 텍스트 테두리를 추가하는 과정을 안내합니다. 제공된 C# 소스 코드는 이를 달성하는 데 필요한 단계를 보여줍니다.

#### Q: 이 튜토리얼을 위해 어떤 네임스페이스를 가져와야 합니까?

A: 텍스트 테두리를 추가하려는 코드 파일에서 파일 시작 부분에 다음 네임스페이스를 가져옵니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### Q: 문서 디렉터리를 어떻게 지정합니까?

 A: 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

#### Q: 문서 개체를 어떻게 생성합니까?

 A: 4단계에서는 새 인스턴스를 생성합니다.`Document` 다음 코드 줄을 사용하여 객체를 생성합니다.

```csharp
Document pdfDocument = new Document();
```

#### Q: 문서에 페이지를 어떻게 추가하나요?

 A: 5단계에서는 다음을 사용하여 문서에 새 페이지를 추가합니다.`Add` 의 방법`Pages` 수집:

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### Q: TextFragment를 생성하고 위치를 설정하려면 어떻게 해야 합니까?

 A: 6단계에서는`TextFragment`개체를 선택하고 다음을 사용하여 페이지에서의 위치를 설정합니다.`Position` 재산:

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### Q: 텍스트 테두리를 포함한 텍스트 속성을 어떻게 사용자 정의할 수 있습니까?

A: 7단계에서는 글꼴 크기, 글꼴 유형, 배경색, 전경색, 텍스트 테두리 등 다양한 텍스트 속성을 사용자 정의합니다.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### Q: TextFragment를 PDF 문서에 어떻게 추가합니까?

 A: 9단계에서는`TextBuilder` 추가할 클래스`TextFragment` 페이지에 반대합니다:

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### Q: 결과 PDF 문서를 어떻게 저장합니까?

 A: 테두리가 있는 텍스트를 추가한 후`Save` 의 방법`Document` PDF 문서를 저장할 개체:

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### Q: 이 튜토리얼의 주요 내용은 무엇입니까?

A: 이 튜토리얼을 따르면 .NET용 Aspose.PDF를 사용하여 텍스트 테두리를 추가하여 PDF 문서를 향상시키는 방법을 성공적으로 배웠습니다. 이는 PDF 파일 내의 특정 텍스트 내용을 강조하는 데 특히 유용할 수 있습니다.