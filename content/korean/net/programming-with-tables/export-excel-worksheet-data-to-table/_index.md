---
title: Excel 워크시트 데이터를 테이블로 내보내기
linktitle: Excel 워크시트 데이터를 테이블로 내보내기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 Excel 시트의 데이터를 PDF 테이블로 내보냅니다.
type: docs
weight: 70
url: /ko/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
이 튜토리얼에서는 Excel 워크시트에서 데이터를 내보내고 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에 테이블을 만드는 방법을 알아봅니다. 소스 코드를 단계별로 살펴보고 각 섹션을 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 Excel 워크시트의 데이터가 포함된 테이블이 포함된 PDF 파일을 생성할 수 있습니다. 시작하자!

## 요구사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 컴퓨터에 설치된 Visual Studio
- 프로젝트에 추가된 .NET 라이브러리용 Aspose.PDF

## 1단계: 환경 설정
시작하려면 Visual Studio에서 새 C# 프로젝트를 만듭니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택한 다음 "Aspose.PDF"를 검색하여 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가합니다. 패키지를 설치하면 바로 사용할 수 있습니다.

## 2단계: Excel 워크시트 로드
코드의 첫 번째 단계에서는 Excel 문서가 포함된 디렉터리의 경로를 정의합니다. "YOUR DOCUMENT DIRECTORY"를 Excel 파일이 있는 실제 디렉터리 경로로 바꾸세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

여기서는 Aspose.Cells 라이브러리를 사용하여 Excel 통합 문서를 로드합니다. "newBook1.xlsx"를 Excel 파일 이름으로 바꾸십시오.

## 3단계: 워크시트에 액세스하기
 다음으로 Excel 파일의 첫 번째 워크시트에 액세스해야 합니다. 우리는 다음을 사용하여 이 작업을 수행합니다.`Worksheets` 의 컬렉션`Workbook` 물체.

```csharp
// Excel 파일의 첫 번째 워크시트에 액세스
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

 Excel 파일에 여러 워크시트가 포함된 경우 색인 값을 변경할 수 있습니다.`[0]` 다른 워크시트에 액세스합니다.

## 4단계: DataTable로 데이터 내보내기
 이제 Excel 워크시트의 내용을`DataTable` 물체. 다음을 사용하여 내보낼 셀 범위를 지정합니다.`ExportDataTable` 방법.

```csharp
// 첫 번째 셀부터 7행 2열의 내용을 DataTable로 내보내기
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

이 예에서는 워크시트의 첫 번째 셀(0, 0)부터 마지막 셀까지 모든 행과 열을 내보냅니다. 요구 사항에 따라 적절한 범위를 설정하십시오.

## 5단계: PDF 문서 만들기
이제 Aspose.PDF 라이브러리를 사용하여 새 PDF 문서를 만들어 보겠습니다.

```csharp
// 문서 인스턴스 인스턴스화
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

그러면 콘텐츠를 추가할 수 있는 빈 PDF 문서가 생성됩니다.

## 6단계: 페이지 및 표 추가하기
데이터를 표 형식으로 표시하려면 PDF 문서에 페이지와 표를 추가해야 합니다.

```csharp
// 문서 인스턴스에서 페이지 만들기
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// 테이블 개체 만들기
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// 섹션의 단락 컬렉션에 표 개체를 추가합니다.
sec1.Paragraphs.Add(tab1);
```

여기서는 새 페이지와 테이블 개체를 만듭니다. 그런 다음 페이지의 단락 컬렉션에 표를 추가합니다.

## 7단계: 테이블 속성 설정
데이터를 가져오기 전에 열 너비 및 기본 셀 테두리와 같은 테이블의 일부 속성을 설정해야 합니다.

```csharp
// 테이블의 열 너비 설정
tab1.ColumnWidths = "40 100 100";

// BorderInfo 개체를 사용하여 테이블의 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

이 예에서는 열 너비를 40, 100 및 100 단위로 설정했습니다. 데이터를 기반으로 값을 조정합니다. 또한 각 셀의 모든 측면에 테두리를 표시하도록 기본 셀 테두리를 설정했습니다.

## 8단계: 테이블로 데이터 가져오기
 이제 다음에서 데이터를 가져오겠습니다.`DataTable` 을 사용하여 테이블에 객체를 넣습니다.`ImportDataTable` 방법.

```csharp
// 위에서 생성한 DataTable에서 Table 개체로 데이터 가져오기
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

 여기서는 가져올 행과 열의 범위를 지정합니다. 이 예에서는 다음에서 모든 행과 열을 가져옵니다.`dataTable` 물체.

## 9단계: 테이블 형식 지정
표의 모양을 향상시키기 위해 특정 셀이나 행에 서식을 적용할 수 있습니다. 이 단계에서는 테이블의 첫 번째 행과 대체 행의 형식을 지정합니다.

```csharp
// 테이블에서 첫 번째 행 가져오기
Aspose.Pdf.Row row1 = tab1.Rows[0];

// 첫 번째 행 서식 지정
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     // 첫 번째 행의 셀 배경색을 설정합니다.
     curCell.BackgroundColor = Color.Blue;// 첫 번째 행에 있는 셀의 면을 설정합니다.
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     // 첫 번째 행에 있는 셀의 글꼴 색상을 설정합니다.
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     // 첫 번째 행의 셀에 대한 텍스트 정렬 설정
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

