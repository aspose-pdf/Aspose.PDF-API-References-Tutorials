---
title: PDF 파일에서 이미지 주위에 텍스트 배치
linktitle: PDF 파일에서 이미지 주위에 텍스트 배치
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF에서 이미지 주위에 텍스트를 배치하는 방법을 알아보세요. 단계별 가이드를 따라 이미지와 텍스트가 나란히 있는 전문적인 PDF를 만드세요.
type: docs
weight: 260
url: /ko/net/programming-with-text/placing-text-around-image/
---
## 소개

PDF 파일에서 이미지 주위에 텍스트를 배치하려고 했지만 어렵다고 생각한 적이 있나요? 그렇다면 올바른 곳에 오셨습니다! Aspose.PDF for .NET은 이 프로세스를 간소화하여 몇 줄의 코드만으로 이미지 옆에 텍스트를 배치할 수 있도록 합니다. 보고서, 문서 또는 프레젠테이션을 만들 때 이 기능은 콘텐츠의 레이아웃을 향상시키고 시각적으로 더 매력적으로 만드는 훌륭한 방법입니다. 오늘은 Aspose.PDF for .NET을 사용하여 PDF 문서에서 이미지 주위에 텍스트를 배치하는 방법을 살펴보겠습니다.

## 필수 조건

코드로 넘어가기 전에 모든 것이 설정되었는지 확인해 보겠습니다. 필요한 것은 다음과 같습니다.

-  .NET용 Aspose.PDF: 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
- Visual Studio: 원활하게 진행하려면 최신 버전이 설치되어 있는지 확인하세요.
- .NET Framework: 이 예제에서는 .NET을 사용하므로 .NET 개발에 적합한 환경이 설정되어 있는지 확인하세요.
-  임시 면허: 임시 면허를 요청할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 제품을 평가하는 경우.

