---
title: PDF 파일에서 데이터베이스와 통합
linktitle: PDF 파일에서 데이터베이스와 통합
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 데이터베이스의 데이터를 PDF 파일에 포함합니다.
type: docs
weight: 120
url: /ko/net/programming-with-tables/integrate-with-database/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 데이터베이스의 데이터를 PDF 파일에 포함시키는 방법을 알아봅니다. C#의 소스코드를 단계별로 설명하겠습니다. 이 튜토리얼이 끝나면 데이터베이스의 테이블 데이터를 PDF 문서로 가져오는 방법을 알게 됩니다. 시작하자!

## 1단계: 환경 설정
.NET용 Aspose.PDF를 사용하여 C# 개발 환경을 구성했는지 확인하세요. 라이브러리에 참조를 추가하고 필요한 네임스페이스를 가져옵니다.

## 2단계: DataTable 만들기
PDF 문서에 포함하려는 데이터를 나타내기 위해 DataTable의 인스턴스를 만듭니다. 이 예에서는 Employee_ID, Employee_Name 및 Gender라는 세 개의 열이 있는 DataTable을 만듭니다. 또한 더미 데이터가 있는 DataTable에 두 개의 행을 추가합니다.

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## 3단계: PDF 문서 및 표 만들기
Document 인스턴스를 생성하고 이 문서에 페이지를 추가합니다. 다음으로 PDF 문서에서 테이블을 나타내는 Table 인스턴스를 만듭니다. 테이블 열 너비와 테두리 스타일을 정의합니다.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 4단계: DataTable의 데이터를 테이블로 가져오기
ImportDataTable 메서드를 사용하여 DataTable의 데이터를 PDF 문서의 테이블로 가져옵니다.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## 5단계: 문서에 표 추가
문서 페이지의 단락 컬렉션에 표를 추가합니다.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## 6단계: 문서 저장
내장된 데이터베이스의 데이터와 함께 PDF 문서를 저장합니다.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

축하해요! 이제 Aspose.PDF for .NET을 사용하여 PDF 문서에 데이터베이스 데이터를 포함하는 방법을 알았습니다.

### .NET용 Aspose.PDF를 사용하여 데이터베이스와 통합하기 위한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
// 프로그래밍 방식으로 DataTable 개체에 2개의 행을 추가합니다.
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
// 문서 인스턴스 생성
Document doc = new Document();
doc.Pages.Add();
// 테이블의 새 인스턴스를 초기화합니다.
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// 테이블의 열 너비 설정
table.ColumnWidths = "40 100 100 100";
// 표 테두리 색상을 LightGray로 설정
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 표 셀의 테두리 설정
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// 입력 문서의 첫 번째 페이지에 테이블 개체 추가
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// 테이블 객체가 포함된 업데이트된 문서 저장
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 데이터베이스의 데이터를 PDF 문서에 포함시키는 방법을 배웠습니다. 이 단계별 가이드를 사용하여 자신의 데이터베이스에서 데이터를 가져와 PDF 문서에 표시할 수 있습니다. 이 강력한 라이브러리가 제공하는 다른 기능과 가능성을 알아보려면 Aspose.PDF 문서를 자세히 살펴보세요.

### PDF 파일의 데이터베이스 통합에 대한 FAQ

#### Q: MySQL, SQL Server 또는 Oracle과 같은 다양한 데이터베이스 유형에서 Aspose.PDF for .NET을 사용할 수 있습니까?

A: 예, MySQL, SQL Server, Oracle 등과 같은 다양한 데이터베이스 유형에서 .NET용 Aspose.PDF를 사용할 수 있습니다. .NET용 Aspose.PDF는 데이터베이스, XML 파일 등을 포함한 다양한 데이터 소스에서 데이터를 읽는 기능을 제공합니다. 원하는 데이터베이스 유형에서 데이터를 검색하여 DataTable 또는 .NET용 Aspose.PDF와 호환되는 기타 데이터 구조에 채울 수 있습니다.

#### Q: PDF 문서의 표 모양을 어떻게 사용자 정의할 수 있나요?

A: Aspose.PDF for .NET 라이브러리에서 제공하는 다양한 속성을 사용하여 PDF 문서의 테이블 모양을 사용자 정의할 수 있습니다. 예를 들어, 테이블과 해당 셀에 대해 다양한 테두리 스타일, 배경색, 글꼴 스타일, 정렬을 설정할 수 있습니다. 테이블 모양 사용자 정의에 대한 자세한 내용은 .NET용 Aspose.PDF 문서를 참조하세요.

#### Q: 데이터베이스에서 가져온 데이터에 하이퍼링크나 대화형 요소를 추가할 수 있습니까?

A: 예, 데이터베이스에서 가져온 데이터에 하이퍼링크나 기타 대화형 요소를 추가할 수 있습니다. .NET용 Aspose.PDF는 PDF 문서에 하이퍼링크, 책갈피 및 기타 대화형 요소를 추가하는 것을 지원합니다. DataTable의 내용을 테이블로 가져오기 전에 조작하고 하이퍼링크나 기타 대화형 기능을 포함할 수 있습니다.

#### Q: 테이블이 특정 행 수를 초과하는 경우 페이지를 매길 수 있나요?

 A: 예. 특정 행 수를 초과하는 경우 테이블의 페이지를 매길 수 있습니다. 이를 달성하려면 다음을 사용할 수 있습니다.`IsInNewPage`Row 개체의 속성을 사용하여 새 페이지가 특정 행 다음에 시작되어야 함을 나타냅니다. 페이지당 표시할 행 수를 계산하고`IsInNewPage` 그에 따라 재산.

#### Q: 데이터베이스 데이터가 포함된 PDF 문서를 DOCX 또는 XLSX와 같은 다른 파일 형식으로 내보내려면 어떻게 해야 합니까?

답변: .NET용 Aspose.PDF를 사용하면 PDF 문서를 DOCX(Microsoft Word) 및 XLSX(Microsoft Excel)를 포함한 다양한 다른 파일 형식으로 변환할 수 있습니다. 이를 달성하기 위해 Aspose.Words 및 Aspose.Cells와 같은 다른 Aspose 라이브러리와 함께 .NET용 Aspose.PDF 라이브러리를 사용할 수 있습니다. 먼저 데이터베이스 데이터가 포함된 PDF 문서를 저장한 다음 해당 Aspose 라이브러리를 사용하여 원하는 파일 형식으로 변환합니다.