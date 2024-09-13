---
title: 창에 자동 맞춤
linktitle: 창에 자동 맞춤
second_title: .NET API 참조를 위한 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 생성 시 창에 자동으로 맞춤을 구현하는 단계별 가이드입니다.
type: docs
weight: 50
url: /ko/net/programming-with-tables/auto-fit-to-window/
---
다음 문서는 제공된 C# 소스 코드를 사용하여 .NET용 Aspose.PDF 라이브러리를 사용하여 Auto Fit To Window 기능을 구현하는 방법에 대한 단계별 가이드입니다. Auto Fit To Window 기능을 사용하면 뷰잉 창에 맞게 레이아웃이 조정된 PDF 파일을 생성할 수 있습니다. 이 기능은 사용자가 사용하는 PDF 리더 창의 크기에 맞게 PDF 문서를 자동으로 조정하려는 경우에 특히 유용합니다.

## 1단계: 환경 설정

시작하기 전에 컴퓨터에 .NET용 Aspose.PDF 라이브러리를 설치해야 합니다. 또한 프로젝트에 필요한 네임스페이스를 가져오세요.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 만들기

 시작하려면 다음을 만들어야 합니다.`Document` 기본 생성자를 호출하여 객체를 생성합니다.

```csharp
Document doc = new Document();
```

 다음으로, 섹션을 만듭니다.`Pdf` 물체.

```csharp
Page sec1 = doc.Pages.Add();
```

## 3단계: 문서에 표 추가

 이 단계에서는 PDF 문서에 표를 추가합니다. 먼저 다음을 만듭니다.`Table` 물체.

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

다음으로, 섹션의 문단 컬렉션에 표를 추가합니다.

```csharp
sec1.Paragraphs.Add(tab1);
```

##  4단계: 테이블 모양 사용자 지정

셀 테두리와 여백 등의 속성을 설정하여 표의 모양을 사용자 지정할 수 있습니다.

```csharp
tab1. ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);

Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin.Right = 5f;
margin. Bottom = 5f;

tab1. DefaultCellPadding = margin;
```

##  4단계: 표에 행과 셀 추가

이제 테이블에 행과 셀을 추가해 보겠습니다. 행을 만들고 그 행에 셀을 추가하는 것으로 시작합니다.

```csharp
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");

Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
```

## 5단계: 문서 저장

마지막으로 출력 파일 경로를 지정하고 문서를 저장합니다.

```csharp
dataDir = dataDir + "AutoFitToWindow_out.pdf";
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 창에 자동 맞춤을 위한 예제 소스 코드

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 빈 생성자를 호출하여 Pdf 객체를 인스턴스화합니다.
Document doc = new Document();
// Pdf 객체에 섹션을 만듭니다.
Page sec1 = doc.Pages.Add();

// 테이블 객체 인스턴스화
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
// 원하는 섹션의 문단 모음에 표를 추가합니다.
sec1.Paragraphs.Add(tab1);

// 표의 열 너비로 설정
tab1.ColumnWidths = "50 50 50";
tab1.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;

// BorderInfo 객체를 사용하여 기본 셀 테두리 설정
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

// 다른 사용자 지정 BorderInfo 개체를 사용하여 테이블 테두리 설정
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
// MarginInfo 객체를 생성하고 왼쪽, 아래쪽, 오른쪽 및 위쪽 여백을 설정합니다.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;

// MarginInfo 개체에 기본 셀 패딩을 설정합니다.
tab1.DefaultCellPadding = margin;

//표에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");

dataDir = dataDir + "AutoFitToWindow_out.pdf";
// 테이블 객체를 포함하는 업데이트된 문서를 저장합니다.
doc.Save(dataDir);
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 Auto Fit To Window 기능이 있는 PDF 파일을 생성하는 방법을 알아보았습니다. 이 기능은 PDF 문서가 보기 창의 크기에 자동으로 맞춰지기를 원할 때 매우 유용합니다. Aspose.PDF for .NET은 PDF 파일을 생성하고 조작하기 위한 다른 많은 강력한 기능을 제공합니다. 이 라이브러리를 더 탐색하여 모든 기능을 발견해 보시기 바랍니다.

### 자주 묻는 질문

#### 질문: PDF 생성 시 창에 자동 맞춤 기능의 목적은 무엇인가요?

A: PDF 생성의 창에 자동 맞춤 기능은 PDF 문서의 레이아웃이 사용자가 사용하는 PDF 리더 창의 크기에 자동으로 조정되도록 합니다. 이를 통해 더 나은 보기가 가능하고 콘텐츠가 사용 가능한 보기 영역에 완벽하게 들어맞도록 합니다.

#### 질문: 글꼴 크기, 색상 등 표의 모양을 사용자 지정할 수 있나요?

A: 네, Aspose.PDF for .NET을 사용하여 PDF 문서에서 표 모양을 사용자 지정할 수 있습니다. 제공된 코드 조각은 셀 테두리, 여백 및 열 너비와 같은 속성을 설정하는 방법을 보여줍니다. 표와 그 내용의 글꼴 크기, 색상 및 기타 스타일링 측면을 추가로 사용자 지정할 수 있습니다.

#### 질문: Aspose.PDF for .NET을 C# 프로젝트에 통합하려면 어떻게 해야 하나요?

A: C# 프로젝트에서 Aspose.PDF for .NET을 사용하려면 먼저 컴퓨터에 Aspose.PDF for .NET 라이브러리를 설치해야 합니다. 그런 다음 C# 프로젝트에 라이브러리에 대한 참조를 추가할 수 있습니다. 마지막으로 Aspose.PDF for .NET에서 제공하는 클래스와 메서드에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

#### 질문: .NET용 Aspose.PDF는 .NET Core 애플리케이션과 호환됩니까?

A: 네, Aspose.PDF for .NET은 .NET Core 애플리케이션과 호환됩니다. .NET Framework, .NET Core, .NET 5.0+를 포함한 다양한 .NET 플랫폼을 지원합니다.

#### 질문: PDF 문서에 표를 더 추가할 수 있나요?

A: 네, 코드 조각에서 보여준 것과 비슷한 단계를 따라 PDF 문서에 여러 테이블을 추가할 수 있습니다. 간단히 새 인스턴스를 만듭니다.`Aspose.Pdf.Table` 클래스를 만들어 PDF 문서의 다른 섹션이나 페이지에 추가합니다.