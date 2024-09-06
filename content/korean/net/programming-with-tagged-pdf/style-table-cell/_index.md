---
title: 스타일 테이블 셀
linktitle: 스타일 테이블 셀
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET으로 테이블 셀의 스타일을 지정하는 방법을 알아보세요. 테이블을 만들고 사용자 정의하는 단계별 가이드입니다.
type: docs
weight: 160
url: /ko/net/programming-with-tagged-pdf/style-table-cell/
---
Aspose.PDF for .NET을 사용하여 표 셀을 서식 지정하는 방법에 대한 자세한 튜토리얼에 오신 것을 환영합니다. 이 가이드에서는 제공된 C# 소스 코드의 각 단계를 자세히 설명하여 표 셀의 스타일을 지정하는 방법을 이해하는 데 도움을 드립니다. 시작하기 전에 Aspose.PDF for .NET을 설치하고 개발 환경을 설정했는지 확인하세요.

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
taggedContent.SetTitle("Example of table cell formatting");
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
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

우리는 새로운 배열 구조 요소를 생성하여 루트 구조 요소에 추가했습니다. 또한 테이블 헤더, 본문, 푸터 요소도 생성했습니다.

## 5단계: 테이블 헤더 추가

이 단계에서는 표에 표 머리글을 추가합니다.

```csharp
// 표의 행과 열의 수
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

// 테이블 헤더 행을 만듭니다
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

우리는 표의 머리글 행을 만들고 배경색, 테두리, 여백 및 정렬과 같은 서식 속성이 있는 머리글 셀을 추가했습니다.

## 6단계: 테이블 본문 행 추가

이제 표 본문 행을 표에 추가해 보겠습니다.
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

루프를 사용하여 각 테이블 셀을 반복하여 테이블 본문에 행을 추가했습니다. 각 셀에 대한 서식 속성(예: 배경색, 테두리, 여백, 텍스트 정렬 등)을 설정했습니다.

## 7단계: 바닥글 추가

마지막으로 표에 표 바닥글을 추가합니다.

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

우리는 표에 바닥글을 만들고 텍스트가 있는 바닥글 셀을 추가했습니다.



## 8단계: 태그가 지정된 PDF 문서 저장

이제 스타일이 지정된 표로 문서를 만들었으므로, 이를 태그가 지정된 PDF 문서로 저장하겠습니다.

```csharp
// 태그가 지정된 PDF 문서를 저장합니다.
document.Save(dataDir + "StyleTableCell.pdf");
```

태그가 지정된 PDF 문서를 지정된 디렉토리에 저장했습니다.

## 9단계: PDF/UA 준수 검증

다음으로, 문서의 PDF/UA 적합성을 검증하겠습니다.

```csharp
// PDF/UA 준수 확인
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

태그가 지정된 PDF 문서를 업로드하고 XML 보고서를 생성하여 PDF/UA 준수 여부를 검증했습니다.

