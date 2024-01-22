---
title: PDF 파일에 페이지 나누기 삽입
linktitle: PDF 파일에 페이지 나누기 삽입
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 페이지 나누기를 삽입하는 방법을 알아보세요.
type: docs
weight: 110
url: /ko/net/programming-with-tables/insert-page-break/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 페이지 나누기를 삽입하는 방법을 알아봅니다. C#의 소스코드를 단계별로 설명하겠습니다. 이 튜토리얼이 끝나면 PDF 문서 표의 특정 줄 수 뒤에 페이지 나누기를 추가하는 방법을 알게 됩니다. 시작하자!

## 1단계: 환경 설정
.NET용 Aspose.PDF를 사용하여 C# 개발 환경을 구성했는지 확인하세요. 라이브러리에 참조를 추가하고 필요한 네임스페이스를 가져옵니다.

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

## 3단계: 테이블에 행 추가
루프를 사용하여 배열에 200개의 행을 추가합니다. 각 행에 대해 Row 인스턴스를 만들고 텍스트 내용이 포함된 두 개의 셀을 추가합니다.

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
    
     // 10줄이 추가되면 새 페이지 나누기를 삽입합니다.
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## 4단계: 문서에 표 추가
문서 페이지의 단락 컬렉션에 표를 추가합니다.

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## 5단계: 문서 저장
페이지 나누기가 삽입된 PDF 문서를 저장합니다.

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 페이지 나누기 삽입에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 인스턴스 인스턴스화
Document doc = new Document();
// PDF 파일의 페이지 모음에 페이지 추가
doc.Pages.Add();
// 테이블 인스턴스 생성
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
// 표의 테두리 스타일 설정
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// 테두리 색상이 빨간색인 표의 기본 테두리 스타일을 설정합니다.
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
// 테이블 열 너비 지정
tab.ColumnWidths = "100 100";
// 테이블에 200개의 행을 추가하는 루프를 만듭니다.
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	// 10개의 행이 추가되면 새 페이지에 새 행을 렌더링합니다.
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
// PDF 파일의 단락 모음에 표 추가
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
// PDF 문서 저장
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에 페이지 나누기를 삽입하는 방법을 배웠습니다. 이 단계별 가이드를 사용하면 C#을 사용하여 PDF 문서의 표에서 특정 줄 수 뒤에 페이지 나누기를 추가할 수 있습니다.

### PDF 파일의 페이지 나누기 삽입에 대한 FAQ

#### Q: 페이지 나누기 이후 생성된 새 페이지의 페이지 크기를 어떻게 변경할 수 있나요?

 A: 페이지 나누기 이후 생성된 새 페이지의 페이지 크기를 변경하려면`PageSize` 의 재산`Page` 물체. 예를 들어 다음 코드를 사용하여 페이지 크기를 A4로 설정할 수 있습니다.

```csharp
// 페이지 크기를 A4로 설정
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### Q: 페이지 나누기 후 새 페이지의 페이지 여백을 제어할 수 있나요?

 A: 예, 페이지 나누기 이후 새 페이지의 페이지 여백을 제어할 수 있습니다. 사용`Margin` 의 재산`Page` 페이지 여백을 설정하는 개체입니다. 예를 들어 모든 여백을 10포인트로 설정하려면 다음 코드를 사용할 수 있습니다.

```csharp
// 모든 여백을 10포인트로 설정
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### Q: 페이지 나누기 후에 새 페이지에 머리글과 바닥글을 추가할 수 있나요?

 A: 예, 페이지 나누기 후에 새 페이지에 머리글과 바닥글을 추가할 수 있습니다. 사용`Page.Header` 그리고`Page.Footer` 페이지의 머리글 및 바닥글 섹션에 콘텐츠를 추가하는 속성입니다. 예를 들어:

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

#### Q: 특정 행 수 이후가 아닌 특정 위치에 페이지 나누기를 삽입할 수 있나요?

 A: 예, 특정 행 수 이후가 아닌 특정 위치에 페이지 나누기를 삽입할 수 있습니다. 당신은 설정할 수 있습니다`IsInNewPage` 행의 속성`true` 해당 행 다음에 테이블이 새 페이지를 시작하도록 강제합니다.

#### Q: 콘텐츠 높이에 따라 페이지 나누기 동작을 어떻게 조정할 수 있습니까?

A: 다음을 사용할 수 있습니다.`IsBroken` 페이지에 걸쳐 자동 행 나누기를 활성화하거나 비활성화하려면 테이블의 속성을 사용하세요. 으로 설정하면`true`, 콘텐츠 높이에 따라 행을 여러 페이지로 나눌 수 있습니다.