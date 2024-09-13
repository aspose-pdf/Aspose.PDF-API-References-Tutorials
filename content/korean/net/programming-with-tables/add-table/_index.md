---
title: PDF 파일에 표 추가
linktitle: PDF 파일에 표 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 쉽게 표를 추가할 수 있습니다.
type: docs
weight: 40
url: /ko/net/programming-with-tables/add-table/
---
Aspose.PDF for .NET은 개발자가 PDF 문서를 프로그래밍 방식으로 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 테이블을 추가하는 과정을 안내합니다. 제공된 코드 조각의 각 단계를 설명하고, 해당 기능을 이해하고 자신의 프로젝트에서 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다.

## 소개

PDF 문서는 휴대용 형식으로 정보를 공유하고 보존하는 데 널리 사용됩니다. PDF 문서에 표를 추가하면 시각적 모양이 향상되고 데이터 표현이 더 체계적이고 구조화될 수 있습니다. Aspose.PDF for .NET은 기존 PDF 문서에 표를 추가하거나 처음부터 새 표를 만드는 편리한 방법을 제공합니다.

## .NET용 Aspose.PDF란 무엇인가요?

Aspose.PDF for .NET은 강력하고 기능이 풍부한 라이브러리로, .NET 개발자가 PDF 문서를 프로그래밍 방식으로 만들고, 조작하고, 변환할 수 있도록 해줍니다. PDF 파일을 처음부터 만들고, 기존 PDF 문서를 수정하고, PDF 파일을 병합하거나 분할하고, 텍스트, 이미지, 표를 추가하고, PDF에서 데이터를 추출하는 등 다양한 기능을 제공합니다. Aspose.PDF for .NET을 사용하면 개발자는 복잡한 PDF 관련 작업을 자동화하고 고품질 PDF 솔루션을 제공할 수 있습니다.

## PDF 문서에 표 추가

Aspose.PDF for .NET을 사용하여 PDF 문서에 표를 추가하려면 아래 단계별 가이드를 따르세요.

## 1단계: 소스 PDF 문서 로드

```csharp
string dataDir = RunExamples.GetDataDir_AsposePdf_Tables();
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
```

위의 코드 조각은 테이블을 추가하려는 소스 PDF 문서를 로드합니다. PDF 파일에 대한 올바른 경로를 제공해야 합니다.

## 2단계: 테이블의 새 인스턴스 초기화

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

이 단계에서는 PDF 문서의 표를 나타내는 Table 클래스의 새 인스턴스를 만듭니다.

## 3단계: 테이블 테두리 색상 설정

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

여기서는 BorderInfo 클래스를 사용하여 테이블의 테두리 색상을 설정합니다. 요구 사항에 따라 테두리 스타일, 너비 및 색상을 사용자 정의할 수 있습니다.

## 4단계: 테이블 셀의 테두리 설정

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

또한 테이블 객체의 DefaultCellBorder 속성을 사용하여 테이블 셀의 테두리를 설정합니다. 이렇게 하면 테이블의 각 셀에 지정된 테두리 스타일, 너비 및 색상이 지정됩니다.

## 5단계: 표에 행과 셀 추가

```csharp
for (int row_count = 1; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. Cells. Add("Column("+row_count+",1)");
   

  row. Cells. Add("Column("+row_count+",2)");
     row. Cells. Add("Column("+row_count+",3)");
}
```

이 단계에서는 루프를 만들어 테이블에 10개의 행을 추가합니다. 각 행 내에서 샘플 데이터가 있는 3개의 셀을 추가합니다. 코드를 수정하여 특정 요구 사항에 따라 행과 셀을 추가할 수 있습니다.

## 6단계: 문서에 테이블 개체 추가

```csharp
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// 테이블 객체를 포함하는 업데이트된 문서를 저장합니다.
doc.Save(dataDir);
Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

마지막으로, 해당 페이지의 Paragraphs 컬렉션을 사용하여 PDF 문서의 첫 번째 페이지에 테이블 객체를 추가합니다.

### .NET용 Aspose.PDF를 사용하여 테이블을 추가하기 위한 예제 소스 코드

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

//소스 PDF 문서 로드
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "AddTable.pdf");
// 테이블의 새 인스턴스를 초기화합니다.
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
// 테이블 테두리 색상을 LightGray로 설정하세요
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 테이블 셀의 테두리 설정
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
// 10개의 행을 추가하기 위한 루프를 생성합니다.
for (int row_count = 1; row_count < 10; row_count++)
{
	// 테이블에 행 추가
	Aspose.Pdf.Row row = table.Rows.Add();
	// 표 셀 추가
	row.Cells.Add("Column (" + row_count + ", 1)");
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
// 입력 문서의 첫 번째 페이지에 테이블 객체 추가
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "document_with_table_out.pdf";
// 테이블 객체를 포함하는 업데이트된 문서를 저장합니다.
doc.Save(dataDir);

Console.WriteLine("\nText added successfully to an existing pdf file.\nFile saved at " + dataDir);       
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 표를 추가하는 단계별 프로세스를 설명했습니다. 소스 PDF 문서 로드, Table 클래스의 새 인스턴스 초기화, 표 테두리 색상 및 셀 테두리 설정, 표에 행과 셀 추가, 문서에 표 객체 추가를 다루었습니다. 이 가이드를 따르면 PDF 문서에 프로그래밍 방식으로 표를 쉽게 통합하고 특정 요구 사항에 맞게 사용자 정의할 수 있습니다.

### PDF 파일에 테이블 추가에 대한 FAQ

#### 질문: 표에 열을 더 추가할 수 있나요?

A: 네, 각 행에 추가된 셀의 수를 늘려서 표에 열을 더 추가할 수 있습니다. 제공된 예에서 각 행은 세 개의 열을 나타내는 세 개의 셀을 가지고 있습니다. 각 행에 셀을 더 추가하여 열을 추가할 수 있습니다.

#### 질문: 글꼴 크기, 스타일 등 표의 모양을 어떻게 변경할 수 있나요?

 A: 글꼴 크기 및 스타일을 포함하여 표의 모양을 사용자 정의하려면 속성을 설정하세요.`Aspose.Pdf.Table` 그리고`Aspose.Pdf.TextFragment` 객체. 예를 들어, 다음을 설정할 수 있습니다.`DefaultCellTextState` 테이블 셀의 텍스트 글꼴 속성을 변경하는 속성입니다.

#### 질문: 표의 셀을 병합할 수 있나요?

 A: 예, 다음을 사용하여 표의 셀을 병합할 수 있습니다.`MergeCells` 의 방법`Aspose.Pdf.Row` 클래스. 이를 통해 여러 행과 열에 걸쳐 있는 셀을 만들 수 있습니다.

#### 질문: 표 셀에 이미지나 다른 콘텐츠를 추가할 수 있나요?

A: 네, 이미지, 텍스트, 하이퍼링크 등 다양한 유형의 콘텐츠를 표 셀에 추가할 수 있습니다. .NET용 Aspose.PDF의 적절한 클래스를 사용하여 다양한 유형의 콘텐츠를 셀에 추가할 수 있습니다.

#### 질문: Aspose.PDF for .NET은 .NET 5.0 이상 버전과 호환됩니까?

A: 네, Aspose.PDF for .NET은 .NET 5.0 이상 버전과 호환됩니다. .NET Framework, .NET Core, .NET 5.0+를 포함한 다양한 .NET 플랫폼을 지원합니다.