### .NET용 Aspose.PDF를 사용한 Style Table Cell의 샘플 소스 코드 
```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 생성
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

// 태그가 지정된 PDF 문서 저장
document.Save(dataDir + "StyleTableCell.pdf");

// PDF/UA 준수 확인
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 표 셀의 스타일을 지정하는 방법을 알아보았습니다. 문서를 만들고, 헤더, 본문 행, 푸터가 있는 표를 추가하고, 셀 스타일을 사용자 지정하는 방법을 알아보았습니다. 마지막으로 태그가 지정된 PDF 문서를 저장하고 PDF/UA 준수 여부를 검증했습니다. 이제 Aspose.PDF for .NET을 사용하여 .NET 애플리케이션에서 표를 만들고 스타일을 지정할 수 있습니다.

### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 표 셀을 서식 지정하는 방법에 대한 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 표 셀의 스타일을 지정하는 방법에 대한 포괄적인 가이드를 제공하는 것을 목표로 합니다. 단계별 지침과 C# 소스 코드 예제를 다루어 표 셀 서식을 이해하고 구현하는 데 도움을 줍니다.

#### 질문: 이 튜토리얼을 따르기 위한 전제 조건은 무엇입니까?

A: 시작하기 전에 Aspose.PDF for .NET을 설치하고 개발 환경을 설정했는지 확인하세요. 여기에는 Aspose.PDF 라이브러리를 참조하도록 프로젝트를 구성하는 것이 포함됩니다.

#### 질문: Aspose.PDF for .NET을 사용하여 새 PDF 문서를 만들려면 어떻게 해야 하나요?

A: 새 PDF 문서를 만들려면 다음을 인스턴스화해야 합니다.`Document` Aspose.PDF 라이브러리의 개체입니다. 제공된 C# 소스 코드는 문서를 만들고 제목과 언어를 설정하는 방법을 보여줍니다.

#### 질문: PDF 문서에서 루트 구조 요소의 중요성은 무엇인가요?

A: 루트 구조 요소는 다른 구조 요소의 컨테이너 역할을 하며 PDF 문서의 내용을 구성하고 분류하는 데 도움이 됩니다. 문서의 논리적 구조를 확립하는 데 중요한 역할을 합니다.

#### 질문: Aspose.PDF for .NET을 사용하여 테이블 구조 요소를 만들고 모양을 사용자 지정하려면 어떻게 해야 합니까?

 A: 다음을 사용하여 테이블 구조 요소를 만들 수 있습니다.`CreateTableElement()` 방법. 제공된 소스 코드는 배경색, 테두리, 여백, 정렬과 같은 속성을 설정하여 헤더, 본문, 푸터를 포함한 테이블의 모양을 사용자 지정하는 방법을 보여줍니다.

#### 질문: 표 본문에 여러 개의 행과 열을 추가하고 서식을 사용자 지정할 수 있나요?

A: 네, 이 튜토리얼은 루프를 사용하여 테이블 본문에 여러 행과 열을 추가하는 방법을 보여줍니다. 또한 배경색, 테두리, 텍스트 정렬, 글꼴 스타일 등과 같은 셀 서식을 사용자 지정하는 예도 제공합니다.

#### 질문: PDF/UA 준수 여부를 검증하는 목적은 무엇이며, 어떻게 이 검증을 수행할 수 있습니까?

 A: PDF/UA 준수를 검증하면 PDF 문서가 접근성 표준을 준수하여 장애가 있는 사용자가 더 쉽게 접근할 수 있습니다. 이 튜토리얼에서는 다음을 사용하여 PDF/UA 준수를 검증하는 방법을 보여줍니다.`Validate()` 방법을 사용하여 XML 보고서를 생성합니다.

#### 질문: 이러한 개념을 내 .NET 애플리케이션에 어떻게 적용할 수 있나요?

A: 제공된 C# 소스 코드 예제를 가이드로 사용하여 자신의 .NET 애플리케이션에서 테이블 셀 서식을 구현할 수 있습니다. 필요에 따라 코드를 사용자 정의하여 요구 사항에 맞게 조정하고 프로젝트에 통합합니다.

#### 질문: PDF 문서에서 표 셀의 스타일을 지정하는 데 권장되는 모범 사례가 있나요?

A: 표 셀을 스타일링할 때는 접근성 요구 사항을 포함하여 대상 고객의 요구 사항을 고려하세요. 대조적인 색상, 적절한 글꼴, 명확한 셀 정렬을 사용하여 가독성을 향상하세요. 또한 PDF/UA 준수 여부를 검증하여 접근성 표준이 충족되는지 확인하세요.

#### 질문: PDF 문서 조작을 위해 .NET용 Aspose.PDF의 다른 어떤 기능을 활용할 수 있나요?

A: Aspose.PDF for .NET은 텍스트 추출, 이미지 삽입, 양식 필드 관리, 디지털 서명 등을 포함하여 PDF 문서 조작을 위한 광범위한 기능을 제공합니다. 추가 기능에 대해 알아보려면 공식 문서와 리소스를 탐색하세요.
