---
title: 머리글 바닥글 섹션의 표
linktitle: 머리글 바닥글 섹션의 표
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서의 머리글/바닥글 섹션에 표를 추가하는 방법을 알아보세요.
type: docs
weight: 170
url: /ko/net/programming-with-stamps-and-watermarks/table-in-header-footer-section/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 머리글 또는 바닥글 섹션에 표를 추가하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드는 빈 PDF 문서를 만들고, 페이지를 추가하고, 머리글 섹션을 구성하고, 테이블을 만들고, 테이블에 행과 셀을 추가하고, 마지막으로 PDF 문서를 저장하는 방법을 보여줍니다.

## 1단계: 환경 설정

시작하기 전에 다음 사항이 있는지 확인하세요.

- 설치된 .NET 개발 환경.
- .NET용 Aspose.PDF 라이브러리가 다운로드되어 프로젝트에서 참조됩니다.

## 2단계: PDF 문서 및 페이지 만들기

 첫 번째 단계는 인스턴스를 생성하는 것입니다.`Document` 클래스를 선택하고 문서에 페이지를 추가합니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document 객체 인스턴스화
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// PDF 문서에 페이지 만들기
Aspose.Pdf.Page page = pdfDocument.Pages.Add();
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서를 저장하려는 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 헤더 섹션 구성

 이제 인스턴스를 생성하여 PDF 문서의 헤더 섹션을 구성하겠습니다.`HeaderFooter` 수업. 방법은 다음과 같습니다.

```csharp
// PDF 파일의 헤더 섹션 만들기
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// 페이지의 헤더 섹션 정의
page. Header = header;

// 헤더 섹션의 상단 여백 설정
header. Margin. Top = 20;
```

## 4단계: 테이블 생성

 이제 우리는 다음을 사용하여 테이블을 만들 것입니다.`Table` 클래스를 만들어 제목 섹션의 단락 컬렉션에 추가합니다. 방법은 다음과 같습니다.

```csharp
// 테이블 개체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// 헤더 섹션의 단락 컬렉션에 표를 추가합니다.
header.Paragraphs.Add(tab1);

// 테이블 열의 너비 정의
tab1.ColumnWidths = "60,300";
```

위의 코드는 지정된 너비의 두 열이 있는 테이블을 만듭니다.

## 5단계: 표에 행과 셀 추가

 이제 다음을 사용하여 테이블에 행과 셀을 추가하겠습니다.`Row` 수업과`Cell` 수업. 방법은 다음과 같습니다.

```csharp
// 테이블에 행을 만들고 셀을 추가합니다.
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in header section");
row1.BackgroundColor = Color.Gray;

// 첫 번째 행의 첫 번째 셀 병합
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// 테이블에 다른 행을 만들고 이미지가 있는 셀을 추가하세요.
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.BackgroundColor = Color.White;
Aspose.Pdf.Cell cell2 = row2.Cells.Add();
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";
img. FixWidth = 60;
cell2.Paragraphs.Add(img);
row2.Cells.Add("The logo is beautiful!");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
```

## 6단계: PDF 문서 저장

표가 헤더 섹션에 추가되면 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// PDF 파일을 저장하세요
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서를 저장하려는 디렉토리의 실제 경로로 바꾸십시오.

### .NET용 Aspose.PDF를 사용하는 머리글 바닥글 섹션의 테이블에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 빈 생성자를 호출하여 Document 인스턴스를 인스턴스화합니다.
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document();

// PDF 문서에 페이지 만들기
Aspose.Pdf.Page page = pdfDocument.Pages.Add();

// PDF 파일의 헤더 섹션 만들기
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

//PDF 파일의 홀수 헤더 설정
page.Header = header;

// 머리글 섹션의 위쪽 여백을 설정합니다.
header.Margin.Top = 20;

// 테이블 객체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

// 원하는 섹션의 단락 모음에 표를 추가합니다.
header.Paragraphs.Add(tab1);

// BorderInfo 개체를 사용하여 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// 테이블의 열 너비로 설정
tab1.ColumnWidths = "60 300";
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
img.File = dataDir + "aspose-logo.jpg";

// 테이블에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("Table in Header Section");
row1.BackgroundColor = Color.Gray;

// 첫 번째 행의 행 범위 값을 2로 설정합니다.
tab1.Rows[0].Cells[0].ColSpan = 2;
tab1.Rows[0].Cells[0].DefaultCellTextState.ForegroundColor = Color.Cyan;
tab1.Rows[0].Cells[0].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// 테이블에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row row2 = tab1.Rows.Add();

// Row2의 배경색을 설정합니다.
row2.BackgroundColor = Color.White;

