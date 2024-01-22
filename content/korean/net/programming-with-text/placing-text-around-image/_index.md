---
title: PDF 파일의 이미지 주위에 텍스트 배치하기
linktitle: PDF 파일의 이미지 주위에 텍스트 배치하기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 이미지 주위에 텍스트를 배치하는 방법을 알아보세요.
type: docs
weight: 260
url: /ko/net/programming-with-text/placing-text-around-image/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일의 이미지 주위에 텍스트를 배치하는 방법을 설명합니다. 제공된 C# 소스 코드를 사용하여 테이블을 만들고, 이미지를 추가하고, 이미지 주위에 텍스트를 배치하는 과정을 단계별로 살펴보겠습니다.

## 요구사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉터리 설정

 먼저 생성된 PDF 파일을 저장할 디렉터리의 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir`변수를 원하는 디렉터리의 경로로 바꿉니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 및 페이지 만들기

 다음으로`Document` 개체를 클릭하고 다음을 사용하여 개체에 페이지를 추가합니다.`Pages.Add()` 방법.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 3단계: 테이블 생성

 우리는 다음을 사용하여 테이블을 만듭니다.`Table` 클래스를 만들어 페이지의 단락 컬렉션에 추가하세요.

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
page.Paragraphs.Add(table1);
```

## 4단계: 표 열 너비 및 여백 설정

 테이블의 열 너비를 설정하고`MarginInfo` 여백을 설정하는 개체입니다.

```csharp
table1. ColumnWidths = "120,270";
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;
table1. DefaultCellPadding = margin;
```

## 5단계: 테이블에 이미지 추가

 우리는`Image` 객체에서 이미지 파일 경로를 지정하고 이미지의 고정 높이와 너비를 설정합니다. 그런 다음 표 셀의 단락 컬렉션에 이미지를 추가합니다.

```csharp
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
logo.File = dataDir + "aspose-logo.jpg";
logo.FixHeight = 120;
logo.FixWidth = 110;
row1.Cells.Add();
row1.Cells[0].Paragraphs.Add(logo);
```

## 6단계: 이미지 주위에 텍스트 추가

 HTML 형식의 텍스트를 포함하는 문자열 변수를 생성하고`HtmlFragment`물체. 그런 다음 이미지가 포함된 테이블 셀에 HTML 텍스트를 추가합니다.

```csharp
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b>Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>" ;

Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
row1.Cells[1].Paragraphs.Add(TitleText);
```

## 7단계: 추가 텍스트 추가

 우리는 또 다른 것을 만듭니다`HtmlFragment` 추가 HTML 형식 텍스트가 포함된 개체를 만들어 별도의 테이블 셀에 추가합니다.

```csharp
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
```

## 8단계: PDF 문서 저장

마지막으로 PDF 문서를 지정된 출력 파일에 저장합니다.

