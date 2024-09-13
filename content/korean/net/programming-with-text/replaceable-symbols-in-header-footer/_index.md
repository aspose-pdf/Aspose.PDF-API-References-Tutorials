---
title: 헤더 푸터의 교체 가능한 심볼
linktitle: 헤더 푸터의 교체 가능한 심볼
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서의 머리글과 바닥글에 바꿀 수 있는 기호를 사용하는 방법을 알아보세요.
type: docs
weight: 320
url: /ko/net/programming-with-text/replaceable-symbols-in-header-footer/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 머리글과 바닥글에 대체 가능한 심볼을 사용하는 방법을 설명합니다. PDF를 만들고, 여백을 설정하고, 대체 가능한 심볼이 있는 머리글과 바닥글을 추가하고, 제공된 C# 소스 코드를 사용하여 PDF를 저장하는 단계별 프로세스를 살펴보겠습니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉토리 설정

 먼저 생성된 PDF 파일을 저장할 디렉토리 경로를 설정해야 합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 원하는 디렉토리의 경로를 담은 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 및 페이지 만들기

 다음으로 새 PDF 문서를 만들고 이를 사용하여 페이지를 추가합니다.`Document` 수업과`Page` Aspose.PDF 라이브러리의 클래스입니다.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 3단계: 여백 설정

 우리는 페이지의 여백을 다음을 사용하여 설정합니다.`MarginInfo` 클래스. 요구 사항에 따라 여백 값을 조정하세요.

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## 4단계: 교체 가능한 기호가 있는 헤더 추가

 우리는 만듭니다`HeaderFooter` 페이지에 대한 객체를 추가하고`TextFragment` 대체 가능한 기호가 포함되어 있습니다.

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
// 원하는 경우 텍스트 속성을 설정하세요
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

// 필요에 따라 더 많은 TextFragments를 추가하거나 사용자 정의하세요
```

## 5단계: 교체 가능한 기호로 바닥글 추가

 마찬가지로 우리는 다음을 생성합니다.`HeaderFooter` 페이지 바닥글에 대한 객체를 추가하고`TextFragment` 대체 가능한 기호가 있는 개체입니다.

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

// 필요에 따라 더 많은 TextFragments를 추가하거나 사용자 정의하세요

hfFoot.Paragraphs.Add(tab2);
```

## 6단계: PDF 문서 저장

마지막으로 PDF 문서를 지정된 출력 파일에 저장합니다.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 헤더 푸터의 교체 가능한 심볼에 대한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//sec1.PageInfo의 Margin 속성에 marginInfo 인스턴스를 할당합니다.
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
// 헤더로 표시할 콘텐츠를 저장할 텍스트 문단을 인스턴스화합니다.
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
// 섹션에 대한 HeaderFooter 객체를 만듭니다.
HeaderFooter hfFoot = new HeaderFooter();
// HeaderFooter 객체를 홀수 및 짝수 바닥글로 설정합니다.
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
// 현재 페이지 번호 또는 총 페이지 번호를 포함하는 텍스트 단락을 추가합니다.
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
// 테이블 객체 인스턴스화
Table tab2 = new Table();
// 원하는 섹션의 문단 모음에 표를 추가합니다.
hfFoot.Paragraphs.Add(tab2);
// 표의 열 너비로 설정
tab2.ColumnWidths = "165 172 165";
//표에 행을 만든 다음 행에 셀을 만듭니다.
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
// 텍스트의 수직 정렬을 중앙 정렬로 설정합니다.
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java는 Aspose에서 제공하는 모든 Java 구성 요소를 컴파일한 것입니다. 각 Java 구성 요소의 최신 버전을 포함하도록 매일 #$NL" + "컴파일합니다. #$NL " + "Aspose.Total for Java 개발자는 다양한 애플리케이션을 만들 수 있습니다. #$NL #$NL #$NP" + "Aspose.Total for Java는 Aspose에서 제공하는 모든 Java 구성 요소를 컴파일한 것입니다. 각 Java 구성 요소의 최신 버전을 포함하도록 매일 #$NL" + "컴파일합니다. #$NL " + "Aspose.Total for Java 개발자는 다양한 애플리케이션을 만들 수 있습니다. #$NL #$NL #$NP" + "Aspose.Total for Java는 Aspose에서 제공하는 모든 Java 구성 요소를 컴파일한 것입니다. 각 Java 구성 요소의 최신 버전을 포함하도록 매일 #$NL" + "컴파일합니다. #$NL " + "Aspose.Total을 사용하면 Java 개발자는 다양한 애플리케이션을 만들 수 있습니다. #$NL #$NL"))
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
// 원하는 섹션의 문단 모음에 표를 추가합니다.
page.Paragraphs.Add(table);
// BorderInfo 객체를 사용하여 기본 셀 테두리 설정
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
// 다른 사용자 지정 BorderInfo 개체를 사용하여 테이블 테두리 설정
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//표에 행을 만든 다음 행에 셀을 만듭니다.
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 머리글과 바닥글에 대체 가능한 심볼을 사용하는 방법을 알아보았습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF를 만들고, 여백을 설정하고, 대체 가능한 심볼이 있는 머리글과 바닥글을 추가하고, PDF를 저장할 수 있습니다.