// 대체 행 형식
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         // 대체 행에 있는 셀의 배경색 설정
         curCell.BackgroundColor = Color.Gray;
        
         // 대체 행에 있는 셀의 텍스트 색상 설정
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

여기서는 첫 번째 행의 셀을 반복하고 배경색, 글꼴, 글꼴 색상 및 텍스트 정렬을 설정합니다. 그런 다음 대체 행의 모든 셀을 반복하고 배경 및 텍스트 색상을 설정합니다.

## 10단계: PDF 문서 저장
마지막으로 PDF 문서를 지정된 위치에 저장합니다.

```csharp
// PDF 저장
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

"YOUR DOCUMENT DIRECTORY"를 출력 PDF 파일의 원하는 디렉토리 경로 및 파일 이름으로 바꾸십시오.

### .NET용 Aspose.PDF를 사용하여 Excel 워크시트 데이터를 테이블로 내보내기에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
// Excel 파일의 첫 번째 워크시트에 액세스
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
// 첫 번째 셀부터 7행 2열의 내용을 DataTable로 내보내기
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

// 문서 인스턴스 인스턴스화
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
// 문서 인스턴스에서 페이지 만들기
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

// 테이블 개체 만들기
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// 섹션의 단락 컬렉션에 표 개체를 추가합니다.
sec1.Paragraphs.Add(tab1);

// 테이블의 열 너비를 설정합니다. ColumnCount를 수동으로 지정해야 합니다.
// 현재 Excel 워크시트에는 세 개의 열이 있으므로 동일한 수를 지정합니다.
tab1.ColumnWidths = "40 100 100";

// BorderInfo 개체를 사용하여 테이블의 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// 위에서 생성한 DataTable에서 Table 개체로 데이터 가져오기
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
// 테이블에서 첫 번째 행 가져오기
Aspose.Pdf.Row row1 = tab1.Rows[0];

// 첫 번째 행의 모든 셀을 반복하고 배경색을 파란색으로 설정합니다.
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	// 테이블의 첫 번째 행에 있는 모든 셀의 배경을 설정합니다.
	curCell.BackgroundColor = Color.Blue;
	// 테이블의 첫 번째 행 셀에 대한 글꼴을 설정합니다.
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	// 테이블의 첫 번째 행에 있는 모든 셀의 글꼴 색상을 설정합니다.
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	// 첫 번째 행의 셀에 대한 텍스트 정렬을 가운데로 설정합니다.
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	// 첫 번째 행의 모든 셀을 반복하고 배경색을 파란색으로 설정합니다.
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
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 Excel 워크시트의 데이터를 PDF 테이블로 내보내는 방법을 배웠습니다. Excel 워크시트 로드, PDF 문서 생성, 테이블 추가, 데이터 가져오기, 테이블 서식 지정 등의 단계별 프로세스를 다루었습니다. 이제 프로그래밍 방식으로 Excel 데이터가 포함된 테이블이 포함된 PDF 파일을 생성할 수 있습니다.

### FAQ

#### Q: Excel 워크시트 데이터를 PDF 테이블로 내보내는 목적은 무엇입니까?

A: Excel 워크시트 데이터를 PDF 테이블로 내보내면 데이터를 구조화되고 정리된 형식으로 표시할 수 있습니다. Excel 워크시트의 데이터가 포함된 테이블로 PDF 파일을 생성할 수 있으므로 정보를 휴대용 문서 형식으로 더 쉽게 공유하고 보존할 수 있습니다.

#### Q: PDF 테이블의 모양을 사용자 정의할 수 있습니까?

A: 예, Aspose.PDF for .NET에서 제공하는 다양한 속성을 사용하여 PDF 테이블의 모양을 사용자 정의할 수 있습니다. 제공된 C# 소스 코드에서 특정 요구 사항에 맞게 열 너비, 셀 테두리, 텍스트 정렬, 글꼴 스타일 등을 수정할 수 있습니다.

#### Q: 여러 워크시트가 포함된 Excel 파일을 어떻게 처리합니까?

 A: 제공된 C# 코드에서는 인덱스를 사용하여 Excel 파일의 첫 번째 워크시트에 액세스했습니다.`[0]` . Excel 파일에 여러 워크시트가 포함된 경우 다음과 같이 색인 값을 적절하게 변경하여 해당 워크시트에 액세스할 수 있습니다.`[1]` 두 번째 워크시트의 경우 또는`[2]` 세 번째 워크시트의 경우

#### Q: PDF 표의 특정 행이나 셀에 다른 서식을 적용할 수 있습니까?

A: 예, PDF 테이블의 특정 행이나 셀에 다른 서식을 적용할 수 있습니다. 제공된 C# 소스 코드에서는 배경색, 글꼴 스타일 및 글꼴 색상을 변경하여 첫 번째 행과 대체 행의 서식을 다르게 지정하는 방법을 시연했습니다. 필요에 따라 특정 행이나 셀에 유사한 서식 기술을 적용할 수 있습니다.

#### Q: Aspose.PDF for .NET이 Excel 데이터를 PDF 테이블로 내보낼 수 있는 유일한 라이브러리입니까?

A: .NET용 Aspose.PDF는 .NET 애플리케이션에서 PDF 문서 작업을 위한 강력한 라이브러리입니다. 사용 가능한 다른 라이브러리가 있을 수 있지만 .NET용 Aspose.PDF는 Excel 데이터의 테이블이 포함된 PDF 파일을 생성, 조작 및 내보내기 위한 광범위한 기능을 제공하므로 이러한 작업에 널리 사용됩니다.