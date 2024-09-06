---
title: Excel 워크시트 데이터를 테이블로 내보내기
linktitle: Excel 워크시트 데이터를 테이블로 내보내기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 Excel 시트의 데이터를 PDF 테이블로 내보냅니다.
type: docs
weight: 70
url: /ko/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
이 튜토리얼에서는 Aspose.PDF for .NET 라이브러리를 사용하여 Excel 워크시트에서 데이터를 내보내고 PDF 문서에 표를 만드는 방법을 알아봅니다. 소스 코드를 단계별로 살펴보고 각 섹션을 자세히 설명합니다. 이 튜토리얼을 마치면 Excel 워크시트의 데이터가 포함된 표가 있는 PDF 파일을 생성할 수 있습니다. 시작해 봅시다!

## 요구 사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 컴퓨터에 설치된 Visual Studio
- 프로젝트에 .NET 라이브러리용 Aspose.PDF가 추가되었습니다.

## 1단계: 환경 설정
시작하려면 Visual Studio에서 새 C# 프로젝트를 만듭니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 "Aspose.PDF"를 검색하여 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가합니다. 패키지를 설치하면 준비가 완료됩니다.

## 2단계: Excel 워크시트 로드
코드의 첫 번째 단계에서 Excel 문서가 들어 있는 디렉토리 경로를 정의합니다. "YOUR DOCUMENT DIRECTORY"를 Excel 파일이 있는 실제 디렉토리 경로로 바꿉니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

여기서 Aspose.Cells 라이브러리를 사용하여 Excel 통합 문서를 로드합니다. "newBook1.xlsx"를 Excel 파일 이름으로 바꿔야 합니다.

## 3단계: 워크시트 액세스
 다음으로 Excel 파일의 첫 번째 워크시트에 액세스해야 합니다. 이를 위해 다음을 사용합니다.`Worksheets` 의 컬렉션`Workbook` 물체.

```csharp
// Excel 파일의 첫 번째 워크시트에 액세스하기
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Excel 파일에 여러 워크시트가 포함되어 있는 경우 인덱스 값을 변경할 수 있습니다.`[0]` 다른 워크시트에 접근합니다.

## 4단계: DataTable로 데이터 내보내기
 이제 Excel 워크시트의 내용을 다음으로 내보냅니다.`DataTable` 개체입니다. 다음을 사용하여 내보낼 셀 범위를 지정합니다.`ExportDataTable` 방법.

```csharp
// 1번째 셀부터 시작하여 7개 행과 2개 열의 내용을 DataTable로 내보내기
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

이 예에서 우리는 워크시트의 첫 번째 셀(0, 0)부터 마지막 셀까지 모든 행과 열을 내보냅니다. 요구 사항에 따라 적절한 범위를 설정합니다.

## 5단계: PDF 문서 만들기
이제 Aspose.PDF 라이브러리를 사용하여 새로운 PDF 문서를 만들어 보겠습니다.

```csharp
// Document 인스턴스를 인스턴스화합니다.
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

이렇게 하면 내용을 추가할 수 있는 빈 PDF 문서가 생성됩니다.

## 6단계: 페이지 및 표 추가
데이터를 표 형식으로 표시하려면 PDF 문서에 페이지와 표를 추가해야 합니다.

```csharp
// 문서 인스턴스에 페이지를 만듭니다.
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// 테이블 객체 생성
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// 섹션의 문단 컬렉션에 Table 객체를 추가합니다.
sec1.Paragraphs.Add(tab1);
```

여기서 새 페이지와 테이블 객체를 만듭니다. 그런 다음 테이블을 페이지의 문단 컬렉션에 추가합니다.

## 7단계: 테이블 속성 설정
데이터를 가져오기 전에 열 너비, 기본 셀 테두리 등 표의 일부 속성을 설정해야 합니다.

```csharp
// 표의 열 너비 설정
tab1.ColumnWidths = "40 100 100";

// BorderInfo 객체를 사용하여 테이블의 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

이 예에서 우리는 열 너비를 40, 100, 100 단위로 설정했습니다. 귀하의 데이터에 따라 값을 조정합니다. 또한 기본 셀 테두리를 설정하여 각 셀의 모든 면에 테두리를 표시합니다.

## 8단계: 테이블에 데이터 가져오기
 이제 우리는 데이터를 가져올 것입니다`DataTable` 테이블에 객체를 사용하여`ImportDataTable` 방법.

```csharp
// 위에서 생성한 DataTable에서 Table 객체로 데이터를 가져옵니다.
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 여기서 가져올 행과 열의 범위를 지정합니다. 이 예에서 우리는 모든 행과 열을 가져옵니다.`dataTable` 물체.

## 9단계: 표 서식 지정
표의 모양을 개선하기 위해 특정 셀이나 행에 서식을 적용할 수 있습니다. 이 단계에서는 표의 첫 번째 행과 대체 행을 서식 지정합니다.

```csharp
// 테이블에서 첫 번째 행을 가져옵니다
Aspose.Pdf.Row row1 = tab1.Rows[0];

// 첫 번째 행을 포맷합니다
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // 첫 번째 행의 셀 배경색을 설정합니다.
     curCell.BackgroundColor = Color.Blue;// 첫 번째 행의 셀에 대한 얼굴을 설정합니다.
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // 첫 번째 행의 셀 글꼴 색상을 설정합니다.
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // 첫 번째 행의 셀에 대한 텍스트 정렬을 설정합니다.
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// 대체 행 형식
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // 교대로 행에 있는 셀의 배경색을 설정합니다.
         curCell.BackgroundColor = Color.Gray;
        
         // 교대로 행에 있는 셀의 텍스트 색상을 설정합니다.
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

