---
title: 스타일 테이블 요소
linktitle: 스타일 테이블 요소
second_title: .NET API 참조를 위한 Aspose.PDF
description: 단계별 지침, 사용자 정의 스타일, PDF/UA 준수를 통해 .NET용 Aspose.PDF에서 표 요소를 만들고 스타일을 지정하는 방법을 알아보세요.
type: docs
weight: 170
url: /ko/net/programming-with-tagged-pdf/style-table-element/
---
## 소개

이 글에서는 Aspose.PDF for .NET을 사용하여 테이블 요소를 만들고 스타일을 지정하는 방법을 알아보겠습니다. 테이블을 구조화하고, 사용자 지정 스타일을 적용하고, 문서의 PDF/UA 준수 여부를 확인하는 방법을 알아봅니다. 이 튜토리얼을 마치면 PDF에서 전문적인 테이블을 쉽게 만들 수 있을 것입니다!

## 필수 조건

튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.

1. 컴퓨터에 Visual Studio나 비슷한 IDE가 설치되어 있어야 합니다.
2. 애플리케이션을 실행하려면 .NET Framework 또는 .NET Core SDK가 필요합니다.
3.  .NET 라이브러리용 Aspose.PDF를 다운로드하여 프로젝트에서 참조합니다. 최신 버전은 다음에서 가져올 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
4.  유효한 Aspose 라이센스 또는[임시 면허](https://purchase.aspose.com/temporary-license/) 라이브러리의 모든 기능을 활용하세요.

## 패키지 가져오기

시작하려면 필요한 네임스페이스를 프로젝트로 가져옵니다.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이러한 네임스페이스는 핵심 PDF 작업, 태그가 지정된 콘텐츠, 표 및 텍스트 서식을 다룹니다.

이제 Aspose.PDF에서 테이블을 만들고 스타일링하는 과정을 분석해 보겠습니다. 각 섹션을 자세히 살펴보겠습니다. 따라할 수 있도록요.

## 1단계: 새 PDF 문서 만들기 및 태그가 지정된 콘텐츠 설정

첫 번째 단계에서는 빈 PDF 문서를 만들고 태그가 지정된 콘텐츠를 설정합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 새 PDF 문서 만들기
Document document = new Document();

// 태그가 지정된 콘텐츠 설정
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");
```

 우리는 새로운 것을 만드는 것으로 시작합니다`Document` PDF를 나타내는 객체입니다.`TaggedContent`객체는 문서의 구조를 관리하고 접근성 표준을 준수하는 데 사용됩니다. 적절한 태그를 위해 문서의 제목과 언어를 설정합니다.

## 2단계: 루트 요소 정의

다음으로, PDF에 있는 모든 콘텐츠의 컨테이너 역할을 하는 루트 구조 요소를 만들어 보겠습니다.

```csharp
// 루트 구조 요소를 가져옵니다
StructureElement rootElement = taggedContent.RootElement;
```

 그만큼`RootElement` 표를 포함한 모든 구조화된 요소의 기본 컨테이너 역할을 합니다. 문서의 구조적 계층을 유지하는 데 도움이 되며, 이는 조직과 접근성에 모두 중요합니다.

## 3단계: 테이블 요소 만들기 및 스타일 지정

 이제 루트 요소가 설정되었으므로 다음을 생성합니다.`TableElement` 배경색, 테두리, 정렬 등의 스타일을 적용합니다.

```csharp
// 테이블 구조 요소 생성
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);

