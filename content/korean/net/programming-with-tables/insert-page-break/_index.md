---
title: PDF 파일에 페이지 나누기 삽입
linktitle: PDF 파일에 페이지 나누기 삽입
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 페이지 나누기를 삽입하는 방법을 알아보세요.
type: docs
weight: 110
url: /ko/net/programming-with-tables/insert-page-break/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 페이지 나누기를 삽입하는 방법을 알아봅니다. C# 소스 코드를 단계별로 설명합니다. 이 튜토리얼을 마치면 PDF 문서의 표에서 특정 줄 뒤에 페이지 나누기를 추가하는 방법을 알게 됩니다. 시작해 봅시다!

## 1단계: 환경 설정
Aspose.PDF for .NET으로 C# 개발 환경을 구성했는지 확인하세요. 라이브러리에 참조를 추가하고 필요한 네임스페이스를 가져옵니다.

## 2단계: 문서 및 표 만들기
새 Document 인스턴스를 만들고 이 문서에 페이지를 추가합니다. 다음으로 PDF 문서에서 테이블을 나타내는 Table 인스턴스를 만듭니다. 또한 테이블의 테두리 스타일을 정의합니다.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## 3단계: 표에 행 추가
루프를 사용하여 배열에 200개의 행을 추가합니다. 각 행에 대해 Row 인스턴스를 만들고 텍스트 콘텐츠가 있는 두 개의 셀을 추가합니다.

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     // 10줄이 추가되면 새로운 페이지 나누기를 삽입합니다.
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## 4단계: 문서에 표 추가
문서 페이지의 문단 컬렉션에 표를 추가합니다.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## 5단계: 문서 저장
페이지 나누기를 삽입하여 PDF 문서를 저장합니다.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 페이지 나누기 삽입을 위한 예제 소스 코드

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 인스턴스화
Document doc = new Document();
// PDF 파일의 페이지 컬렉션에 페이지 추가
doc.Pages.Add();
// 테이블 인스턴스 생성
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// 표의 테두리 스타일 설정
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// 테두리 색상을 빨간색으로 하여 표의 기본 테두리 스타일을 설정합니다.
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// 테이블 열 너비 지정
tab.ColumnWidths = "100 100";
// 테이블에 200개의 행을 추가하기 위한 루프를 생성합니다.
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// 10개의 행이 추가되면 새 페이지에서 새 행을 렌더링합니다.
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// PDF 파일의 문단 컬렉션에 표 추가
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// PDF 문서 저장
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 페이지 나누기를 삽입하는 방법을 알아보았습니다. 이 단계별 가이드를 사용하여 C#을 사용하여 PDF 문서의 표에서 특정 줄 수 뒤에 페이지 나누기를 추가할 수 있습니다.

### PDF 파일에 페이지 나누기 삽입에 대한 FAQ

#### 질문: 페이지 나누기 이후에 생성되는 새 페이지의 페이지 크기를 어떻게 변경할 수 있나요?

 A: 페이지 나누기 후 생성된 새 페이지의 페이지 크기를 변경하려면 다음을 설정할 수 있습니다.`PageSize` 의 속성`Page` 객체. 예를 들어, 다음 코드를 사용하여 페이지 크기를 A4로 설정할 수 있습니다.

```csharp
// 페이지 크기를 A4로 설정하세요
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### 질문: 페이지 나누기 뒤에 새 페이지의 페이지 여백을 제어할 수 있나요?

 A: 네, 페이지 나누기 후 새 페이지의 페이지 여백을 제어할 수 있습니다.`Margin` 의 속성`Page` 페이지 여백을 설정하는 객체입니다. 예를 들어, 모든 여백을 10포인트로 설정하려면 다음 코드를 사용할 수 있습니다.

```csharp
// 모든 여백을 10포인트로 설정하세요
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### 질문: 페이지 나누기 뒤에 새 페이지에 머리글과 바닥글을 추가할 수 있나요?

 A: 네, 페이지 나누기 후에 새 페이지에 머리글과 바닥글을 추가할 수 있습니다. 다음을 사용하세요.`Page.Header` 그리고`Page.Footer` 페이지의 헤더 및 푸터 섹션에 콘텐츠를 추가하는 속성입니다. 예:

```csharp
// 새 페이지에 헤더 추가
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

// 새 페이지에 바닥글 추가
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### 질문: 특정 행 수 이후가 아닌 특정 위치에 페이지 나누기를 삽입할 수 있나요?

 A: 네, 특정 행 수 이후가 아닌 특정 위치에 페이지 나누기를 삽입할 수 있습니다.`IsInNewPage` 행의 속성`true` 해당 행 다음에 표의 새 페이지를 시작하도록 강제합니다.

#### 질문: 콘텐츠 높이에 따라 페이지 나누기 동작을 어떻게 조정할 수 있나요?

 A: 다음을 사용할 수 있습니다.`IsBroken` 페이지 간에 자동 행 나누기를 활성화하거나 비활성화하는 테이블 속성입니다. 설정된 경우`true`, 이를 통해 콘텐츠 높이에 따라 행을 여러 페이지로 나눌 수 있습니다.