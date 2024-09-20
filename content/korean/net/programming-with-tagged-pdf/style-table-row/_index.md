---
title: 스타일 테이블 행
linktitle: 스타일 테이블 행
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF의 표 행에 스타일을 지정하는 방법을 단계별 가이드와 함께 알아보고, 문서 서식을 쉽게 개선해 보세요.
type: docs
weight: 180
url: /ko/net/programming-with-tagged-pdf/style-table-row/
---
## 소개

잘 구성되고 아름답게 포맷된 PDF 문서를 만드는 데 있어 Aspose.PDF for .NET은 꼭 필요한 솔루션입니다. 보고서, 송장을 자동화하든 동적 테이블을 만들든 다양한 스타일로 테이블을 포맷하는 것이 세련된 문서의 핵심입니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 테이블 행의 스타일을 지정하는 방법을 자세히 알아보겠습니다. 걱정하지 마세요. 커피 한 잔을 마시며 나누는 좋은 대화처럼 단계별로 안내해 드리겠습니다!

## 필수 조건

본론으로 들어가기 전에, 모든 것을 제대로 준비했는지 확인해 보겠습니다. 다음이 필요합니다.

1. .NET 라이브러리용 Aspose.PDF  
    아직 가지고 있지 않다면 다음에서 가져올 수 있습니다.[여기](https://releases.aspose.com/pdf/net/) . 또한 다음을 얻을 수 있습니다.[무료 체험](https://releases.aspose.com/) 시작하려면 클릭하세요.
2. 개발 환경  
   Visual Studio나 원하는 C# IDE를 설정하세요. .NET도 설치해야 하지만, 아마 이미 잘 알고 계실 겁니다.
3. C# 및 .NET에 대한 기본 지식  
   C#에 대한 좋은 이해는 이 튜토리얼을 아주 쉽게 만들어 줄 것입니다. 하지만 걱정하지 마세요. 각 단계를 자세히 설명해 드리겠습니다!

## 패키지 가져오기

Aspose.PDF 작업을 시작하기 전에 필요한 네임스페이스를 가져와야 합니다. C# 프로젝트에서 다음을 포함해야 합니다.

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이러한 기능은 표를 만들고 스타일을 지정하는 데 필수적이며, 물론 규정 준수를 위해 태그가 지정된 콘텐츠를 처리하는 데도 필수적입니다.

이제 작업을 단계별로 나누어 전문가처럼 표 행의 스타일을 지정해 보겠습니다!

## 1단계: 새 PDF 문서 만들기

우선 가장 먼저: 새로운 PDF 문서를 만들어 보겠습니다. 이 문서는 스타일이 지정된 모든 표 행을 보관합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 생성
Document document = new Document();
```

 여기서 우리는 단순히 새로운 것을 초기화하고 있습니다`Document` PDF 파일을 나타낼 객체입니다. 출력 파일을 저장할 디렉토리 경로를 설정해야 합니다.

## 2단계: 태그가 지정된 콘텐츠 작업

PDF를 접근성을 위해 구조화하기 위해 태그가 지정된 콘텐츠로 작업합니다. 이는 표와 같은 구조화된 요소를 만드는 데 도움이 되며 PDF/UA와 같은 접근성 표준을 준수하도록 합니다.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");
```

여기서는 PDF의 태그가 지정된 콘텐츠에 대한 제목과 언어를 설정합니다. PDF에 이름을 지정하고 어떤 언어를 말해야 하는지 알려주는 것과 같습니다!

## 3단계: 테이블 구조 정의

다음으로, 우리가 만들려는 테이블의 구조를 정의해 보겠습니다. 모든 테이블에는 헤더, 본문, 푸터가 필요합니다. 잘 정리된 블로그 게시물과 매우 비슷합니다!

```csharp
// 루트 구조 요소 가져오기
StructureElement rootElement = taggedContent.RootElement;

// 테이블 구조 요소 생성
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

여기서 우리가 하는 일은 헤더가 있는 테이블을 만드는 것입니다.`THead`), 몸 (`TBody`), 및 바닥글(`TFoot`). 이 요소들은 행을 유지하게 될 것입니다.

## 4단계: 테이블 헤더 행 추가

헤더가 없는 테이블은 제목이 없는 책과 같습니다. 먼저 헤더 행을 만들어 데이터의 맥락을 제공합시다.

```csharp
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTHElement thElement = headTrElement.CreateTH();
    thElement.SetText(String.Format("Head {0}", colIndex));
}
```

여기서 우리는 루프를 실행하고 세 개의 헤더 셀을 추가합니다.`TableTHElement`), 각각에 설명 텍스트를 제공합니다. 간단하죠?

## 5단계: 스타일이 지정된 본문 행 추가

이제 재밌는 부분인 행 스타일링이 시작됩니다! 사용자 지정 스타일로 7개의 행을 만들어 보겠습니다. 배경색, 테두리, 패딩, 텍스트 정렬을 설정합니다.

```csharp
for (int rowIndex = 0; rowIndex < 7; rowIndex++)
{
    TableTRElement trElement = tableTBodyElement.CreateTR();
    trElement.AlternativeText = String.Format("Row {0}", rowIndex);
    trElement.BackgroundColor = Color.LightGoldenrodYellow;
    trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
    trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
    trElement.MinRowHeight = 100.0;
    trElement.FixedRowHeight = 120.0;
    trElement.IsInNewPage = (rowIndex % 3 == 1);
    trElement.IsRowBroken = true;

    for (int colIndex = 0; colIndex < 3; colIndex++)
    {
        TableTDElement tdElement = trElement.CreateTD();
        tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
    }
}
```

- 배경색: 전문적이면서도 따뜻한 느낌을 주기 위해 밝은 황금빛 노란색을 사용했습니다.
- 테두리: 각 행에는 뚜렷한 느낌을 주기 위해 짙은 회색 바깥쪽 테두리와 파란색 셀 테두리가 적용됩니다.
- 높이 및 패딩: 행 높이가 설정되고, 깔끔한 모양을 위해 패딩이 추가됩니다.
- 페이지 나누기: 표를 더 읽기 쉽게 하기 위해 두 번째 행마다 새 페이지에서 시작합니다.

## 6단계: 바닥글 행 추가

헤더와 마찬가지로 푸터는 테이블을 고정합니다. 푸터를 하나 만들어 봅시다.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (int colIndex = 0; colIndex < 3; colIndex++)
{
    TableTDElement tdElement = footTrElement.CreateTD();
    tdElement.SetText(String.Format("Foot {0}", colIndex));
}
```