// 테이블 스타일 지정
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
```

 우리는 만듭니다`TableElement` , 테이블 구조를 정의합니다.`BackgroundColor`, `Border` , 그리고`Alignment` 속성을 사용하면 테이블의 모양을 사용자 정의할 수 있습니다.`Broken` 이 속성은 표가 여러 페이지에 걸쳐 나누어질 경우 수직 방향으로 나누어지도록 보장합니다.

## 4단계: 테이블 크기 및 셀 스타일 설정

이 단계에서는 열 수, 셀 패딩 및 기타 중요한 표 속성을 정의합니다.

```csharp
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
```

 우리는 테이블의 각 열이 균일하게 간격을 두도록 열 너비를 지정합니다.`DefaultCellBorder`, `DefaultCellPadding` , 그리고`DefaultCellTextState` 테두리, 패딩, 텍스트 색상, 글꼴 크기 등 셀의 기본 스타일을 정의합니다.

## 5단계: 반복되는 행 및 사용자 정의 스타일 추가

반복되는 행과 머리글, 바닥글 같은 다른 특정 테이블 요소에 대한 스타일을 정의할 수도 있습니다.

```csharp
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

 그만큼`RepeatingRowsCount` 테이블이 여러 페이지에 걸쳐 있는 경우 처음 세 행이 반복되도록 합니다.`RepeatingRowsStyle` 이러한 행에 사용자 지정 배경색을 적용합니다.

## 6단계: 테이블 머리글, 본문 및 바닥 요소 추가

이제 표의 머리글, 본문, 바닥글 섹션을 만들고 여기에 콘텐츠를 채워보겠습니다.

```csharp
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

// 헤더 행 만들기
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 5; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText($"Head {colIndex}");
}

// 테이블 본문 채우기
for (int rowIndex = 0; rowIndex < 10; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    for (int colIndex = 0; colIndex < 5; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText($"Cell [{rowIndex}, {colIndex}]");
    }
}
```

 테이블은 머리, 본문, 발의 세 부분으로 나뉩니다. 먼저 다음을 사용하여 헤더 행을 만듭니다.`TableTHElement`그리고 열 제목을 추가합니다. 그런 다음 테이블 본문을 다음과 같이 채웁니다.`TableTDElement`각 셀에 해당 위치가 포함된 라벨을 채웁니다.

## 7단계: 문서 저장

마지막으로 PDF 문서를 지정된 디렉토리에 저장합니다.

```csharp
// 태그가 지정된 PDF 문서를 저장합니다.
document.Save(dataDir + "StyleTableElement.pdf");
```

이 단계에서는 스타일이 지정된 표가 포함된 PDF 파일을 저장하여 문서 생성 프로세스를 마무리합니다.

## 8단계: PDF/UA 준수 확인

문서를 저장한 후에는 해당 문서가 PDF/UA(Universal Accessibility) 표준을 준수하는지 확인하는 것이 중요합니다.

```csharp
// PDF/UA 준수 확인
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine($"PDF/UA compliance: {isPdfUaCompliance}");
```

여기서 문서를 다시 로드하고 PDF/UA 표준에 대해 검증합니다. 규정 준수를 통해 PDF가 접근성 요구 사항을 충족하여 광범위한 사용자에게 적합하게 만듭니다.

## 결론

Aspose.PDF for .NET을 사용하면 PDF 문서에서 표를 만들고 스타일을 지정하는 것이 간단하고 직관적입니다. 이 튜토리얼에 설명된 단계를 따르면 사용자 지정 스타일로 표를 작성하고 PDF가 접근성 표준을 충족하는지 확인할 수 있습니다. 보고서를 생성하든 구조화된 문서를 작성하든 표는 데이터를 명확하게 표현하는 강력한 도구입니다.

## 자주 묻는 질문

### 표 셀 안에 이미지를 추가할 수 있나요?
 예, 다음을 사용하여 표 셀에 이미지를 삽입할 수 있습니다.`Image` 요소.

### 열 너비를 동적으로 조정하려면 어떻게 해야 하나요?
 설정할 수 있습니다`ColumnAdjustment` 재산에`AutoFitToWindow` 콘텐츠에 따라 열 너비를 자동으로 조정합니다.

### 모든 문서가 PDF/UA 규정을 준수해야 합니까?
필수는 아니지만, 높은 접근성 표준이 요구되는 문서에 권장됩니다.

### 특정 행에 다른 스타일을 적용할 수 있나요?
 예, 개별 행이나 셀을 조정하여 사용자 정의할 수 있습니다.`TextState` 또는`BackgroundColor`.

### 태그가 달린 콘텐츠를 사용하면 어떤 이점이 있나요?
태그가 지정된 콘텐츠는 문서 접근성을 개선하고 PDF/UA와 같은 표준을 준수하는 데 도움이 됩니다.