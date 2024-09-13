---
title: 테이블 행 내용에 대한 텍스트 정렬
linktitle: 테이블 행 내용에 대한 텍스트 정렬
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 표의 행 내용을 정렬하는 방법을 알아보세요.
type: docs
weight: 210
url: /ko/net/programming-with-tables/text-alignment-for-table-row-content/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 표에서 행의 내용을 정렬하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 설명하고 구현 방법을 보여드리겠습니다.

## 1단계: PDF 문서 만들기
먼저 PDF 문서를 만듭니다.

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 2단계: 테이블 초기화
다음으로, 테이블을 초기화합니다.

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## 3단계: 테이블 테두리 색상 설정
테이블 테두리 색상을 구성합니다.

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 4단계: 테이블 셀 테두리 구성
테이블 셀 테두리를 구성해 보겠습니다.

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 5단계: 루프를 실행하여 테이블에 10개 행을 추가합니다.
이제 루프를 사용하여 테이블에 10개의 행을 추가해 보겠습니다.

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
우리는 테이블 행의 수직 정렬을 구성하려고 합니다.

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## 7단계: 행 셀에 콘텐츠 추가
행 셀에 내용을 추가해 보겠습니다.

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## 8단계: 문서 페이지에 표 추가
이제 문서 페이지에 표를 추가해 보겠습니다.

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## 9단계: PDF 문서 저장
마지막으로 PDF 문서를 저장합니다.

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 테이블 행 내용에 대한 텍스트 정렬을 위한 예제 소스 코드

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF 문서 만들기
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// 테이블의 새 인스턴스를 초기화합니다.
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// 테이블 테두리 색상을 LightGray로 설정하세요
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 테이블 셀의 테두리 설정
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 10개의 행을 추가하기 위해 루프를 생성하세요
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
// 입력 문서의 첫 번째 페이지에 테이블 객체 추가
tocPage.Paragraphs.Add(table);
// 테이블 객체를 포함하는 업데이트된 문서를 저장합니다.
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## 결론
축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF 문서의 표에 있는 행의 내용을 정렬하는 방법을 배웠습니다. 이 단계별 가이드에서는 문서를 만들고, 표를 초기화하고, 테두리와 정렬을 구성하고, 내용을 추가하고, PDF 문서를 저장하는 방법을 보여주었습니다. 이제 이 지식을 자신의 프로젝트에 적용할 수 있습니다.

### 자주 묻는 질문

#### 질문: 표 셀의 내용을 수평으로 정렬하려면 어떻게 해야 하나요?

 A: 테이블 셀의 내용을 수평으로 정렬하려면 다음을 설정합니다.`HorizontalAlign` 세포의 속성`TextState` 개체. 예를 들어, 텍스트를 중앙 정렬하려면 다음을 사용합니다.`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center` . 또한 설정할 수도 있습니다`HorizontalAlignment.Left` 또는`HorizontalAlignment.Right` 각각 왼쪽 및 오른쪽 정렬을 위해.

#### 질문: 표 내의 각 셀에 다른 테두리 스타일과 색상을 적용할 수 있나요?

 A: 네, 테이블 내의 개별 셀에 다른 테두리 스타일과 색상을 적용할 수 있습니다. 특정 셀의 테두리를 사용자 지정하려면`cell.Border` 새로운 속성`BorderInfo`테두리 측면, 너비, 색상 등 원하는 설정을 가진 개체입니다.

#### 질문: 셀 내에서 표 내용의 수직 정렬을 어떻게 조정할 수 있나요?

 A: 셀 내에서 표 내용의 수직 정렬을 조정하려면 다음을 설정하세요.`VerticalAlignment` 행의 속성`VerticalAlignment.Center`, `VerticalAlignment.Top` , 또는`VerticalAlignment.Bottom`. 이 속성은 해당 행의 모든 셀의 수직 정렬을 제어합니다.

#### 질문: 표에 더 많은 열이나 행을 동적으로 추가할 수 있나요?

 A: 예, 다음을 사용하여 테이블에 더 많은 열과 행을 동적으로 추가할 수 있습니다.`table.Rows.Add()` 새 행을 추가하는 방법과`row.Cells.Add()` 행에 새 셀을 추가하는 방법입니다. 루프 내부에서 또는 특정 요구 사항에 따라 이를 수행할 수 있습니다.

#### 질문: 특정 셀이나 표 전체의 배경색을 어떻게 설정할 수 있나요?

 A: 특정 셀이나 전체 표의 배경색을 설정하려면 다음을 사용하십시오.`BackgroundColor` 의 속성`Cell` 또는`Table` 개체. 예를 들어 셀의 배경색을 설정하려면 다음을 사용합니다.`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.