---
title: PDF 문서의 테이블 렌더링
linktitle: PDF 문서의 테이블 렌더링
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에 테이블을 표시하는 방법을 알아보세요.
type: docs
weight: 170
url: /ko/net/programming-with-tables/render-table/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 테이블을 표시하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 설명하고 이를 구현하는 방법을 보여 드리겠습니다.

## 1단계: 문서 만들기
먼저 새 PDF 문서를 만듭니다.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 새 문서 만들기
Document doc = new Document();
```

## 2단계: 페이지 여백 및 방향 구성
다음으로 페이지 여백을 구성하고 방향을 가로 모드로 설정합니다.

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## 3단계: 테이블 및 열 만들기
이제 테이블을 만들고 열 너비를 설정해 보겠습니다.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## 4단계: 표에 행과 셀 추가
다음으로 루프를 사용하여 테이블에 행과 셀을 추가합니다.

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## 5단계: 페이지에 테이블 추가
이제 문서 페이지에 테이블을 추가해 보겠습니다.

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## 6단계: 새 페이지에 테이블 표시
다음으로, 새 테이블을 만들고 "IsInNewPage" 속성을 "true"로 설정하여 새 페이지에 테이블을 표시하겠습니다.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## 7단계: PDF 저장
마지막으로 PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### .NET용 Aspose.PDF를 사용하는 Render Table의 소스 코드 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
// 페이지가 추가되었습니다.
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
// 표 1을 다음 페이지로 유지하고 싶습니다.
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## 결론
축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF 문서에 표를 표시하는 방법을 배웠습니다. 이 단계별 가이드에서는 문서를 만들고, 페이지 여백과 방향을 구성하고, 표를 추가하고, 새 페이지에 표를 표시하는 방법을 보여주었습니다. 이제 이 지식을 자신의 프로젝트에 적용할 수 있습니다.

### PDF 문서의 렌더링 테이블에 대한 FAQ

#### Q: 셀 색상 변경, 테두리 추가 등 표의 모양을 수정하려면 어떻게 해야 합니까?

A: 테이블의 모양을 수정하려면 테이블의 다양한 속성을 설정하면 됩니다.`Aspose.Pdf.Table` 그리고 그 세포. 예를 들어 다음을 설정할 수 있습니다.`BackgroundColor` 셀의 배경색을 변경하는 속성입니다. 다음을 설정할 수도 있습니다.`Border` 테두리를 추가하려면 테이블이나 개별 셀의 속성을 사용하세요. 또한,`TextState` ~의`TextFragment` 셀에 개체가 추가되었습니다.

#### Q: 표에 머리글이나 바닥글을 추가할 수 있나요?

A: 예, 표의 시작이나 끝 부분에 추가 행을 만들고 셀에 적절한 내용을 설정하여 표에 머리글이나 바닥글을 추가할 수 있습니다. 이러한 특정 행에 다양한 스타일이나 내용을 추가하여 표의 나머지 내용과 별도로 머리글이나 바닥글을 사용자 정의할 수 있습니다.

#### Q: 페이지에서 표의 위치를 어떻게 제어할 수 있나요?

 A: 페이지에서 표의 위치를 제어하려면`MarginInfo` ~의`PageInfo` 물체. 그만큼`MarginInfo`페이지의 왼쪽, 오른쪽, 위쪽 및 아래쪽 여백을 설정할 수 있으며 이는 테이블의 사용 가능한 공간에 영향을 미칩니다. 다음을 사용할 수도 있습니다.`PositioningType` 의 재산`Aspose.Pdf.Table` 페이지의 콘텐츠 영역 내에서 수평 및 수직 정렬을 제어합니다.

#### Q: 표를 Excel이나 CSV 등 다른 파일 형식으로 내보낼 수 있나요?

A: .NET용 Aspose.PDF는 주로 PDF 문서 작업을 위해 설계되었습니다. PDF 문서를 이미지나 XPS로 내보낼 수 있지만 Excel이나 CSV와 같은 형식으로 테이블을 내보내는 것은 직접 지원하지 않습니다. 테이블 데이터를 다른 파일 형식으로 내보내려면 추가 라이브러리나 방법을 사용하여 PDF 콘텐츠를 원하는 형식으로 변환해야 할 수도 있습니다.

#### Q: 표 셀에 하이퍼링크를 어떻게 추가할 수 있나요?

 A: 표 셀에 하이퍼링크를 추가하려면`Aspose.Pdf.WebHyperlink` 클래스를 사용하여 하이퍼링크를 만든 다음 이를 앵커로 추가합니다.`TextFragment`세포 내부. 이를 통해 URL 또는 링크 대상을 셀 내의 특정 텍스트 또는 콘텐츠와 연결하여 클릭 가능한 하이퍼링크를 만들 수 있습니다.