### 자주 묻는 질문

#### 질문: "헤더 푸터의 바꿀 수 있는 기호" 튜토리얼의 목적은 무엇인가요?

A: "헤더 푸터의 대체 가능한 심볼" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서의 헤더와 푸터에 대체 가능한 심볼을 추가하는 과정을 안내합니다. 대체 가능한 심볼을 사용하면 PDF를 생성할 때 특정 플레이스홀더를 실제 값으로 동적으로 대체할 수 있습니다.

#### 질문: PDF 머리글과 바닥글에서 대체 가능한 기호는 무엇입니까?

A: 대체 가능한 심볼은 PDF 문서의 머리글과 바닥글에 삽입할 수 있는 플레이스홀더입니다. 이러한 심볼은 페이지 번호, 날짜 및 사용자 정의 정보와 같이 런타임에 채울 수 있는 값에 대한 동적 플레이스홀더 역할을 합니다.

#### 질문: PDF 머리글과 바닥글에 대체 가능한 기호를 사용해야 하는 이유는 무엇입니까?

답변: 머리글과 바닥글의 바꿀 수 있는 기호는 페이지 번호, 날짜 또는 문서가 생성될 때 변경될 수 있는 다른 가변 데이터와 같은 동적 정보를 PDF 문서에 포함하려는 경우 유용합니다.

#### 질문: PDF 페이지의 여백을 어떻게 설정할 수 있나요?

 A: PDF 페이지의 여백은 다음을 사용하여 설정할 수 있습니다.`MarginInfo` 클래스와 그것을 할당`Margin` 의 속성`PageInfo` 페이지의. 필요에 따라 여백 값을 조정합니다.

#### 질문: 머리글과 바닥글에 바꿀 수 있는 기호를 추가하려면 어떻게 해야 하나요?

 A: 다음을 생성하여 교체 가능한 심볼을 추가할 수 있습니다.`HeaderFooter` 페이지의 헤더와 푸터에 대한 개체입니다. 그런 다음 추가할 수 있습니다.`TextFragment`원하는 텍스트가 있는 개체, 교체 가능한 기호 포함`Paragraphs` 의 컬렉션`HeaderFooter` 물체.

#### 질문: 교체 가능한 심볼의 모양을 사용자 지정할 수 있나요?

 A: 예, 속성을 수정하여 교체 가능한 기호의 모양을 사용자 정의할 수 있습니다.`TextFragment` 심볼을 포함하는 객체. 글꼴, 글꼴 크기, 색상, 정렬 및 줄 간격과 같은 속성을 설정할 수 있습니다.

#### 질문: 어떤 종류의 대체 기호를 사용할 수 있나요?

A: 다음과 같은 다양한 대체 가능한 기호를 사용할 수 있습니다.

- `$p`: 현재 페이지 번호.
- `$P`: 총 페이지 수.
- `$d`: 현재 날짜.
- `$t`: 현재 시간.
- 사용자가 정의하는 사용자 정의 플레이스홀더.

#### 질문: 대체 가능한 기호 주위에 다른 텍스트와 서식을 포함할 수 있나요?

 A: 예, 교체 가능한 기호 주위에 다른 텍스트와 서식을 포함할 수 있습니다.`TextFragment` 객체. 이를 통해 동적 및 정적 콘텐츠를 통합하는 더 복잡한 헤더와 푸터를 만들 수 있습니다.

#### 질문: 생성된 PDF 문서를 어떻게 저장할 수 있나요?

 A: 생성된 PDF 문서를 저장하려면 다음을 사용할 수 있습니다.`Save` 의 방법`Document`클래스. 원하는 출력 파일 경로와 이름을 인수로 제공합니다.

#### 질문: 이 튜토리얼을 사용하려면 유효한 Aspose 라이선스가 필요합니까?

A: 네, 이 튜토리얼에서 코드를 성공적으로 실행하려면 유효한 Aspose 라이선스가 필요합니다. Aspose 웹사이트에서 전체 라이선스 또는 30일 임시 라이선스를 얻을 수 있습니다.