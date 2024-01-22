---
title: 스타일 테이블 셀
linktitle: 스타일 테이블 셀
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 표 셀의 스타일을 지정하는 방법을 알아보세요. 테이블 생성 및 사용자 정의에 대한 단계별 가이드입니다.
type: docs
weight: 160
url: /ko/net/programming-with-tagged-pdf/style-table-cell/
---
.NET용 Aspose.PDF를 사용하여 표 셀 서식을 지정하는 방법에 대한 자세한 튜토리얼에 오신 것을 환영합니다. 이 가이드에서는 표 셀의 스타일을 지정하는 방법을 이해하는 데 도움이 되도록 제공된 C# 소스 코드의 각 단계를 자세히 설명합니다. 시작하기 전에 .NET용 Aspose.PDF를 설치하고 개발 환경을 설정했는지 확인하세요.

## 1단계: 환경 설정

시작하기 전에 Aspose.PDF for .NET을 사용하도록 개발 환경을 구성했는지 확인하세요. 여기에는 Aspose.PDF 라이브러리 설치 및 이를 참조하도록 프로젝트 구성이 포함됩니다.

## 2단계: 문서 만들기

이 단계에서는 새 문서 개체 Aspose.PDF를 만듭니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서작성
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table cell formatting");
taggedContent.SetLanguage("fr-FR");
```

새 문서를 만들고 문서 제목과 언어를 설정했습니다.

## 3단계: 루트 구조 요소 얻기

이 단계에서는 문서의 루트 구조 요소를 가져옵니다.

```csharp
//루트 구조 요소 얻기
StructureElement rootElement = taggedContent.RootElement;
```

우리는 배열 요소의 컨테이너 역할을 할 루트 구조 요소를 얻었습니다.

## 4단계: 배열 구조 요소 생성

이제 문서에 대한 새 테이블 구조 요소를 만들어 보겠습니다.

```csharp
// 배열 구조 요소 생성
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

새로운 배열 구조 요소를 생성하여 루트 구조 요소에 추가했습니다. 또한 표 머리글, 본문 및 바닥글 요소도 만들었습니다.

## 5단계: 테이블 헤더 추가하기

이 단계에서는 테이블 헤더를 테이블에 추가합니다.

```csharp
// 테이블의 행과 열 수
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// 테이블 헤더 행 생성
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

테이블의 머리글 행을 만들고 배경색, 테두리, 여백 및 정렬과 같은 서식 속성이 있는 머리글 셀을 추가했습니다.

## 6단계: 표 본문 행 추가하기

이제 테이블에 테이블 본문 행을 추가해 보겠습니다.
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         int colSpan = 1;
         int rowSpan = 1;

         if (colIndex == 1 && rowIndex == 1)
         {
             colSpan = 2;
             rowSpan = 2;
         }
         else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
         {
             keep on going;
         }
         else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
         {
             keep on going;
         }

         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
         tdElement.BackgroundColor = Color.Yellow;
         tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
         tdElement.IsNoBorder = false;
         tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
         tdElement.Alignment = HorizontalAlignment.Center;

         TextState cellTextState = new TextState();
         cellTextState.ForegroundColor = Color.DarkBlue;
         cellTextState.FontSize = 7.5F;
         cellTextState.FontStyle = FontStyles.Bold;
         cellTextState.Font = FontRepository.FindFont("Arial");

         tdElement. DefaultCellTextState = cellTextState;
         tdElement.IsWordWrapped = true;
         tdElement.VerticalAlignment = VerticalAlignment.Center;
         tdElement.ColSpan = colSpan;
         tdElement. RowSpan = rowSpan;
     }
}
```

각 테이블 셀을 반복하는 루프를 사용하여 테이블 본문에 행을 추가했습니다. 배경색, 테두리, 여백, 텍스트 정렬 등과 같은 각 셀의 서식 속성을 설정합니다.

## 7단계: 바닥글 추가

마지막으로 테이블 바닥글을 테이블에 추가하겠습니다.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

테이블의 바닥글을 만들고 텍스트가 있는 바닥글 셀을 추가했습니다.



## 8단계: 태그가 있는 PDF 문서 저장

이제 스타일이 지정된 표를 사용하여 문서를 만들었으므로 태그가 있는 PDF 문서로 저장하겠습니다.

```csharp
// 태그가 있는 PDF 문서 저장
document.Save(dataDir + "StyleTableCell.pdf");
```

태그가 지정된 PDF 문서를 지정된 디렉토리에 저장했습니다.

## 9단계: PDF/UA 규정 준수 확인

다음으로 문서의 PDF/UA 적합성을 검증하겠습니다.

