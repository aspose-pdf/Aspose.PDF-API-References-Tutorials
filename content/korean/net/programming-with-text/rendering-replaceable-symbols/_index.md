---
title: PDF 파일에서 대체 가능한 심볼 렌더링
linktitle: PDF 파일에서 대체 가능한 심볼 렌더링
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 대체 가능한 심볼을 렌더링하는 방법을 알아보세요.
type: docs
weight: 310
url: /ko/net/programming-with-text/rendering-replaceable-symbols/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에서 대체 가능한 심볼을 렌더링하는 방법을 설명합니다. PDF 생성, 줄바꿈 마커가 있는 텍스트 조각 추가, 텍스트 속성 설정, 텍스트 위치 지정, 제공된 C# 소스 코드를 사용하여 PDF 저장의 단계별 프로세스를 살펴보겠습니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉토리 설정

 먼저 생성된 PDF 파일을 저장할 디렉토리 경로를 설정해야 합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 원하는 디렉토리의 경로를 담은 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 및 페이지 만들기

 다음으로 새 PDF 문서를 만들고 이를 사용하여 페이지를 추가합니다.`Document` 수업과`Page` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## 3단계: 줄바꿈 마커로 텍스트 조각 추가

 우리는 만듭니다`TextFragment` 객체를 만들고 텍스트에 줄바꿈 표시기를 포함하도록 설정합니다.`Environment.NewLine`)를 사용하여 여러 줄의 텍스트를 표현합니다.

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## 4단계: 텍스트 조각 속성 설정

원하는 경우 텍스트 조각에 대해 글꼴 크기, 글꼴, 배경색, 전경색 등 다양한 속성을 설정할 수 있습니다.

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## 5단계: 텍스트 단락 및 위치 만들기

 우리는 만듭니다`TextParagraph` 객체를 사용하여 텍스트 조각을 문단에 추가하고 페이지에서 문단의 위치를 설정합니다.

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## 6단계: 페이지에 텍스트 문단 추가

 우리는 만듭니다`TextBuilder` 페이지에 객체를 추가하고 텍스트 빌더에 텍스트 문단을 추가합니다.

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

### .NET용 Aspose.PDF를 사용하여 대체 가능한 심볼 렌더링을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
// 필수 줄바꿈 마커를 포함하는 텍스트로 새 TextFragment를 초기화합니다.
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
// 필요한 경우 텍스트 조각 속성을 설정하세요
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
// TextParagraph 객체 생성
TextParagraph par = new TextParagraph();
// 문단에 새로운 TextFragment 추가
par.AppendLine(textFragment);
// 문단 위치 설정
par.Position = new Aspose.Pdf.Text.Position(100, 600);
// TextBuilder 객체를 생성합니다
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
// TextBuilder를 사용하여 TextParagraph 추가
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 대체 가능한 심볼을 렌더링하는 방법을 알아보았습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF를 만들고, 줄바꿈 마커가 있는 텍스트를 추가하고, 텍스트 속성을 설정하고, 페이지에 텍스트를 배치하고, PDF를 저장할 수 있습니다.

### 자주 묻는 질문

#### 질문: "PDF 파일에서 대체 가능한 기호 렌더링" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일에서 대체 가능한 심볼 렌더링" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 대체 가능한 심볼을 포함하는 PDF 문서를 만드는 방법을 보여줍니다. 이러한 심볼은 여러 줄의 콘텐츠를 만들기 위해 줄 바꿈 마커가 있는 텍스트 조각으로 표현됩니다.

#### 질문: PDF 문서에서 대체 가능한 기호를 렌더링하고 싶은 이유는 무엇인가요?

A: 대체 가능한 심볼을 렌더링하는 것은 변수 또는 사용자별 정보를 포함하는 PDF 콘텐츠를 동적으로 생성해야 할 때 유용합니다. 이러한 심볼은 런타임 중에 양식 필드 값이나 개인화된 세부 정보와 같은 실제 데이터로 대체할 수 있는 플레이스홀더 역할을 합니다.

#### 질문: 문서 디렉토리를 어떻게 설정하나요?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 생성된 PDF 파일을 저장할 디렉토리 경로가 있는 변수입니다.

#### 질문: Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 대체 가능한 기호를 렌더링하려면 어떻게 해야 하나요?

A: 튜토리얼은 단계별로 과정을 안내합니다.

1.  다음을 사용하여 새 PDF 문서를 만듭니다.`Document` 수업.
2.  문서에 페이지를 추가하려면 다음을 사용합니다.`Page` 수업.
3.  생성하다`TextFragment` 줄바꿈 표시가 있는 객체(`Environment.NewLine`)를 사용하여 여러 줄로 된 콘텐츠를 표현합니다.
4. 글꼴 크기, 글꼴, 배경색, 전경색 등 텍스트 조각의 속성을 사용자 지정합니다.
5.  생성하다`TextParagraph` 객체를 만들고, 텍스트 조각을 추가한 다음, 페이지에서 문단의 위치를 설정합니다.
6.  생성하다`TextBuilder` 페이지에 객체를 추가하고 텍스트 문단을 추가합니다.
7. PDF 문서를 저장합니다.

#### Q: 줄바꿈 표시기를 사용하는 목적은 무엇입니까?`Environment.NewLine`) in the text fragment?

 A: 줄바꿈 마커는 단일 텍스트 조각 내에서 여러 줄의 콘텐츠를 만드는 데 사용됩니다. 다음을 사용하여`Environment.NewLine`텍스트에서 줄 바꿈이 발생하는 위치를 지정할 수 있습니다.

#### 질문: 교체 가능한 심볼의 모양을 사용자 지정할 수 있나요?

A: 네, 글꼴 크기, 글꼴, 배경색, 전경색 등 텍스트 조각의 다양한 속성을 사용자 지정할 수 있습니다. 이러한 속성은 PDF 문서에서 대체 가능한 심볼의 시각적 모양을 결정합니다.

#### 질문: 페이지에서 텍스트의 위치를 어떻게 지정합니까?

 A: 텍스트의 위치를 설정하려면 다음을 생성하세요.`TextParagraph` 객체 및 사용`Position` 해당 페이지에서 문단이 위치해야 하는 X 및 Y 좌표를 지정하는 속성입니다.

#### 질문: 제공된 코드를 실행하면 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따라 제공된 C# 코드를 실행하면 대체 가능한 심볼을 포함하는 PDF 문서를 만들 수 있습니다. 대체 가능한 심볼은 줄바꿈 마커와 사용자 지정 속성이 있는 텍스트 조각으로 표현됩니다.

#### 질문: 이 방법을 사용하면 개인화된 PDF 문서를 동적으로 생성할 수 있나요?

A: 네, 이 접근 방식은 개인화된 정보가 포함된 PDF 문서를 동적으로 생성하는 데 적합합니다. 대체 가능한 심볼을 실제 데이터로 대체하면 각 사용자 또는 시나리오에 맞게 사용자 지정된 PDF 콘텐츠를 만들 수 있습니다.