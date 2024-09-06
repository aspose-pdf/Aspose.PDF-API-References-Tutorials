---
title: 테이블 요소 생성
linktitle: 테이블 요소 생성
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET으로 배열 요소를 만드는 단계별 가이드. 테이블이 있는 동적 PDF를 쉽게 생성하세요.
type: docs
weight: 80
url: /ko/net/programming-with-tagged-pdf/create-table-element/
---
이 단계별 가이드에서는 Aspose.PDF for .NET을 사용하여 배열 요소를 만드는 과정을 안내합니다. Aspose.PDF는 PDF 문서를 프로그래밍 방식으로 조작할 수 있는 강력한 라이브러리입니다. 동적 PDF를 생성할 때 배열 요소를 만드는 것은 일반적인 요구 사항이며 Aspose.PDF는 이를 달성하는 쉽고 효율적인 방법을 제공합니다.

이제 코드를 살펴보고 Aspose.PDF for .NET을 사용하여 배열 요소를 만드는 방법을 알아보겠습니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. .NET용 Aspose.PDF 라이브러리가 설치되었습니다.
2. C# 프로그래밍 언어에 대한 기본 지식.

## 1단계: 환경 설정

시작하려면 C# 개발 환경을 열고 새 프로젝트를 만드세요. 프로젝트에 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가했는지 확인하세요.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 만들기

 첫 번째 단계는 다음을 사용하여 새 PDF 문서를 만드는 것입니다.`Document` 수업.

```csharp
// 문서를 생성하세요
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

여기서는 태그가 지정된 콘텐츠의 제목과 언어도 설정합니다.

## 3단계: 배열 요소 생성

다음으로, 배열 요소를 생성하여 문서에 추가해야 합니다. 먼저 루트 구조 요소를 가져온 다음, 다음을 사용하여 새 테이블 요소를 만듭니다.`CreateTableElement` 방법.

```csharp
// 루트 구조 요소를 가져옵니다
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
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
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
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
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

// 태그가 지정된 PDF 문서를 저장합니다.
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA 준수 확인
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### .NET용 Aspose.PDF를 사용하여 테이블 요소 생성을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 생성
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

// 루트 구조 요소 가져오기
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
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
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

// 태그가 지정된 PDF 문서 저장
document.Save(dataDir + "CreateTableElement.pdf");

// PDF/UA 준수 확인
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 결론

Aspose.PDF for .NET을 사용하여 배열 요소를 만드는 방법을 배웠습니다. 이제 이 방법을 사용하여 동적 테이블이 있는 PDF 문서를 생성할 수 있습니다. Aspose.PDF의 더 많은 기능을 탐색하여 그 잠재력을 최대한 발견하세요.

### 자주 묻는 질문

#### 질문: PDF 문서의 배열 요소란 무엇이고, Aspose.PDF for .NET을 사용하여 배열 요소를 만들어야 하는 이유는 무엇입니까?

A: PDF 문서의 배열 요소는 종종 테이블이나 그리드를 만드는 데 사용되는 구조화된 데이터 컬렉션을 나타냅니다. 표 형식 정보나 그리드와 같이 구조화된 데이터 표현이 필요한 동적 PDF를 생성할 때 Aspose.PDF for .NET을 사용하여 배열 요소를 만들어야 할 수도 있습니다.

#### 질문: .NET용 Aspose.PDF는 어떻게 배열 요소를 만드는 과정을 단순화하나요?

A: Aspose.PDF for .NET은 PDF 문서에서 배열 요소(테이블)를 프로그래밍 방식으로 만들고, 사용자 지정하고, 관리할 수 있는 포괄적인 클래스 및 메서드 세트를 제공합니다. 이를 통해 수동 PDF 조작의 필요성이 없어지고 구조화된 데이터 표현의 생성이 간소화됩니다.

