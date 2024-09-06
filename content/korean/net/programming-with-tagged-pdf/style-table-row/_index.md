---
title: 스타일 테이블 행
linktitle: 스타일 테이블 행
second_title: .NET API 참조를 위한 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 테이블 행을 사용자 지정하는 방법을 단계별 가이드로 알아보고 행의 스타일과 서식을 지정하세요.
type: docs
weight: 180
url: /ko/net/programming-with-tagged-pdf/style-table-row/
---
이 자세한 튜토리얼에서는 제공된 C# 소스 코드를 단계별로 안내하여 .NET용 Aspose.PDF를 사용하여 테이블 행을 포맷합니다. 아래 지침에 따라 테이블 행 스타일과 속성을 사용자 지정하는 방법을 이해합니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.PDF for .NET을 사용하도록 개발 환경을 구성했는지 확인하세요. 여기에는 Aspose.PDF 라이브러리를 설치하고 이를 참조하도록 프로젝트를 구성하는 것이 포함됩니다.

## 2단계: 문서 만들기

이 단계에서는 Aspose.PDF라는 새 문서 개체를 만듭니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 생성
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of Table Row Formatting");
taggedContent.SetLanguage("fr-FR");
```

새 문서를 만들고 문서 제목과 언어를 설정했습니다.

## 3단계: 루트 구조 요소 얻기

이 단계에서는 문서의 루트 구조 요소를 가져옵니다.

```csharp
//루트 구조 요소를 얻습니다
StructureElement rootElement = taggedContent.RootElement;
```

배열 요소를 담는 컨테이너 역할을 할 루트 구조 요소를 얻었습니다.

## 4단계: 배열 구조 요소 생성

이제 문서에 대한 새로운 테이블 구조 요소를 만들어 보겠습니다.

```csharp
// 배열 구조 요소 생성
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

새로운 배열 구조 요소를 생성하여 루트 구조 요소에 추가했습니다.

## 5단계: 테이블 행 스타일 및 속성 사용자 지정

이 단계에서는 테이블 행 스타일과 속성을 사용자 지정합니다.

```csharp
// 테이블 행 스타일 및 속성 사용자 정의
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;

// 테이블 헤더 행을 만듭니다
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

// 표 본문의 행을 사용자 정의합니다.
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);
     trElement.BackgroundColor = Color.LightGoldenrodYellow;
     trElement.Border = new BorderInfo(BorderSide.All, 0.75F, Color.DarkGray);
     trElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.Blue);
     trElement.MinRowHeight = 100.0;
     trElement.FixedRowHeight = 120.0;
     trElement. IsInNewPage = (rowIndex % 3 == 1);
     trElement.IsRowBroken = true;
     TextState cellTextState = new TextState();
     cellTextState.ForegroundColor = Color.Red;
     trElement. DefaultCellTextState = cellTextState;
     trElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     trElement.VerticalAlignment = VerticalAlignment.Bottom;

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

// 테이블의 바닥글 줄을 만듭니다.
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

배경색, 테두리, 행 높이, 페이지 번호, 기본 셀 스타일 등 테이블 행의 다양한 측면을 사용자 지정했습니다.

## 6단계: 태그가 지정된 PDF 문서 저장

이제 스타일이 지정된 표 행이 있는 문서를 만들었으므로 이를 태그가 지정된 PDF 문서로 저장하겠습니다.
```csharp
// 태그가 지정된 PDF 문서를 저장합니다.
document.Save(dataDir + "StyleTableRow.pdf");
```

태그가 지정된 PDF 문서를 지정된 디렉토리에 저장했습니다.

## 7단계: PDF/UA 준수 검증

다음으로, 문서의 PDF/UA 적합성을 검증하겠습니다.

```csharp
// PDF/UA 준수 확인
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

태그가 지정된 PDF 문서를 업로드하고 XML 보고서를 생성하여 PDF/UA 준수 여부를 검증했습니다.