// 이미지가 들어있는 셀을 추가하세요
Aspose.Pdf.Cell cell2 = row2.Cells.Add();

// 이미지 너비를 60으로 설정
img.FixWidth = 60;

// 테이블 셀에 이미지 추가
cell2.Paragraphs.Add(img);
row2.Cells.Add("Logo is looking fine !");
row2.Cells[1].DefaultCellTextState.Font = FontRepository.FindFont("Helvetica");

// 텍스트의 세로 정렬을 가운데 정렬로 설정합니다.
row2.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Center;
row2.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;

// PDF 파일 저장
pdfDocument.Save(dataDir + "TableInHeaderFooterSection_out.pdf");

```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 PDF 문서의 머리글 또는 바닥글 섹션에 표를 추가하는 방법을 배웠습니다. 이제 PDF 문서에 추가 정보를 표시하는 표를 추가하여 머리글과 바닥글을 사용자 정의할 수 있습니다.

### 머리글 바닥글 섹션의 표에 대한 FAQ

#### Q: PDF 문서의 머리글이나 바닥글 섹션에 표를 추가하는 목적은 무엇입니까?

A: PDF 문서의 머리글 또는 바닥글 섹션에 표를 추가하면 제목, 부제, 로고 또는 문서의 각 페이지에 일관되게 표시하려는 기타 콘텐츠와 같은 구조화되고 구성된 정보를 표시할 수 있습니다.

#### Q: 제공된 C# 소스 코드는 어떻게 PDF 문서의 머리글 또는 바닥글 섹션에 표를 추가합니까?

답변: 코드는 빈 PDF 문서 만들기, 페이지 추가, 머리글 섹션 구성, 행과 셀이 포함된 테이블 만들기, 마지막으로 PDF 문서 저장 과정을 보여줍니다. 결과는 PDF 문서의 헤더 섹션에 표시되는 테이블입니다.

#### Q: 테두리, 배경색, 텍스트 스타일 등 표 셀의 모양을 사용자 정의할 수 있습니까?

A: 예, 셀 테두리, 배경색, 텍스트 스타일, 글꼴, 글꼴 크기 등과 같은 속성을 설정하여 표 셀의 모양을 사용자 정의할 수 있습니다.

#### Q: PDF 문서의 헤더 부분에 표를 어떻게 추가하나요?

A: 코드는 표를 헤더 섹션의 단락 컬렉션에 추가하여 표가 각 페이지의 헤더에 표시되도록 합니다.

#### Q: 필요에 따라 테이블에 행과 셀을 더 추가할 수 있습니까?

 A: 물론입니다. 다음을 사용하여 테이블에 더 많은 행과 셀을 추가할 수 있습니다.`Rows.Add()` 그리고`Cells.Add()` 행동 양식. 이를 통해 테이블 내용을 원하는 대로 구성할 수 있습니다.

#### Q: 테이블 열의 너비를 조정할 수 있나요?
 A: 예, 다음을 사용하여 테이블 열의 너비를 조정할 수 있습니다.`ColumnWidths` 재산. 이를 통해 테이블의 레이아웃을 제어할 수 있습니다.

#### Q: 표 내의 여러 열이나 행에 걸쳐 셀을 확장하려면 어떻게 해야 합니까?
 A: 여러 열에 걸쳐 셀을 확장하려면 다음을 사용할 수 있습니다.`ColSpan` 해당 셀의 속성입니다. 마찬가지로 다음을 사용할 수 있습니다.`RowSpan` 여러 행에 걸쳐 셀을 확장하는 속성입니다.

#### 질문: PDF 문서의 머리글과 바닥글 섹션 모두에 표를 추가하려면 어떻게 됩니까?

A: 머리글과 바닥글 섹션 모두에 대해 비슷한 접근 방식을 따를 수 있습니다. 간단히`HeaderFooter` 바닥글의 인스턴스를 구성하고 해당 단락 컬렉션에 표를 추가합니다.

#### Q: 표 셀 내에서 이미지를 사용할 수 있나요? 어떻게 사용하나요?

 A: 예, 표 셀 내에 이미지를 추가할 수 있습니다. 코드 예제에서는`Image` 개체의 파일 경로와 크기를 설정한 다음 셀의 단락에 추가합니다.

#### 질문: PDF 문서의 모든 페이지에 표가 일관되게 표시되도록 하려면 어떻게 해야 합니까?

 A: 다음을 사용하여 머리글이나 바닥글 섹션에 표를 추가하면`HeaderFooter` 예를 들어 Aspose.PDF는 테이블이 각 페이지에 일관되게 나타나도록 보장하여 균일한 레이아웃을 제공합니다.