우리는 단순히 3개의 푸터 셀을 반복하고 약간의 텍스트를 추가합니다. 푸터의 대체 텍스트는 "Foot Row"로 접근 가능하게 만듭니다.

## 7단계: PDF 문서 저장

이제 테이블이 모두 준비되었으니, 걸작을 저장할 시간입니다!

```csharp
document.Save(dataDir + "StyleTableRow.pdf");
```

이렇게 하면 방금 스타일을 지정한 모든 아름다운 표 행이 포함된 PDF가 저장됩니다.

## 8단계: PDF/UA 준수 확인

PDF가 접근성 표준을 준수하는지 확인하기 위해 PDF/UA 준수 여부를 검증합니다.

```csharp
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));
```

이렇게 하면 PDF가 PDF/UA 표준을 충족하여 모든 사람이 접근할 수 있습니다. 접근성이 게임의 이름입니다!

## 결론

이제 다 되었습니다! Aspose.PDF for .NET을 사용하여 몇 줄의 코드만으로 PDF에 완전히 스타일이 적용된 표를 만들었습니다. 머리글에서 바닥글까지 각 행에 스타일을 지정하고 접근성 요소를 추가했으며 문서의 규정 준수 여부도 검증했습니다. 기업 보고서, 프레젠테이션을 작업하든 PDF로 재미있게 놀든 이 가이드가 도와드립니다. 이제 프로처럼 표 스타일을 지정해 보세요!

## 자주 묻는 질문

### 표의 글꼴 스타일도 변경할 수 있나요?  
 네! 다음을 사용하여 글꼴 스타일을 수정할 수 있습니다.`TextState` 각 셀에 대한 객체를 제공하여 완전한 사용자 정의가 가능합니다.

### 내 표에 열을 더 추가하려면 어떻게 해야 하나요?  
 그냥 조정하세요`colCount`변수를 추가하고 헤더, 본문, 푸터에 대한 루프에 셀을 추가합니다.

### 행 높이를 설정하지 않으면 어떻게 되나요?  
행 높이를 설정하지 않으면 표는 콘텐츠에 따라 자동으로 조정됩니다.

### 이것을 동적인 행 개수에 사용할 수 있나요?  
물론입니다! 데이터베이스나 다른 소스에서 데이터를 가져와서 행과 열 개수를 동적으로 조정할 수 있습니다.

### .NET용 Aspose.PDF는 무료로 사용할 수 있나요?  
 .NET용 Aspose.PDF는 라이센스가 있는 제품이지만 다음을 사용하여 시도할 수 있습니다.[무료 체험](https://releases.aspose.com/) 또는 얻을[임시 면허](https://purchase.aspose.com/temporary-license/).