```csharp
// PDF/UA 규정 준수 확인
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

태그가 지정된 PDF 문서를 업로드하고 XML 보고서를 생성하여 PDF/UA 준수 여부를 확인했습니다.

### .NET용 Aspose.PDF를 사용하는 스타일 테이블 셀의 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 만들기
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

// 루트 구조 요소 가져오기
StructureElement rootElement = taggedContent.RootElement;

// 테이블 구조 요소 생성
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

// 태그가 있는 PDF 문서 저장
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA 준수 확인
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 표 셀의 스타일을 지정하는 방법을 배웠습니다. 문서를 만들고, 머리글, 본문 행, 바닥글이 포함된 표를 추가하고, 셀 스타일을 사용자 정의하는 방법을 살펴보았습니다. 마지막으로 태그가 지정된 PDF 문서를 저장하고 PDF/UA 준수 여부를 확인했습니다. 이제 .NET용 Aspose.PDF를 사용하여 .NET 애플리케이션에서 테이블을 생성하고 스타일을 지정할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 표 셀 서식을 지정하는 방법에 대한 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼의 목적은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 표 셀의 스타일을 지정하는 방법에 대한 포괄적인 가이드를 제공하는 것입니다. 표 셀 서식을 이해하고 구현하는 데 도움이 되는 단계별 지침과 C# 소스 코드 예제를 다룹니다.

#### Q: 이 튜토리얼을 따르기 위한 전제 조건은 무엇입니까?

A: 시작하기 전에 Aspose.PDF for .NET을 설치하고 개발 환경을 설정했는지 확인하세요. 여기에는 Aspose.PDF 라이브러리를 참조하도록 프로젝트를 구성하는 것이 포함됩니다.

#### Q: .NET용 Aspose.PDF를 사용하여 새 PDF 문서를 어떻게 생성합니까?

A: 새 PDF 문서를 만들려면`Document` Aspose.PDF 라이브러리의 개체입니다. 제공된 C# 소스 코드는 문서를 만들고 제목과 언어를 설정하는 방법을 보여줍니다.

#### Q: PDF 문서에서 루트 구조 요소의 중요성은 무엇입니까?

답변: 루트 구조 요소는 다른 구조 요소에 대한 컨테이너 역할을 하여 PDF 문서의 내용을 구성하고 분류하는 데 도움을 줍니다. 문서의 논리적 구조를 확립하는 데 중요한 역할을 합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 테이블 구조 요소를 만들고 모양을 사용자 정의하려면 어떻게 해야 합니까?

 A: 다음을 사용하여 테이블 구조 요소를 생성할 수 있습니다.`CreateTableElement()` 방법. 제공된 소스 코드는 배경색, 테두리, 여백, 정렬 등의 속성을 설정하여 머리글, 본문, 바닥글을 포함한 표의 모양을 사용자 지정하는 방법을 보여줍니다.

#### Q: 표 본문에 여러 행과 열을 추가하고 서식을 사용자 지정할 수 있나요?

A: 예, 튜토리얼에서는 루프를 사용하여 테이블 본문에 여러 행과 열을 추가하는 방법을 보여줍니다. 또한 배경색, 테두리, 텍스트 정렬, 글꼴 스타일 등과 같은 셀 서식을 사용자 정의하는 예도 제공합니다.

#### Q: PDF/UA 규정 준수 여부를 검증하는 목적은 무엇이며, 이 검증을 어떻게 수행할 수 있습니까?

 A: PDF/UA 준수 여부를 확인하면 PDF 문서가 접근성 표준을 준수하므로 장애가 있는 사용자가 더 쉽게 접근할 수 있습니다. 튜토리얼에서는 다음을 사용하여 PDF/UA 적합성을 검증하는 방법을 보여줍니다.`Validate()` 방법을 사용하여 XML 보고서를 생성합니다.

#### Q: 이러한 개념을 내 .NET 애플리케이션에 어떻게 적용할 수 있습니까?

A: 제공된 C# 소스 코드 예제를 자신의 .NET 애플리케이션에서 표 셀 형식 지정을 구현하기 위한 지침으로 사용할 수 있습니다. 요구 사항에 맞게 필요에 따라 코드를 사용자 정의하고 프로젝트에 통합하십시오.

#### Q: PDF 문서의 표 셀 스타일을 지정하는 데 권장되는 모범 사례가 있습니까?

A: 표 셀의 스타일을 지정할 때 접근성 요구 사항을 포함하여 청중의 요구 사항을 고려하십시오. 대비되는 색상, 적절한 글꼴, 명확한 셀 정렬을 사용하여 가독성을 높입니다. 또한 PDF/UA 규정 준수 여부를 검증하여 접근성 표준이 충족되는지 확인하세요.

#### Q: PDF 문서 조작을 위해 Aspose.PDF for .NET의 다른 어떤 기능을 탐색할 수 있습니까?

답변: .NET용 Aspose.PDF는 텍스트 추출, 이미지 삽입, 양식 필드 관리, 디지털 서명 등을 포함하여 PDF 문서 조작을 위한 광범위한 기능을 제공합니다. 추가 기능에 대해 알아보려면 공식 문서와 리소스를 살펴보세요.
