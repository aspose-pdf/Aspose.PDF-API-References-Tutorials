---
title: 다중 열 PDF 생성
linktitle: 다중 열 PDF 생성
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 다중 열 PDF를 만드는 방법을 알아보세요. 코드 예제와 자세한 설명이 포함된 단계별 가이드입니다. 전문가에게 완벽합니다.
type: docs
weight: 110
url: /ko/net/programming-with-text/create-multi-column-pdf/
---
## 소개

다중 열 PDF를 만드는 것은 텍스트를 더 체계적이고 읽기 쉬운 형식으로 표현하는 좋은 방법입니다. 보고서, 기사 또는 간행물 레이아웃을 만들든 다중 열 구조는 콘텐츠를 더 매력적으로 만들 수 있습니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 다중 열 PDF를 만드는 방법을 살펴보겠습니다. 걱정하지 마세요. 모든 것을 간단한 단계로 나누어서 플랫폼을 처음 사용하는 사람이라도 쉽게 따라할 수 있도록 하겠습니다.

## 필수 조건

코드로 들어가기 전에, 순조롭게 따라갈 수 있도록 꼭 준비해야 할 몇 가지 사항이 있습니다.

1.  .NET용 Aspose.PDF: 이 라이브러리를 설치해야 합니다. 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
2. 개발 환경: C# 코드를 작성하고 실행하기 위해 Visual Studio와 같은 원하는 IDE를 설정합니다.
3. .NET Framework: 호환되는 버전의 .NET이 설치되어 있는지 확인하세요.
4. C#에 대한 기본적인 이해: C# 구문에 익숙하면 도움이 되지만, 각 단계를 자세히 설명하겠습니다.
5.  임시 라이센스: Aspose.PDF는 워터마크나 제한을 피하기 위해 라이센스가 필요합니다.[임시 면허](https://purchase.aspose.com/temporary-license/) 필요한 경우.

## 패키지 가져오기

코딩을 시작하기 전에 Aspose.PDF와 상호 작용할 수 있는 필수 네임스페이스를 가져와야 합니다. 가져와야 할 내용은 다음과 같습니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

이러한 네임스페이스는 PDF 생성, 도형 그리기, 텍스트 서식 처리에 필요한 클래스에 대한 액세스를 제공합니다.

여러 열로 구성된 PDF를 만드는 과정을 간단하고 관리하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 문서 설정

시작하려면 새 PDF 문서를 만들어야 합니다. 여기에는 여백을 정의하고 콘텐츠를 넣을 페이지를 추가하는 것이 포함됩니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 새 PDF 문서 만들기
Document doc = new Document();

// PDF 파일의 여백을 설정합니다
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;

// 문서에 페이지 추가
Page page = doc.Pages.Add();
```

 여기서 우리는 다음을 생성했습니다.`Document`객체를 만들고 왼쪽과 오른쪽 여백을 40단위로 설정합니다. 그런 다음 이 문서에 새 페이지를 추가했는데, 여기에는 다중 열 레이아웃이 포함됩니다.

## 2단계: 섹션을 구분하기 위한 줄 추가

다음으로, 시각적 분리를 위해 페이지에 수평선을 추가해 보겠습니다. 이렇게 하면 깔끔하고 전문적인 모습을 만드는 데 도움이 됩니다.

```csharp
// 선을 보관할 그래프 객체를 생성합니다.
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500.0, 2.0);

// 페이지의 문단 컬렉션에 줄을 추가합니다.
page.Paragraphs.Add(graph1);

// 선의 좌표를 정의합니다
float[] posArr = new float[] { 1, 2, 500, 2 };

// 선을 생성하여 그래프에 추가합니다.
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
```

 여기서 우리는 다음을 사용하여 수평선을 만들고 있습니다.`Graph` 그리고`Line` 클래스. 이 줄은 페이지에 추가됩니다.`Paragraphs` 모든 시각적 요소를 보유한 컬렉션입니다.

## 3단계: 서식이 적용된 HTML 텍스트 추가

다음으로, PDF에서 텍스트를 동적으로 서식 지정하는 방법을 보여주기 위해 HTML 태그가 포함된 텍스트를 삽입해 보겠습니다.

```csharp
// HTML 콘텐츠로 문자열을 만듭니다.
string s = "<font face=\"Times New Roman\" size=4>" +
           "<strong> How to Steer Clear of Money Scams </strong>" +
           "</font>";

// 포맷된 텍스트로 새 HtmlFragment를 만듭니다.
HtmlFragment heading_text = new HtmlFragment(s);

