---
title: PDF 파일에서 데이터베이스와 통합
linktitle: PDF 파일에서 데이터베이스와 통합
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 데이터베이스의 데이터를 PDF 파일에 포함합니다.
type: docs
weight: 120
url: /ko/net/programming-with-tables/integrate-with-database/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 데이터베이스의 데이터를 PDF 파일에 임베드하는 방법을 알아봅니다. C# 소스 코드를 단계별로 설명합니다. 이 튜토리얼을 마치면 데이터베이스에서 테이블 데이터를 PDF 문서로 가져오는 방법을 알게 됩니다. 시작해 봅시다!

## 1단계: 환경 설정
Aspose.PDF for .NET으로 C# 개발 환경을 구성했는지 확인하세요. 라이브러리에 참조를 추가하고 필요한 네임스페이스를 가져옵니다.

## 2단계: DataTable 만들기
PDF 문서에 임베드하려는 데이터를 나타내기 위해 DataTable 인스턴스를 만듭니다. 이 예에서 Employee_ID, Employee_Name, Gender라는 세 개의 열이 있는 DataTable을 만듭니다. 또한 더미 데이터가 있는 DataTable에 두 개의 행을 추가합니다.

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
Document 인스턴스를 만들고 이 문서에 페이지를 추가합니다. 다음으로 PDF 문서에서 테이블을 나타내는 Table 인스턴스를 만듭니다. 테이블 열 너비와 테두리 스타일을 정의합니다.

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 4단계: DataTable에서 테이블로 데이터 가져오기
ImportDataTable 메서드를 사용하여 DataTable의 데이터를 PDF 문서의 테이블로 가져옵니다.

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## 5단계: 문서에 표 추가
문서 페이지의 문단 컬렉션에 표를 추가합니다.

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## 6단계: 문서 저장
내장된 데이터베이스의 데이터를 사용하여 PDF 문서를 저장합니다.

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

축하합니다! 이제 Aspose.PDF for .NET을 사용하여 데이터베이스 데이터를 PDF 문서에 임베드하는 방법을 알게 되었습니다.

### .NET용 Aspose.PDF를 사용하여 데이터베이스와 통합하기 위한 예제 소스 코드

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//DataTable 개체에 프로그래밍 방식으로 2개의 행 추가
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
// 표의 열 너비 설정
table.ColumnWidths = "40 100 100 100";
// 테이블 테두리 색상을 LightGray로 설정하세요
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 테이블 셀의 테두리 설정
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

// 입력 문서의 첫 번째 페이지에 테이블 객체 추가
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
// 테이블 객체를 포함하는 업데이트된 문서를 저장합니다.
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 데이터베이스의 데이터를 PDF 문서에 임베드하는 방법을 알아보았습니다. 이 단계별 가이드를 사용하여 자신의 데이터베이스에서 데이터를 가져와 PDF 문서에 표시할 수 있습니다. Aspose.PDF 문서를 더 탐색하여 이 강력한 라이브러리가 제공하는 다른 기능과 가능성을 알아보세요.

### PDF 파일에 데이터베이스와 통합하기 위한 FAQ

#### 질문: Aspose.PDF for .NET을 MySQL, SQL Server, Oracle과 같은 다른 데이터베이스 유형과 함께 사용할 수 있나요?

A: 네, Aspose.PDF for .NET을 MySQL, SQL Server, Oracle 등과 같은 다양한 데이터베이스 유형과 함께 사용할 수 있습니다. Aspose.PDF for .NET은 데이터베이스, XML 파일 등을 포함한 다양한 데이터 소스에서 데이터를 읽는 기능을 제공합니다. 원하는 데이터베이스 유형에서 데이터를 검색하여 DataTable 또는 Aspose.PDF for .NET과 호환되는 다른 데이터 구조에 채울 수 있습니다.

#### 질문: PDF 문서에서 표의 모양을 사용자 지정하려면 어떻게 해야 하나요?

A: Aspose.PDF for .NET 라이브러리에서 제공하는 다양한 속성을 사용하여 PDF 문서에서 표 모양을 사용자 지정할 수 있습니다. 예를 들어, 표와 셀에 대해 다양한 테두리 스타일, 배경색, 글꼴 스타일 및 정렬을 설정할 수 있습니다. 표 모양을 사용자 지정하는 방법에 대한 자세한 내용은 Aspose.PDF for .NET 설명서를 참조하십시오.

#### 질문: 데이터베이스에서 가져온 데이터에 하이퍼링크나 대화형 요소를 추가할 수 있나요?

A: 네, 데이터베이스에서 가져온 데이터에 하이퍼링크나 다른 대화형 요소를 추가할 수 있습니다. Aspose.PDF for .NET은 PDF 문서에 하이퍼링크, 북마크 및 다른 대화형 요소를 추가하는 것을 지원합니다. 테이블에 가져오기 전에 DataTable의 콘텐츠를 조작하고 하이퍼링크나 다른 대화형 기능을 포함할 수 있습니다.

#### 질문: 행의 개수가 일정 개수를 초과하면 표를 페이지별로 나눌 수 있나요?

A: 네, 특정 행 수를 초과하는 경우 테이블을 페이지별로 나눌 수 있습니다. 이를 위해 다음을 사용할 수 있습니다.`IsInNewPage` Row 객체의 속성을 사용하여 특정 행 다음에 새 페이지가 시작되어야 함을 나타냅니다. 페이지당 표시할 행 수를 계산하고 설정할 수 있습니다.`IsInNewPage` 이에 따라 재산을 소유합니다.

#### 질문: 내장된 데이터베이스 데이터가 있는 PDF 문서를 DOCX나 XLSX와 같은 다른 파일 형식으로 내보내려면 어떻게 해야 합니까?

A: Aspose.PDF for .NET을 사용하면 PDF 문서를 DOCX(Microsoft Word) 및 XLSX(Microsoft Excel)를 포함한 다양한 다른 파일 형식으로 변환할 수 있습니다. Aspose.PDF for .NET 라이브러리를 Aspose.Words 및 Aspose.Cells와 같은 다른 Aspose 라이브러리와 함께 사용하여 이를 달성할 수 있습니다. 먼저 PDF 문서를 내장된 데이터베이스 데이터와 함께 저장한 다음 해당 Aspose 라이브러리를 사용하여 원하는 파일 형식으로 변환합니다.