#### 질문: Aspose.PDF for .NET을 사용하여 배열 요소를 만드는 데 필요한 주요 단계는 무엇입니까?

A: 주요 단계에는 환경 설정, 문서 생성, 루트 구조 요소 획득, 테이블 요소 생성, 테이블 내 행과 셀 정의, 요소의 서식 및 속성 지정이 포함됩니다. 제공된 코드 예제는 이러한 단계를 보여줍니다.

####  Q: 어떤 역할을 하나요?`taggedContent` object play in creating an array element?

 A: 그`taggedContent` 문서에서 얻은 객체`TaggedContent`속성은 PDF 문서 내에서 태그가 지정된 콘텐츠의 구조를 정의할 수 있게 해줍니다. 여기에는 계층적 방식으로 배열 요소와 그 자식 요소를 만들고 구성하는 것이 포함됩니다.

#### 질문: 코드는 생성된 배열 요소의 접근성과 의미론을 어떻게 보장합니까?

 A: 코드는 다음과 같은 속성을 설정합니다.`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment` , 그리고`ColSpan` 배열 요소의 접근성과 의미론을 강화합니다. 이러한 속성은 잘 구조화되고, 정보가 풍부하고, 시각적으로 매력적인 데이터 표현에 기여합니다.

#### 질문: 배열 요소를 만드는 맥락에서 PDF/UA 규정을 준수하는 것이 왜 중요한가요?

 A: PDF/UA(Universal Accessibility) 준수는 생성된 PDF 문서가 장애가 있는 사용자가 액세스할 수 있고 특정 접근성 표준을 충족하는지 확인합니다. 코드 예제는 다음을 사용하여 PDF/UA 준수를 확인합니다.`Validate` 이 방법을 사용하면 포괄적이고 접근 가능한 문서를 만들 수 있습니다.

#### 질문: 배열 요소의 서식과 모양을 추가로 사용자 지정할 수 있나요?

A: 네, 배경색, 테두리 스타일, 글꼴 크기, 정렬 등의 속성을 조정하여 배열 요소의 서식과 모양을 사용자 지정할 수 있습니다. Aspose.PDF for .NET은 시각적 표현을 요구 사항에 맞게 조정할 수 있는 광범위한 속성을 제공합니다.

#### 질문: 이러한 지식을 확장하여 더 복잡한 표 구조를 만들거나 배열 요소를 더 큰 PDF 문서에 통합할 수 있는 방법은 무엇입니까?

A: 여러 배열 요소 병합, 중첩 테이블 생성, 머리글 및 바닥글 추가, 배열 요소를 더 큰 PDF 레이아웃에 통합하는 것과 같은 Aspose.PDF for .NET의 추가 기능을 탐색하여 이러한 지식을 확장할 수 있습니다. 라이브러리의 설명서와 예제는 이러한 고급 시나리오에 대한 지침을 제공합니다.

#### 질문: 데이터베이스나 스프레드시트와 같은 외부 소스에서 데이터를 가져와서 배열 요소를 채울 수 있나요?

A: 네, 외부 소스에서 데이터를 가져와서 배열 요소를 채울 수 있습니다. C#에서 데이터 검색 및 변환 기술을 사용하여 데이터베이스, 스프레드시트 또는 기타 소스에서 데이터를 가져온 다음 그에 따라 배열 요소를 채울 수 있습니다.

#### 질문: 이 튜토리얼에서 얻은 지식을 사용하여 프로그래밍 방식으로 만든 PDF 문서의 품질과 유용성을 어떻게 향상시킬 수 있습니까?

A: 이 튜토리얼에서 얻은 지식을 통해 PDF 문서에서 구조화되고 시각적으로 매력적인 배열 요소(표)를 만들 수 있습니다. 이러한 기술을 통합하면 동적으로 생성된 PDF의 가독성, 접근성 및 사용자 경험을 개선하여 보다 유익하고 사용자 친화적으로 만들 수 있습니다.