// 페이지에 HTML 텍스트를 추가합니다
page.Paragraphs.Add(heading_text);
```

 사용하여`HtmlFragment`클래스에서 글꼴 크기, 스타일, 굵은 텍스트와 같은 HTML 태그를 포함하는 서식이 지정된 텍스트를 추가할 수 있습니다. 이는 PDF 콘텐츠의 모양을 향상시키는 데 유용합니다.

## 4단계: 다중 열 레이아웃 만들기

이제 다중 열 레이아웃을 만들겠습니다. 여기서 마법이 일어납니다. 원하는 열의 수와 너비를 지정할 수 있습니다.

```csharp
// 열을 고정하기 위한 떠 있는 상자를 만듭니다.
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();

// 열의 개수와 열 사이의 간격을 설정합니다.
box.ColumnInfo.ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

// 페이지에 상자를 추가하세요
page.Paragraphs.Add(box);
```

여기서는 두 개의 열을 포함하는 떠다니는 상자를 만듭니다. 열 사이의 간격을 설정하고 각 열의 너비가 105단위가 되도록 지정합니다. 이렇게 하면 PDF 내에서 원하는 열 레이아웃을 만들 수 있습니다.

## 5단계: 열에 텍스트 추가

 이제 열에 텍스트 콘텐츠를 채워 봅시다. 다양한 내용을 추가할 수 있습니다.`TextFragment` 각 열에 객체를 추가합니다.

```csharp
// 첫 번째 텍스트 조각을 만들고 서식 지정
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.FontStyle = FontStyles.Italic;
box.Paragraphs.Add(text1);

// 구분을 위해 또 다른 줄을 추가합니다
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50.0, 10.0);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

//두 번째 텍스트 조각을 만들고 추가합니다.
TextFragment text2 = new TextFragment("Lorem ipsum dolor sit amet, consectetur adipiscing elit...");
box.Paragraphs.Add(text2);
```

 우리는 추가한다`TextFragment` 떠 있는 상자로, 그 다음에 또 다른 수평선이 이어집니다. 두 번째`TextFragment` 두 번째 열을 채울 더 많은 텍스트가 들어 있습니다. 이러한 조각을 사용하면 다양한 서식 옵션으로 PDF에 다양한 텍스트 요소를 추가할 수 있습니다.

## 6단계: PDF 저장

모든 콘텐츠를 추가한 후 마지막 단계는 문서를 PDF 파일로 저장하는 것입니다.

```csharp
// PDF에 대한 출력 경로를 정의합니다
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";

// PDF 문서 저장
doc.Save(dataDir);

// 출력 성공 메시지
Console.WriteLine("\nMulti-column PDF file created successfully.\nFile saved at " + dataDir);
```

이 블록은 PDF 파일을 지정된 디렉토리에 저장하고 콘솔에 성공 메시지를 출력합니다. 이제 PDF를 볼 준비가 되었습니다!

## 결론

간단한 단계를 따르면 Aspose.PDF for .NET을 사용하여 전문적인 다중 열 PDF를 쉽게 만들 수 있습니다. 보고서, 기사 또는 뉴스레터이든 이 기술은 콘텐츠를 시각적으로 매력적인 형식으로 구성하는 데 도움이 됩니다. Aspose.PDF는 여백과 레이아웃에서 텍스트 서식 지정 및 모양 그리기에 이르기까지 PDF를 사용자 정의하기 위한 강력한 도구를 제공합니다. 이제 여러분이 시도하고 PDF 생성 기술을 한 단계 업그레이드할 차례입니다!

## 자주 묻는 질문

### PDF에 두 개 이상의 열을 만들 수 있나요?
 네, 필요한 만큼 많은 열을 만들 수 있습니다. 간단히 조정하세요.`ColumnCount` 원하는 열 개수에 맞게 속성을 변경합니다.

### 각 열의 너비를 어떻게 변경합니까?
 수정할 수 있습니다`ColumnWidths` 각 열에 대해 다른 너비를 지정하는 속성입니다. 이 속성은 공백으로 구분된 값의 문자열을 허용합니다.

### 열에 이미지를 추가할 수 있나요?
 물론입니다! 다음을 사용하여 이미지를 추가할 수 있습니다.`Image` 클래스를 만들고 PDF의 떠 있는 상자나 다른 레이아웃 요소에 포함시킵니다.

### HTML 태그로 열의 텍스트에 스타일을 지정할 수 있나요?
 네, HTML 태그를 사용할 수 있습니다.`HtmlFragment` 텍스트에 스타일을 지정할 개체입니다. 여기에는 글꼴, 크기, 색상 등이 추가됩니다.

### 동일한 열 레이아웃으로 페이지를 더 추가하려면 어떻게 해야 하나요?
 추가 페이지를 추가하려면 다음을 사용하세요.`doc.Pages.Add()` 그리고 각 페이지에 열과 내용을 추가하는 과정을 반복합니다.