---
title: PDF 파일에 테이블 추가
linktitle: PDF 파일에 테이블 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 테이블을 쉽게 추가할 수 있습니다.
type: docs
weight: 40
url: /ko/net/programming-with-tables/add-table/
---
.NET용 Aspose.PDF는 개발자가 프로그래밍 방식으로 PDF 문서를 생성, 조작 및 변환할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 테이블을 추가하는 과정을 안내합니다. 제공된 코드 조각의 각 단계를 설명하고 자신의 프로젝트에서 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다.

## 소개

PDF 문서는 정보를 휴대용 형식으로 공유하고 보존하는 데 널리 사용됩니다. PDF 문서에 표를 추가하면 시각적 모양이 향상되고 데이터 프레젠테이션이 더욱 체계화되고 구조화될 수 있습니다. .NET용 Aspose.PDF는 기존 PDF 문서에 표를 추가하거나 처음부터 새 문서를 만드는 편리한 방법을 제공합니다.

## .NET용 Aspose.PDF란 무엇입니까?

Aspose.PDF for .NET은 .NET 개발자가 프로그래밍 방식으로 PDF 문서를 생성, 조작 및 변환할 수 있도록 하는 강력하고 기능이 풍부한 라이브러리입니다. 처음부터 PDF 파일 생성, 기존 PDF 문서 수정, PDF 파일 병합 또는 분할, 텍스트, 이미지 및 테이블 추가, PDF에서 데이터 추출 등을 포함한 광범위한 기능을 제공합니다. .NET용 Aspose.PDF를 사용하면 개발자는 복잡한 PDF 관련 작업을 자동화하고 고품질 PDF 솔루션을 제공할 수 있습니다.

## PDF 문서에 표 추가

.NET용 Aspose.PDF를 사용하여 PDF 문서에 표를 추가하려면 아래의 단계별 가이드를 따르십시오.

## 1단계: 원본 PDF 문서 로드

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

위의 코드 조각은 테이블을 추가하려는 소스 PDF 문서를 로드합니다. PDF 파일의 올바른 경로를 제공하십시오.

## 2단계: 테이블의 새 인스턴스 초기화

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

이 단계에서는 PDF 문서의 테이블을 나타내는 Table 클래스의 새 인스턴스를 만듭니다.

## 3단계: 표 테두리 색상 설정

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

여기서는 BorderInfo 클래스를 사용하여 테이블의 테두리 색상을 설정합니다. 요구 사항에 따라 테두리 스타일, 너비 및 색상을 사용자 정의할 수 있습니다.

## 4단계: 표 셀의 테두리 설정하기

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

또한 테이블 개체의 DefaultCellBorder 속성을 사용하여 테이블 셀의 테두리를 설정했습니다. 이렇게 하면 테이블의 각 셀에 지정된 테두리 스타일, 너비 및 색상이 적용됩니다.

## 5단계: 테이블에 행과 셀 추가하기

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

이 단계에서는 테이블에 10개의 행을 추가하는 루프를 만듭니다. 각 행 내에 샘플 데이터가 포함된 셀 3개를 추가합니다. 특정 요구 사항에 따라 코드를 수정하여 행과 셀을 추가할 수 있습니다.

## 6단계: 문서에 표 개체 추가

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// 테이블 객체가 포함된 업데이트된 문서 저장
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

마지막으로 해당 페이지의 Paragraphs 컬렉션을 사용하여 PDF 문서의 첫 번째 페이지에 표 개체를 추가합니다.

### .NET용 Aspose.PDF를 사용하여 테이블 추가에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//소스 PDF 문서 로드
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// 테이블의 새 인스턴스를 초기화합니다.
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// 표 테두리 색상을 LightGray로 설정
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 표 셀의 테두리 설정
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 루프를 만들어 10개의 행을 추가하세요.
for (int row_count = 1; row_count < 10; row_count++)
{
	// 테이블에 행 추가
	Aspose.Pdf.Row row = table.Rows.Add();
	// 표 셀 추가
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// 입력 문서의 첫 번째 페이지에 테이블 개체 추가
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// 테이블 객체가 포함된 업데이트된 문서 저장
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 테이블을 추가하는 단계별 프로세스를 설명했습니다. 소스 PDF 문서 로드, Table 클래스의 새 인스턴스 초기화, 표 테두리 색상 및 셀 테두리 설정, 표에 행과 셀 추가, 문서에 표 개체 추가 등을 다루었습니다. 이 가이드를 따르면 프로그래밍 방식으로 테이블을 PDF 문서에 쉽게 통합하고 특정 요구 사항에 따라 사용자 정의할 수 있습니다.

### PDF 파일에 테이블 추가에 대한 FAQ

#### Q: 테이블에 열을 더 추가할 수 있나요?

A: 예, 각 행에 추가되는 셀 수를 늘려 테이블에 더 많은 열을 추가할 수 있습니다. 제공된 예에서 각 행에는 3개의 열을 나타내는 3개의 셀이 있습니다. 각 행에 더 많은 셀을 추가하여 추가 열을 추가할 수 있습니다.

#### Q: 글꼴 크기, 스타일 등 표의 모양을 어떻게 변경할 수 있나요?

 답변: 글꼴 크기 및 스타일을 포함한 표의 모양을 사용자 정의할 수 있습니다.`Aspose.Pdf.Table` 그리고`Aspose.Pdf.TextFragment` 사물. 예를 들어 다음을 설정할 수 있습니다.`DefaultCellTextState` 속성을 사용하여 테이블 셀에 있는 텍스트의 글꼴 속성을 변경할 수 있습니다.

#### Q: 테이블의 셀을 병합할 수 있나요?

 A: 예, 다음을 사용하여 표의 셀을 병합할 수 있습니다.`MergeCells` 의 방법`Aspose.Pdf.Row` 수업. 이를 통해 여러 행과 열에 걸쳐 있는 셀을 만들 수 있습니다.

#### Q: 표 셀에 이미지나 기타 콘텐츠를 추가할 수 있나요?

A: 예, 이미지, 텍스트, 하이퍼링크 등을 포함하여 다양한 유형의 콘텐츠를 표 셀에 추가할 수 있습니다. .NET용 Aspose.PDF의 적절한 클래스를 사용하여 다양한 유형의 콘텐츠를 셀에 추가할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 .NET 5.0 이상 버전과 호환됩니까?

A: 예, .NET용 Aspose.PDF는 .NET 5.0 이상 버전과 호환됩니다. .NET Framework, .NET Core 및 .NET 5.0+를 포함한 다양한 .NET 플랫폼을 지원합니다.