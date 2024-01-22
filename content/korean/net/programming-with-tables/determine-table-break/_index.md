---
title: PDF 파일에서 테이블 나누기 결정
linktitle: PDF 파일에서 테이블 나누기 결정
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 테이블 나누기를 결정하는 방법을 알아보세요.
type: docs
weight: 60
url: /ko/net/programming-with-tables/determine-table-break/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 테이블 나누기를 결정하는 방법을 배우겠습니다. C#의 소스코드를 단계별로 설명하겠습니다. 이 튜토리얼이 끝나면 테이블이 페이지 여백을 초과하는지 확인하는 방법을 알게 됩니다. 시작하자!

## 1단계: 환경 설정
먼저 .NET용 Aspose.PDF를 사용하여 C# 개발 환경을 설정했는지 확인하세요. 라이브러리에 참조를 추가하고 필요한 네임스페이스를 가져옵니다.

## 2단계: PDF 문서 만들기
 이 단계에서는 새로운`Document` PDF 문서를 나타내는 개체입니다.

```csharp
pdf-Document = new Document();
```

이 문서는 섹션과 테이블을 추가하는 데 사용됩니다.

## 3단계: 섹션 및 테이블 추가
이제 PDF 문서에 섹션을 추가하고 이 섹션 안에 테이블을 생성하겠습니다.

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

또한 테이블의 상단 여백을 300포인트로 지정합니다. 필요에 따라 이 값을 조정할 수 있습니다.

## 4단계: 테이블 설정
이 단계에서는 열 너비 및 테두리와 같은 테이블 속성을 구성합니다.

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

여기서는 테이블 열의 너비와 셀 테두리를 정의합니다. 원하는 대로 이 값을 조정할 수 있습니다.

## 5단계: 표에 행과 셀 추가
이제 루프를 사용하여 테이블에 행과 셀을 만듭니다.

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

여기서는 테이블에 17개의 행을 만들고 각 행에 3개의 셀을 추가합니다. 필요에 따라 버클을 조정할 수 있습니다.

## 6단계: 테이블 나누기 결정
이제 페이지 높이와 테이블에 있는 개체의 전체 높이를 비교하여 테이블이 페이지 여백을 초과하는지 판단하겠습니다.

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

여백을 고려하여 페이지 높이와 개체의 전체 높이를 계산합니다. 차이가 10 이하이면 테이블이 페이지 여백을 초과합니다.

## 7단계: PDF 문서 저장
마지막으로 결과와 함께 PDF 문서를 저장합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

올바른 문서 디렉토리를 지정하십시오. 결과 PDF 파일은 결정된 테이블 나누기와 함께 저장됩니다.

### .NET용 Aspose.PDF를 사용하여 테이블 나누기 결정에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 객체 PDF 클래스 인스턴스화
Document pdf = new Document();
// PDF 문서 섹션 컬렉션에 섹션 추가
Aspose.Pdf.Page page = pdf.Pages.Add();
// 테이블 객체 인스턴스화
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
// 원하는 섹션의 단락 모음에 표를 추가합니다.
page.Paragraphs.Add(table1);
// 테이블의 열 너비로 설정
table1.ColumnWidths = "100 100 100";
// BorderInfo 개체를 사용하여 기본 셀 테두리 설정
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
// 다른 사용자 정의된 BorderInfo 개체를 사용하여 테이블 테두리 설정
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// MarginInfo 개체를 만들고 왼쪽, 아래쪽, 오른쪽 및 위쪽 여백을 설정합니다.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// MarginInfo 개체에 기본 셀 패딩을 설정합니다.
table1.DefaultCellPadding = margin;
// 카운터를 17로 늘리면 테이블이 깨집니다.
// 이 페이지에서는 더 이상 수용할 수 없기 때문에
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	// 테이블에 행을 만든 다음 행에 셀을 만듭니다.
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
// 페이지 높이 정보 가져오기
float PageHeight = (float)pdf.PageInfo.Height;
// 페이지 상단 및 하단 여백의 전체 높이 정보를 가져옵니다.
// 테이블 상단 여백 및 테이블 높이.
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

// 페이지 높이, 표 높이, 표 상단 여백 및 페이지 상단 표시
// 및 하단 여백 정보
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

// 페이지 위쪽 여백 + 페이지 아래쪽 여백의 합을 빼는지 확인하세요.
// + 페이지 높이에서 테이블 상단 여백 및 테이블 높이 이하
// 10보다 많음(평균 행은 10보다 클 수 있음)
if ((PageHeight - TotalObjectsHeight) <= 10)
	// 값이 10보다 작으면 메시지를 표시합니다.
	//다른 행을 배치할 수 없으며 새 행을 추가하면 표시됩니다.
	// 행, 테이블이 깨집니다. 행 높이 값에 따라 달라집니다.
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
// PDF 문서를 저장하세요
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 테이블 나누기를 결정하는 방법을 배웠습니다. 이 단계별 가이드를 사용하여 C# 프로젝트에서 테이블이 페이지 여백을 초과하는지 확인할 수 있습니다.

### PDF 파일의 테이블 나누기 결정에 대한 FAQ

#### Q: PDF 문서에서 표 나누기를 결정하는 목적은 무엇입니까?

A: PDF 문서에서 표 나누기를 결정하는 목적은 표가 페이지 여백을 초과하는지 확인하는 것입니다. 이렇게 하면 테이블의 내용이 사용 가능한 페이지 공간 내에 올바르게 표시됩니다. 테이블 나누기를 감지하면 콘텐츠 오버플로를 처리하고 이에 따라 테이블 레이아웃을 조정할 수 있습니다.

#### Q: 표의 상단 여백을 어떻게 조정하나요?

 A: 제공된 C# 소스 코드에서`table1.Margin.Top`재산. 필요에 따라 값을 늘리거나 줄여 테이블의 원하는 위쪽 여백을 설정합니다.

#### Q: 셀 색상, 글꼴 크기 등 표의 모양을 사용자 정의할 수 있나요?

A: 예, Aspose.PDF for .NET에서 제공하는 다양한 속성과 메서드를 사용하여 테이블과 해당 셀의 모양을 사용자 정의할 수 있습니다. 예를 들어 셀 배경색, 글꼴 크기, 글꼴 모음, 텍스트 정렬 등을 변경할 수 있습니다. 테이블 모양을 사용자 정의하는 방법에 대한 자세한 내용은 공식 문서를 참조하세요.

#### Q: 표가 페이지 여백을 초과하면 어떻게 되나요?

A: 표가 페이지 여백을 초과하면 내용이 잘리거나 겹쳐서 PDF 문서의 가독성과 구성이 어려워질 수 있습니다. 테이블 나누기를 감지하고 오버플로를 처리하면 콘텐츠가 사용 가능한 페이지 영역 내에 올바르게 표시되도록 할 수 있습니다.

#### Q: 동일한 PDF 문서에 있는 여러 테이블의 테이블 나누기를 결정할 수 있습니까?

A: 예, 동일한 PDF 문서의 여러 테이블에 대한 테이블 나누기를 결정할 수 있습니다. 콘텐츠 오버플로를 방지하려면 분석하려는 각 테이블에 대해 단계를 반복하고 필요에 따라 테이블 레이아웃을 조정하기만 하면 됩니다.