여기서, 우리는 첫 번째 행의 셀을 반복하고 배경색, 글꼴, 글꼴 색상, 텍스트 정렬을 설정합니다. 그런 다음, 우리는 대체 행의 모든 셀을 반복하고 배경색과 텍스트 색상을 설정합니다.

## 10단계: PDF 문서 저장
마지막으로 PDF 문서를 지정된 위치에 저장합니다.

```csharp
// PDF 저장
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

"YOUR DOCUMENT DIRECTORY"를 출력 PDF 파일에 대한 원하는 디렉토리 경로와 파일 이름으로 바꿔야 합니다.

### Aspose.PDF for .NET을 사용하여 Excel 워크시트 데이터를 테이블로 내보내기 위한 예제 소스 코드

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Excel 파일의 첫 번째 워크시트에 액세스하기
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// 1번째 셀부터 시작하여 7개 행과 2개 열의 내용을 DataTable로 내보내기
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// 문서 인스턴스화
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// 문서 인스턴스에 페이지를 만듭니다.
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// 테이블 객체 생성
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// 섹션의 문단 컬렉션에 Table 객체를 추가합니다.
sec1.Paragraphs.Add(tab1);

// 테이블의 열 너비를 설정합니다. ColumnCount를 수동으로 지정해야 합니다.
// 현재 Excel 워크시트에는 열이 3개 있으므로 동일한 개수를 지정합니다.
tab1.ColumnWidths = "40 100 100";

// BorderInfo 객체를 사용하여 테이블의 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// 위에서 생성한 DataTable에서 Table 객체로 데이터를 가져옵니다.
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// 테이블에서 첫 번째 행을 가져옵니다
Aspose.Pdf.Row row1 = tab1.Rows[0];

// 1번째 행의 모든 셀을 반복하고 배경색을 파란색으로 설정합니다.
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// 표의 첫 번째 행에 있는 모든 셀의 배경을 설정합니다.
	curCell.BackgroundColor = Color.Blue;
	// 표의 첫 번째 행 셀의 글꼴을 설정합니다.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// 표의 첫 번째 행에 있는 모든 셀의 글꼴 색상을 설정합니다.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// 첫 번째 행의 셀에 대한 텍스트 정렬을 가운데로 설정합니다.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// 1번째 행의 모든 셀을 반복하고 배경색을 파란색으로 설정합니다.
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		// 첫 번째 행을 제외한 모든 셀의 배경색을 설정합니다.
		curCell.BackgroundColor = Color.Gray;
		// 첫 번째 행을 제외한 모든 셀의 텍스트 색상을 설정합니다.
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

// PDF 저장
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET 라이브러리를 사용하여 Excel 워크시트에서 PDF 테이블로 데이터를 내보내는 방법을 알아보았습니다. Excel 워크시트를 로드하고, PDF 문서를 만들고, 테이블을 추가하고, 데이터를 가져오고, 테이블을 포맷하는 단계별 프로세스를 다루었습니다. 이제 Excel 데이터가 포함된 테이블이 있는 PDF 파일을 프로그래밍 방식으로 생성할 수 있습니다.

### 자주 묻는 질문

#### 질문: Excel 워크시트 데이터를 PDF 표로 내보내는 목적은 무엇입니까?

A: Excel 워크시트 데이터를 PDF 표로 내보내면 데이터를 구조화되고 정리된 형식으로 표현할 수 있습니다. Excel 워크시트의 데이터가 포함된 표가 있는 PDF 파일을 생성하여 휴대용 문서 형식으로 정보를 공유하고 보존하기가 더 쉬워집니다.

#### 질문: PDF 표의 모양을 사용자 정의할 수 있나요?

A: 네, Aspose.PDF for .NET에서 제공하는 다양한 속성을 사용하여 PDF 테이블의 모양을 사용자 정의할 수 있습니다. 제공된 C# 소스 코드에서 열 너비, 셀 테두리, 텍스트 정렬, 글꼴 스타일 등을 수정하여 특정 요구 사항에 맞출 수 있습니다.

#### 질문: 여러 개의 워크시트가 있는 Excel 파일을 어떻게 처리합니까?

 A: 제공된 C# 코드에서 인덱스를 사용하여 Excel 파일의 첫 번째 워크시트에 액세스했습니다.`[0]` . Excel 파일에 여러 워크시트가 포함되어 있는 경우 인덱스 값을 적절히 변경하여 액세스할 수 있습니다.`[1]` 두 번째 워크시트 또는`[2]` 세 번째 워크시트에 대해서요.

#### 질문: PDF 표의 특정 행이나 셀에 다른 서식을 적용할 수 있나요?

A: 네, PDF 테이블의 특정 행이나 셀에 다른 서식을 적용할 수 있습니다. 제공된 C# 소스 코드에서 배경색, 글꼴 스타일, 글꼴 색상을 변경하여 첫 번째 행과 교대 행을 다르게 서식 지정하는 방법을 보여주었습니다. 필요에 따라 특정 행이나 셀에 유사한 서식 지정 기술을 적용할 수 있습니다.

#### 질문: .NET용 Aspose.PDF가 Excel 데이터를 PDF 테이블로 내보낼 수 있는 유일한 라이브러리인가요?

A: Aspose.PDF for .NET은 .NET 애플리케이션에서 PDF 문서 작업을 위한 강력한 라이브러리입니다. 다른 라이브러리도 있을 수 있지만 Aspose.PDF for .NET은 Excel 데이터에서 표가 있는 PDF 파일을 생성, 조작 및 내보내기 위한 광범위한 기능과 성능을 제공하므로 이러한 작업에 인기 있는 선택입니다.