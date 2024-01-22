---
title: PDF 파일에서 교체 가능한 기호 렌더링
linktitle: PDF 파일에서 교체 가능한 기호 렌더링
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 교체 가능한 기호를 렌더링하는 방법을 알아보세요.
type: docs
weight: 310
url: /ko/net/programming-with-text/rendering-replaceable-symbols/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에서 교체 가능한 기호를 렌더링하는 방법을 설명합니다. 제공된 C# 소스 코드를 사용하여 PDF 만들기, 줄 바꿈 표시가 있는 텍스트 조각 추가, 텍스트 속성 설정, 텍스트 위치 지정 및 PDF 저장 등의 단계별 프로세스를 살펴보겠습니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉터리 설정

 먼저 생성된 PDF 파일을 저장할 디렉터리의 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir`변수를 원하는 디렉터리의 경로로 바꿉니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 및 페이지 만들기

 다음으로 새 PDF 문서를 만들고 다음을 사용하여 페이지를 추가합니다.`Document` 수업과`Page` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## 3단계: 줄 바꿈 마커가 있는 텍스트 조각 추가

 우리는`TextFragment`개행 표시자를 포함하도록 개체를 설정하고 해당 텍스트를 설정합니다(`Environment.NewLine`) 여러 줄의 텍스트를 나타냅니다.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## 4단계: 텍스트 조각 속성 설정

원하는 경우 글꼴 크기, 글꼴, 배경색, 전경색 등 텍스트 조각에 대한 다양한 속성을 설정할 수 있습니다.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## 5단계: 텍스트 단락 및 위치 만들기

 우리는`TextParagraph` 개체를 선택하고 텍스트 조각을 단락에 추가하고 페이지에서 단락의 위치를 설정합니다.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## 6단계: 페이지에 텍스트 단락 추가

 우리는`TextBuilder` 페이지에 개체를 추가하고 텍스트 작성기에 텍스트 단락을 추가합니다.

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## 7단계: PDF 문서 저장

마지막으로 PDF 문서를 지정된 출력 파일에 저장합니다.

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 교체 가능한 기호를 렌더링하기 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// 필수 개행 마커가 포함된 텍스트로 새 TextFragment를 초기화합니다.
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// 필요한 경우 텍스트 조각 속성을 설정하세요.
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// TextParagraph 객체 생성
TextParagraph par = new TextParagraph();
// 단락에 새 TextFragment 추가
par.AppendLine(textFragment);
// 단락 위치 설정
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// TextBuilder 객체 생성
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// TextBuilder를 사용하여 TextParagraph 추가
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 교체 가능한 기호를 렌더링하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF를 만들고, 줄바꿈 마커가 있는 텍스트를 추가하고, 텍스트 속성을 설정하고, 페이지에 텍스트를 배치하고, PDF를 저장할 수 있습니다.

### FAQ

#### Q: "PDF 파일에서 교체 가능한 기호 렌더링" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일에서 교체 가능한 기호 렌더링" 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 교체 가능한 기호가 포함된 PDF 문서를 만드는 방법을 보여줍니다. 이러한 기호는 여러 줄의 콘텐츠를 생성하기 위해 개행 표시가 있는 텍스트 조각으로 표시됩니다.

#### Q: PDF 문서에서 교체 가능한 기호를 렌더링하려는 이유는 무엇입니까?

A: 교체 가능한 기호 렌더링은 변수 또는 사용자별 정보가 포함된 PDF 컨텐츠를 동적으로 생성해야 할 때 유용합니다. 이러한 기호는 런타임 중에 양식 필드 값이나 개인화된 세부 정보와 같은 실제 데이터로 대체될 수 있는 자리 표시자 역할을 합니다.

#### Q: 문서 디렉터리를 어떻게 설정합니까?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 생성된 PDF 파일을 저장하려는 디렉터리의 경로로 변수를 지정합니다.

#### Q: Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 교체 가능한 기호를 어떻게 렌더링합니까?

A: 튜토리얼에서는 프로세스를 단계별로 안내합니다.

1.  다음을 사용하여 새 PDF 문서를 만듭니다.`Document` 수업.
2.  다음을 사용하여 문서에 페이지를 추가합니다.`Page` 수업.
3.  만들기`TextFragment` 개행 마커가 있는 객체(`Environment.NewLine`) 여러 줄의 내용을 나타냅니다.
4. 글꼴 크기, 글꼴, 배경색, 전경색 등 텍스트 조각의 속성을 사용자 정의합니다.
5.  만들기`TextParagraph` 개체에 텍스트 조각을 추가하고 페이지에서 단락의 위치를 설정합니다.
6.  만들기`TextBuilder` 페이지에 개체를 추가하고 텍스트 단락을 추가합니다.
7. PDF 문서를 저장합니다.

#### Q: 개행 마커를 사용하는 목적은 무엇입니까(`Environment.NewLine`) in the text fragment?

 A: 줄 바꿈 마커는 단일 텍스트 조각 내에 여러 줄의 콘텐츠를 만드는 데 사용됩니다. 사용하여`Environment.NewLine`를 사용하면 텍스트에서 줄 바꿈이 발생해야 하는 위치를 지정할 수 있습니다.

#### Q: 교체 가능한 기호의 모양을 사용자 정의할 수 있습니까?

A: 예, 글꼴 크기, 글꼴, 배경색, 전경색 등 텍스트 조각의 다양한 속성을 사용자 지정할 수 있습니다. 이러한 속성은 PDF 문서에서 교체 가능한 기호의 시각적 모양을 결정합니다.

#### Q: 페이지에서 텍스트의 위치를 어떻게 지정합니까?

 A: 텍스트 위치를 설정하려면`TextParagraph` 객체를 사용하고`Position` 단락이 배치되어야 하는 페이지의 X 및 Y 좌표를 지정하는 속성입니다.

#### Q: 제공된 코드를 실행하면 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따르고 제공된 C# 코드를 실행하면 교체 가능한 기호가 포함된 PDF 문서를 만들 수 있습니다. 교체 가능한 기호는 개행 표시와 사용자 정의된 속성이 있는 텍스트 조각으로 표시됩니다.

#### Q: 이 접근 방식을 사용하여 개인화된 PDF 문서를 동적으로 생성할 수 있습니까?

A: 예, 이 접근 방식은 개인화된 정보가 포함된 PDF 문서를 동적으로 생성하는 데 적합합니다. 교체 가능한 기호를 실제 데이터로 대체함으로써 각 사용자 또는 시나리오에 맞는 맞춤형 PDF 컨텐츠를 생성할 수 있습니다.