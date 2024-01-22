---
title: 테이블 행 콘텐츠의 텍스트 정렬
linktitle: 테이블 행 콘텐츠의 텍스트 정렬
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 테이블의 행 내용을 정렬하는 방법을 알아보세요.
type: docs
weight: 210
url: /ko/net/programming-with-tables/text-alignment-for-table-row-content/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서 테이블의 행 내용을 정렬하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 설명하고 이를 구현하는 방법을 보여 드리겠습니다.

## 1단계: PDF 문서 만들기
먼저 PDF 문서를 만듭니다.

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 2단계: 테이블 초기화
다음으로 테이블을 초기화하겠습니다.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## 3단계: 표 테두리 색상 설정
테이블 테두리 색상을 구성합니다.

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 4단계: 표 셀 테두리 구성
테이블 셀 테두리를 구성하겠습니다.

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 5단계: 반복하여 테이블에 10개의 행을 추가합니다.
이제 루프를 사용하여 테이블에 10개의 행을 추가하겠습니다.

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## 6단계: 수직선 정렬 구성
테이블 행의 수직 정렬을 구성하겠습니다.

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## 7단계: 행 셀에 콘텐츠 추가
행 셀에 내용을 추가하겠습니다.

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## 8단계: 문서 페이지에 표 추가
이제 문서 페이지에 테이블을 추가해 보겠습니다.

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## 9단계: PDF 문서 저장
마지막으로 PDF 문서를 저장합니다.

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 테이블 행 내용의 텍스트 정렬에 대한 예제 소스 코드

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF 문서 만들기
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// 테이블의 새 인스턴스를 초기화합니다.
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// 표 테두리 색상을 LightGray로 설정
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 표 셀의 테두리 설정
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 루프를 만들어 10개의 행을 추가하세요
for (int row_count = 0; row_count < 10; row_count++)
{
	// 테이블에 행 추가
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
// 입력 문서의 첫 번째 페이지에 테이블 개체 추가
tocPage.Paragraphs.Add(table);
// 테이블 객체가 포함된 업데이트된 문서 저장
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## 결론
축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF 문서의 테이블 행 내용을 정렬하는 방법을 배웠습니다. 이 단계별 가이드에서는 문서 만들기, 표 초기화, 테두리 및 정렬 구성, 내용 추가, PDF 문서 저장 방법을 보여주었습니다. 이제 이 지식을 자신의 프로젝트에 적용할 수 있습니다.

### FAQ

#### Q: 표 셀의 내용을 수평으로 정렬하려면 어떻게 해야 합니까?

 A: 다음을 설정하여 표 셀의 내용을 가로로 정렬할 수 있습니다.`HorizontalAlign` 세포의 속성`TextState` 물체. 예를 들어 텍스트를 가운데 정렬하려면 다음을 사용하세요.`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . 다음으로 설정할 수도 있습니다.`HorizontalAlignment.Left` 또는`HorizontalAlignment.Right` 각각 왼쪽 및 오른쪽 정렬에 사용됩니다.

#### Q: 표 내의 개별 셀에 다양한 테두리 스타일과 색상을 적용할 수 있나요?

 A: 예, 표 내의 개별 셀에 다양한 테두리 스타일과 색상을 적용할 수 있습니다. 특정 셀의 테두리를 사용자 정의하려면`cell.Border` 새로운 재산으로`BorderInfo`테두리 측면, 너비, 색상 등 원하는 설정을 사용하여 개체를 만듭니다.

#### Q: 셀 내 표 내용의 수직 정렬을 어떻게 조정할 수 있나요?

 A: 다음을 설정하여 셀 내 표 내용의 수직 정렬을 조정할 수 있습니다.`VerticalAlignment` 행의 속성`VerticalAlignment.Center`, `VerticalAlignment.Top` , 또는`VerticalAlignment.Bottom`. 이 속성은 해당 행에 있는 모든 셀의 수직 정렬을 제어합니다.

#### Q: 테이블에 동적으로 더 많은 열이나 행을 추가할 수 있습니까?

 A: 예, 다음을 사용하여 테이블에 더 많은 열과 행을 동적으로 추가할 수 있습니다.`table.Rows.Add()` 새 행을 추가하는 방법과`row.Cells.Add()` 행에 새 셀을 추가하는 방법입니다. 루프 내부에서 또는 특정 요구 사항에 따라 이 작업을 수행할 수 있습니다.

#### Q: 특정 셀이나 표 전체의 배경색을 어떻게 설정할 수 있나요?

 A: 특정 셀이나 표 전체의 배경색을 설정하려면`BackgroundColor` 의 재산`Cell` 또는`Table` 물체. 예를 들어, 셀의 배경색을 설정하려면 다음을 사용하세요.`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.