---
title: PDF 문서에 반복 열 추가
linktitle: PDF 문서에 반복 열 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에 반복 열을 추가하는 방법을 알아보세요.
type: docs
weight: 20
url: /ko/net/programming-with-tables/add-repeating-column/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 반복 열을 추가하는 방법을 알아 보겠습니다. C#의 소스코드를 단계별로 설명하겠습니다. 이 튜토리얼이 끝나면 PDF 문서에서 반복되는 열이 있는 표를 만드는 방법을 알게 될 것입니다. 시작하자!

## 1단계: 환경 설정
먼저 .NET용 Aspose.PDF를 사용하여 C# 개발 환경을 설정했는지 확인하세요. 라이브러리에 참조를 추가하고 필요한 네임스페이스를 가져옵니다.

## 2단계: PDF 문서 만들기
이 단계에서는 새 PDF 문서를 만듭니다.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

콘텐츠를 추가할 수 있는 빈 PDF 문서를 만들었습니다.

## 3단계: 테이블 생성
이 단계에서는 기본 테이블(`outerTable`) 및 중첩 테이블(`mytable`) 이 내용은 열에서 반복됩니다.

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

열 너비 및 중첩 테이블 나누기 모드와 같은 테이블 속성을 지정했습니다.

## 4단계: 문서에 표 추가
이제 생성된 테이블을 PDF 문서에 추가합니다.

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

먼저 메인 테이블(`outerTable`)를 PDF 문서로 복사합니다. 다음으로 중첩 테이블(`mytable` )를 기본 테이블의 셀에 단락으로 표시합니다. 또한 반복되는 열의 수를 지정합니다.`mytable` (이 예에서는 5개 열)

## 5단계: 헤더 및 줄 추가하기
이제 테이블에 헤더와 행을 추가합니다.

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
// 여기에 다른 헤더를 추가하세요.

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     // 여기에 다른 열을 추가하세요.
}
```

먼저 테이블의 첫 번째 행에 헤더를 추가합니다(`headerRow`). 그런 다음 루프에서 데이터 행을 추가합니다. 이 예에서는 6개의 데이터 행을 추가합니다.

## 6단계: PDF 문서 저장
마지막으로 PDF 문서를 지정된 파일에 저장합니다.

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

출력 PDF 파일을 저장하려면 올바른 디렉터리와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.PDF를 사용하여 반복 열을 추가하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
// 새 문서 만들기
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

// 전체 페이지를 차지하는 외부 테이블을 인스턴스화합니다.
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//동일한 페이지 내에서 분리되는 externalTable 내에 중첩될 테이블 개체를 인스턴스화합니다.
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

// 페이지 단락에 externalTable을 추가합니다.
// 외부 테이블에 mytable 추가
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

// 헤더 행 추가
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	// 테이블에 행을 만든 다음 행에 셀을 만듭니다.
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 반복 열을 추가하는 방법을 배웠습니다. 이 단계별 가이드를 사용하여 C# 프로젝트에서 반복되는 열이 있는 테이블을 만들 수 있습니다.

### PDF 문서에 반복 열 추가에 대한 FAQ

#### Q: 중첩 테이블에서 반복되는 열 수를 사용자 정의할 수 있습니까?

 A: 예, 중첩 테이블에서 반복되는 열 수를 사용자 정의할 수 있습니다. 제공된 예에서는 다음을 설정했습니다.`mytable.RepeatingColumnsCount = 5;`즉, 5개의 반복되는 열이 있음을 의미합니다. 이 값을 원하는 숫자로 변경할 수 있습니다.

#### Q: 중첩 테이블에 동적으로 더 많은 행을 추가할 수 있습니까?

A: 예, 튜토리얼에 표시된 것과 동일한 방식으로 중첩 테이블에 더 많은 행을 동적으로 추가할 수 있습니다. 루프나 다른 논리를 사용하여 데이터를 기반으로 행을 추가할 수 있습니다.

#### Q: 표와 셀에 스타일과 서식을 적용할 수 있나요?

A: 예, Aspose.PDF for .NET을 사용하여 테이블과 해당 셀에 스타일과 서식을 적용할 수 있습니다. 라이브러리는 테이블의 모양과 내용을 사용자 정의하는 다양한 속성과 메서드를 제공합니다.

#### Q: .NET용 Aspose.PDF는 .NET Core와 호환됩니까?

A: 예, .NET용 Aspose.PDF는 .NET Core와 호환됩니다. .NET Framework 및 .NET Core 애플리케이션 모두에서 사용할 수 있습니다.

#### 질문: 이 접근 방식을 사용하여 기존 PDF 문서에 반복 열을 추가할 수 있습니까?

A: 예, 이 접근 방식을 사용하여 기존 PDF 문서에 반복되는 열을 추가할 수 있습니다. .NET용 Aspose.PDF를 사용하여 기존 문서를 로드하고 동일한 단계에 따라 반복 열을 만들고 추가하면 됩니다.