```csharp
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 이미지 주위에 텍스트를 배치하기 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 객체 인스턴스화
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
// PDF에 페이지 만들기
Aspose.Pdf.Page page = doc.Pages.Add();
// 테이블 객체 인스턴스화
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
// 원하는 섹션의 단락 모음에 표를 추가합니다.
page.Paragraphs.Add(table1);
// 테이블의 열 너비로 설정
table1.ColumnWidths = "120 270";
// MarginInfo 개체를 만들고 왼쪽, 아래쪽, 오른쪽 및 위쪽 여백을 설정합니다.
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
// MarginInfo 개체에 기본 셀 패딩을 설정합니다.
table1.DefaultCellPadding = margin;
// 테이블에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row row1 = table1.Rows.Add();
// 이미지 객체 생성
Aspose.Pdf.Image logo = new Aspose.Pdf.Image();
// 이미지 파일 경로 지정
logo.File = dataDir + "aspose-logo.jpg";
// 이미지 고정 높이 지정
logo.FixHeight = 120;
// 이미지 고정 너비 지정
logo.FixWidth = 110;
row1.Cells.Add();
// 표 셀의 단락 컬렉션에 이미지 추가
row1.Cells[0].Paragraphs.Add(logo);
// html 태그가 포함된 텍스트로 문자열 변수 만들기
string TitleString = "<font face=\"Arial\" size=6 color=\"#101090\"><b> Aspose.Pdf for .NET</b></font>";
string BodyString1 = "<font face=\"Arial\" size=2><br/>Aspose.Pdf for .NET is a non-graphical PDF� document reporting component that enables .NET applications to <b> create PDF documents from scratch </b> without utilizing Adobe Acrobat�. Aspose.Pdf for .NET is very affordably priced and offers a wealth of strong features including: compression, tables, graphs, images, hyperlinks, security and custom fonts. </font>";
//이미지 오른쪽에 추가할 텍스트 개체를 만듭니다.
Aspose.Pdf.HtmlFragment TitleText = new Aspose.Pdf.HtmlFragment(TitleString + BodyString1);
row1.Cells.Add();
// 테이블 셀에 HTML 텍스트가 포함된 텍스트 단락을 추가합니다.
row1.Cells[1].Paragraphs.Add(TitleText);
// 행 내용의 수직 정렬을 위쪽으로 설정
row1.Cells[1].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
// 테이블에 행을 만든 다음 행에 셀을 만듭니다.
Aspose.Pdf.Row SecondRow = table1.Rows.Add();
SecondRow.Cells.Add();
// 두 번째 행의 행 범위 값을 2로 설정합니다.
SecondRow.Cells[0].ColSpan = 2;
// 두 번째 행의 수직 정렬을 위쪽으로 설정
SecondRow.Cells[0].VerticalAlignment = Aspose.Pdf.VerticalAlignment.Top;
string SecondRowString = "<font face=\"Arial\" size=2>Aspose.Pdf for .NET supports the creation of PDF files through API and XML or XSL-FO templates. Aspose.Pdf for .NET is very easy to use and is provided with 14 fully featured demos written in both C# and Visual Basic.</font>";
Aspose.Pdf.HtmlFragment SecondRowText = new Aspose.Pdf.HtmlFragment(SecondRowString);
// 테이블 셀에 HTML 텍스트가 포함된 텍스트 단락을 추가합니다.
SecondRow.Cells[0].Paragraphs.Add(SecondRowText);
// PDF 파일 저장
doc.Save(dataDir + "PlacingTextAroundImage_out.pdf");
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 이미지 주위에 텍스트를 배치하는 방법을 배웠습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 테이블을 만들고, 이미지를 추가하고, PDF 문서에서 이미지 주위에 텍스트를 배치할 수 있습니다.

### FAQ

#### Q: "PDF 파일의 이미지 주위에 텍스트 배치" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일의 이미지 주위에 텍스트 배치" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 이미지 주위에 텍스트를 배치하는 방법을 보여줍니다. 이 자습서에서는 테이블을 만들고, 이미지를 추가하고, 이미지 주위에 텍스트를 배치하는 데 도움이 되는 단계별 가이드와 C# 소스 코드를 제공합니다.

#### Q: PDF 문서의 이미지 주위에 텍스트를 배치하려는 이유는 무엇입니까?

답변: 이미지 주위에 텍스트를 배치하면 PDF 문서의 시각적 표현이 향상되어 더욱 매력적이고 유익하게 만들어집니다. 이 기술은 미적으로 보기 좋은 방식으로 이미지와 텍스트를 결합하려는 문서, 브로셔, 보고서 및 기타 자료에 자주 사용됩니다.

#### Q: 문서 디렉터리를 어떻게 설정합니까?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 생성된 PDF 파일을 저장하려는 디렉터리의 경로로 변수를 지정합니다.

#### Q: 테이블을 생성하고 테이블에 이미지를 추가하려면 어떻게 해야 합니까?

 A: 튜토리얼에서는 다음을 사용하여 테이블을 생성하는 과정을 안내합니다.`Table` 클래스를 사용하여 테이블에 이미지를 추가합니다.`Image` 수업. 테이블 셀에 이미지 파일을 추가하기 전에 이미지 파일 경로, 높이 및 너비를 지정합니다.

#### Q: 이미지 주위에 텍스트를 배치하려면 어떻게 해야 합니까?

 A: 이미지 주위에 텍스트를 배치하려면`HtmlFragment` 수업. 이 텍스트에는 제목과 본문 텍스트가 모두 포함됩니다. 그런 다음 이 HTML 텍스트를 이미지 셀에 인접한 테이블 셀에 추가합니다.

#### Q: 텍스트와 이미지의 모양을 맞춤설정할 수 있나요?

A: 예, HTML 태그와 속성을 사용하여 텍스트와 이미지의 모양을 사용자 정의할 수 있습니다. 예를 들어 텍스트의 글꼴 크기, 색상, 스타일 및 정렬을 설정할 수 있습니다. 또한 이미지의 크기와 치수를 조정할 수 있습니다.

#### Q: PDF 문서를 어떻게 저장하나요?

 A: 테이블에 이미지와 텍스트를 추가한 후 다음을 사용하여 PDF 문서를 저장할 수 있습니다.`Save` 의 방법`Document` 수업. 원하는 출력 파일 경로를 인수로 제공하십시오.`Save` 방법.

#### Q: 이 튜토리얼에서 예상되는 결과는 무엇입니까?

A: 튜토리얼을 따르고 제공된 C# 코드를 실행하면 이미지 주위에 텍스트를 배치하는 방법을 보여주는 PDF 문서가 생성됩니다. 출력 문서에는 이미지와 텍스트가 주위에 배치된 표가 포함됩니다.

#### Q: JPG 외에 다른 이미지 형식을 사용할 수 있나요?

 A: 예, Aspose.PDF 라이브러리에서 지원하는 PNG, BMP, GIF 등과 같은 다양한 이미지 형식을 사용할 수 있습니다. 생성할 때`Image` 개체에서 원하는 이미지 형식의 파일 경로를 지정합니다.

#### Q: 이 튜토리얼에는 유효한 Aspose 라이선스가 필요합니까?

A: 예, 이 튜토리얼이 올바르게 작동하려면 유효한 Aspose 라이선스가 필요합니다. Aspose 웹사이트에서 정식 라이선스를 구매하거나 30일 임시 라이선스를 얻을 수 있습니다.