### .NET용 Aspose.PDF를 사용한 Style Table Row의 샘플 소스 코드 
```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 생성
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table row style");
taggedContent.SetLanguage("en-US");

// 루트 구조 요소 가져오기
StructureElement rootElement = taggedContent.RootElement;

// 테이블 구조 요소 생성
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 7;
int colCount = 3;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
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
	TextState cellTextState = new TextState();
	cellTextState.ForegroundColor = Color.Red;
	trElement.DefaultCellTextState = cellTextState;
	trElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	trElement.VerticalAlignment = VerticalAlignment.Bottom;
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// 태그가 지정된 PDF 문서 저장
document.Save(dataDir + "StyleTableRow.pdf");

// PDF/UA 준수 확인
document = new Document(dataDir + "StyleTableRow.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableRow.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET으로 표 행을 포맷하는 방법을 배웠습니다. 표 행 스타일과 속성을 사용자 지정하고, 헤더, 본문 행, 푸터를 추가하고, 태그가 지정된 PDF 문서를 저장하고, PDF/UA 준수 여부를 검증했습니다.

### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 표 행을 서식 지정하는 방법에 대한 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼의 목적은 Aspose.PDF for .NET을 사용하여 PDF 문서의 표 행을 포맷하는 과정을 안내하는 것입니다. 단계별 지침과 C# 소스 코드 예제를 제공하여 표 행 스타일과 속성을 사용자 지정하는 데 도움이 됩니다.

#### 질문: 이 튜토리얼을 따르기 위한 전제 조건은 무엇입니까?

A: 시작하기 전에 Aspose.PDF for .NET을 사용하도록 개발 환경을 설정했는지 확인하세요. 여기에는 Aspose.PDF 라이브러리를 설치하고 프로젝트를 구성하여 참조하도록 하는 것이 포함됩니다.

#### 질문: Aspose.PDF for .NET을 사용하여 새 PDF 문서를 만들고 제목과 언어를 설정하려면 어떻게 해야 합니까?

 A: 새 PDF 문서를 만들려면 다음을 만들어야 합니다.`Document` Aspose.PDF 라이브러리의 개체입니다. 튜토리얼의 제공된 C# 소스 코드는 문서를 만들고 제목과 언어 속성을 설정하는 방법을 보여줍니다.

#### 질문: PDF 문서에서 루트 구조 요소의 중요성은 무엇인가요?

A: 루트 구조 요소는 다른 구조 요소의 컨테이너 역할을 하며 PDF 문서의 내용을 구성하고 분류하는 데 도움이 됩니다. 문서의 논리적 구조를 확립하는 데 중요한 역할을 합니다.

#### 질문: Aspose.PDF for .NET을 사용하여 표 행을 서식 지정하는 표 구조 요소를 만들고 사용자 지정하려면 어떻게 해야 합니까?

A: 이 튜토리얼에서는 테이블 구조 요소를 만들고 테이블 행을 포맷하기 위해 속성을 사용자 지정하는 방법을 설명합니다. 배경색, 테두리, 행 높이, 페이지 번호, 기본 셀 스타일 등과 같은 측면을 다룹니다.

#### 질문: 표 행 내 개별 셀의 스타일과 속성을 사용자 지정할 수 있나요?

A: 네, 테이블 행 내의 개별 셀의 스타일과 속성을 사용자 지정할 수 있습니다. 이 튜토리얼은 서식이 지정된 테이블 행 내의 테이블 셀에 대한 배경색, 테두리, 텍스트 색상, 패딩 등의 속성을 설정하는 방법을 보여줍니다.

#### 질문: 서식이 지정된 표 행에 머리글, 본문 행, 바닥글을 추가하려면 어떻게 해야 하나요?

A: 이 튜토리얼은 테이블 구조 요소에 헤더, 본문 행, 푸터를 만들고 추가하는 예를 제공합니다. 이러한 요소는 튜토리얼에 설명된 속성을 사용하여 추가로 사용자 정의할 수 있습니다.

#### 질문: PDF/UA 준수란 무엇이며, 태그가 지정된 PDF 문서에 대해 어떻게 검증할 수 있습니까?

 A: PDF/UA 준수는 PDF 문서가 접근성 표준을 준수하여 장애가 있는 사용자가 더 쉽게 접근할 수 있도록 보장합니다. 이 튜토리얼은 다음을 사용하여 PDF/UA 준수를 검증하는 방법을 보여줍니다.`Validate()` 방법을 사용하여 XML 준수 보고서를 생성합니다.

#### 질문: 이러한 개념을 내 .NET 애플리케이션에 어떻게 통합할 수 있습니까?

A: 제공된 C# 소스 코드 예제를 가이드로 사용하여 자신의 .NET 애플리케이션에서 테이블 행 서식을 구현할 수 있습니다. 요구 사항에 맞게 코드를 수정하고 조정하여 프로젝트에 통합합니다.

#### 질문: PDF 문서의 표 행을 서식 지정하는 데 권장되는 모범 사례가 있나요?

A: 표 행을 서식 지정할 때 콘텐츠의 가독성과 접근성을 고려하세요. 색상이 충분한 대비를 갖고 있는지, 명확하고 읽기 쉬운 글꼴을 사용하고, 일관된 레이아웃을 유지하세요. PDF/UA 준수를 검증하여 접근성 표준이 충족되는지 확인하세요.

#### 질문: PDF 문서 사용자 정의를 위해 .NET용 Aspose.PDF의 다른 어떤 기능을 살펴볼 수 있나요?

A: Aspose.PDF for .NET은 텍스트 조작, 이미지 삽입, 양식 필드 관리, 디지털 서명, 주석 등을 포함하여 PDF 문서 사용자 지정을 위한 광범위한 기능을 제공합니다. 추가 기능을 탐색하려면 공식 문서와 리소스를 참조하세요.