아직 .NET용 Aspose.PDF를 설정하지 않은 경우 설치 지침을 따르십시오.[선적 서류 비치](https://reference.aspose.com/pdf/net/).

## 네임스페이스 가져오기

코딩을 시작하기 전에 필요한 네임스페이스를 가져와야 합니다. 이를 위한 코드 조각은 다음과 같습니다.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

 이러한 네임스페이스는 다음과 같은 클래스에 대한 액세스를 제공하므로 필수적입니다.`Document`, `Page`, `Image` , 그리고`HtmlFragment`이를 사용하여 PDF를 만들고 조작할 것입니다.

이제 무대를 마련했으니 Aspose.PDF for .NET을 사용하여 PDF 파일의 이미지 주위에 텍스트를 배치하는 방법을 알아보겠습니다. 단계별로 안내해 드리겠습니다.

## 1단계: 문서 개체 인스턴스화

 먼저 PDF 문서를 만들어야 합니다. Aspose.PDF에서는 다음을 인스턴스화하여 이를 수행합니다.`Document` 객체. 이 객체는 우리가 추가할 모든 콘텐츠의 기반이 될 것입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

여기서 우리는 빈 PDF 문서를 만들었습니다. 아직 페이지가 없지만 걱정하지 마세요. 다음 단계에서 페이지를 추가할 겁니다.

## 2단계: 문서에 페이지 추가

이제 문서가 있으니 페이지를 추가할 차례입니다. 이것은 콘텐츠를 추가할 빈 종이를 만드는 것으로 생각하세요.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

이 코드는 문서에 새 페이지를 추가합니다. 기본적으로 페이지는 비어 있지만, 우리는 그것을 바꾸려고 합니다.

## 3단계: 콘텐츠를 정리하기 위한 표 만들기

이미지와 텍스트를 제대로 정렬하기 위해 표를 사용합니다. PDF의 표는 Word 문서나 HTML과 마찬가지로 레이아웃을 구성하는 데 도움이 될 수 있습니다.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

이 스니펫은 테이블을 만들어 페이지에 추가합니다. 테이블을 이미지와 텍스트를 정렬하기 위한 프레임워크로 생각하세요.

## 4단계: 표의 열 너비 설정

이제 테이블을 추가했으니 열의 너비를 정의해야 합니다. 이렇게 하면 이미지와 텍스트가 페이지에서 적절한 크기로 조정됩니다.

```csharp
table1.ColumnWidths = "120 270";
```

이 줄은 두 열의 너비를 설정합니다. 하나는 이미지용이고 다른 하나는 텍스트용입니다. 이미지나 텍스트에 더 많은 공간이 필요하거나 더 적은 공간이 필요한 경우 이 값을 조정합니다.

## 5단계: 여백 및 패딩 정의

모든 것이 깔끔하게 보이도록 표에 여백과 패딩을 추가해 보겠습니다.

```csharp
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
table1.DefaultCellPadding = margin;
```

이러한 설정을 사용하면 표의 간격이 일관되게 유지되어 콘텐츠가 시각적으로 매력적으로 보입니다.

## 6단계: 표에 이미지 삽입

이제 재밌는 부분인 이미지 추가에 들어가겠습니다. 이 경우 Aspose 로고를 추가하지만 원하는 이미지를 자유롭게 사용하세요.

```csharp
Aspose.Pdf.Row row1 = table1.Rows.Add();
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

무슨 일이 일어나고 있는지 알려드리겠습니다.
- 귀하가 지정한 디렉토리에서 이미지를 로드합니다.
- 이미지의 높이와 너비를 설정합니다.
- 마지막으로, 표의 첫 번째 셀에 이미지를 추가합니다.

## 7단계: 이미지 옆에 텍스트 추가

이제 이미지가 제자리에 있으므로 그 옆에 텍스트를 추가해 보겠습니다. 이 예에서는 HTML 형식의 텍스트를 사용하여 콘텐츠 스타일을 지정합니다.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF document reporting component that enables .NET applications to <b>create PDF documents from scratch</b> without utilizing Adobe Acrobat.</font>";

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

이 블록은 이미지 옆의 셀에 스타일이 적용된 제목과 설명을 추가합니다. HTML 태그를 사용하여 텍스트를 서식 지정하여 더욱 사용자 정의할 수 있습니다.

## 8단계: 수직 정렬 조정

기본적으로 테이블 셀의 내용은 원하는 대로 정렬되지 않을 수 있습니다. 이 경우 텍스트가 셀의 맨 위에 정렬되도록 해야 합니다.

```csharp
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
```

이렇게 하면 텍스트가 셀의 맨 위에 표시되어 레이아웃이 깔끔하고 전문적으로 유지됩니다.

## 9단계: 이미지와 설명 아래에 더 많은 텍스트 추가

이미지와 텍스트 아래에 더 많은 콘텐츠를 포함하고 싶을 수도 있습니다. 이 목적을 위해 표에 또 다른 행을 추가해 보겠습니다.

```csharp
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
SecondRow.Cells[0].ColSpan = 2;
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;

string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

여기서는 레이아웃의 균형을 유지하기 위해 두 열에 걸쳐 추가 텍스트가 있는 행을 추가했습니다.

## 10단계: PDF 문서 저장

마지막으로, 변경 사항을 볼 수 있도록 문서를 저장해야 합니다.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

이렇게 하면 원하는 대로 이미지와 텍스트가 포함된 PDF가 저장됩니다.

## 결론

PDF에서 이미지 주위에 텍스트를 배치하는 것은 어려운 작업처럼 보일 수 있지만 Aspose.PDF for .NET은 이 과정을 간소화합니다. 표, 이미지, 스타일이 지정된 텍스트를 활용하면 최소한의 노력으로 전문적인 PDF를 만들 수 있습니다. 몇 줄의 코드만 있으면 원하는 위치에 정확히 콘텐츠를 배치하여 문서에 세련되고 잘 정리된 모양을 줄 수 있습니다.

## 자주 묻는 질문

### 이 방법을 사용하면 텍스트와 함께 여러 이미지를 배치할 수 있나요?
네, 표에 행과 셀을 더 추가하여 이미지와 텍스트를 추가하기만 하면 됩니다.

### 이미지의 정렬을 변경할 수 있나요?
물론입니다! 셀의 정렬 속성을 조정하여 이미지 정렬을 수정할 수 있습니다.

### 텍스트의 스타일을 추가로 지정하려면 어떻게 해야 하나요?
 HTML 태그를 사용할 수 있습니다.`HtmlFragment` 굵게, 기울임꼴 또는 다른 글꼴과 같은 다양한 스타일을 적용하는 데 사용됩니다.

### 텍스트와 이미지 사이의 간격을 조절할 수 있나요?
 네, 다음을 사용하여`MarginInfo` 객체를 사용하면 요소 사이의 패딩과 여백을 제어할 수 있습니다.

### 텍스트에 링크를 추가할 수 있나요?
 물론입니다! 다음을 사용하여 HTML 형식의 텍스트에 하이퍼링크를 삽입할 수 있습니다.`<a>` 꼬리표.