---
title: 헤더 푸터의 교체 가능한 심볼
linktitle: 헤더 푸터의 교체 가능한 심볼
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서의 머리글과 바닥글에 바꿀 수 있는 기호를 사용하는 방법을 알아보세요.
type: docs
weight: 320
url: /ko/net/programming-with-text/replaceable-symbols-in-header-footer/
---
## 소개

PDF 파일을 작업할 때 페이지 번호, 보고서 이름 또는 생성된 날짜와 같은 동적 콘텐츠로 머리글과 바닥글을 사용자 지정해야 할 때가 있습니다. 다행히도 Aspose.PDF for .NET은 이 프로세스를 간소화하여 머리글과 바닥글에 페이지 번호 또는 보고서 생성 세부 정보와 같은 자동으로 업데이트된 기호가 있는 PDF를 만들 수 있습니다. 이 문서에서는 Aspose.PDF for .NET을 사용하여 머리글과 바닥글의 기호를 바꾸는 단계별 프로세스를 안내합니다. 간단할 뿐만 아니라 놀라울 정도로 효율적인 방법입니다.

## 필수 조건

단계별 가이드를 살펴보기 전에 다음 사항이 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.PDF –[다운로드](https://releases.aspose.com/pdf/net/) 또는 얻을[무료 체험](https://releases.aspose.com/).
- 시스템에 Visual Studio 또는 C# IDE가 설치되어 있어야 합니다.
- C# 및 .NET 개발에 대한 기본 지식.
-  유효한[특허](https://purchase.aspose.com/temporary-license/) Aspose.PDF의 경우 체험판을 사용하실 수 있습니다.

## 패키지 가져오기

시작하려면 Aspose.PDF for .NET의 기능을 활성화하는 데 필요한 네임스페이스를 가져와야 합니다. 필요한 가져오기는 다음과 같습니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

이러한 기능은 PDF 생성, 텍스트 조작, 머리글/바닥글 관리에 필수적입니다.

예제 코드를 이해하기 쉬운 단계로 나누어 보겠습니다.

## 1단계: 문서 및 페이지 설정

먼저, 문서를 초기화하고 페이지를 추가해야 합니다. 이렇게 하면 헤더와 푸터를 추가하기 위한 기초가 마련됩니다.

```csharp
// 문서 디렉토리 설정
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 객체를 초기화합니다
Document doc = new Document();

// 문서에 페이지 추가
Page page = doc.Pages.Add();
```

 여기서는 다음을 사용하여 PDF 문서를 설정합니다.`Document` 클래스와 페이지 추가`doc.Pages.Add()`이 페이지에는 머리글, 바닥글 및 기타 콘텐츠가 포함됩니다.

## 2단계: 페이지 여백 구성

다음으로, 콘텐츠가 가장자리까지 늘어나지 않도록 페이지의 여백을 정의하겠습니다.

```csharp
// 여백 구성
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

 여기서 우리는 다음을 사용하여 위쪽, 아래쪽, 왼쪽 및 오른쪽 여백을 정의했습니다.`MarginInfo` 클래스를 사용하여 페이지에 적용했습니다.`page.PageInfo.Margin`.

## 3단계: 헤더 생성 및 구성

이제 헤더를 만들어 페이지에 추가해 보겠습니다. 헤더에는 보고서 제목과 이름이 포함됩니다.

```csharp
// 헤더 생성
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;

// 헤더 여백 설정
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

// 헤더에 제목 추가
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t1);

// 헤더에 보고서 이름 추가
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.FontSize = 12;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
hfFirst.Paragraphs.Add(t2);
```

 우리는 두 개를 추가했습니다`TextFragment` 헤더에 대한 개체: 하나는 보고서 제목용이고 다른 하나는 보고서 이름용입니다. 텍스트는 다음을 사용하여 스타일이 지정됩니다.`TextState` 글꼴, 크기, 정렬과 같은 속성.

## 4단계: 바닥글 만들기 및 구성

이제 페이지 번호와 생성 날짜와 같은 동적 콘텐츠를 보관할 바닥글을 설정할 시간입니다.

```csharp
// 푸터 만들기
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;

// 바닥글 여백 설정
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

// 푸터 콘텐츠 추가
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("Report Name");
TextFragment t5 = new TextFragment("Page $p of $P");
```

바닥글에는 생성 날짜, 보고서 이름 및 동적 페이지 번호에 대한 조각을 포함합니다.`$p` 그리고`$P` 각각 현재 페이지 번호와 전체 페이지 수를 나타냅니다).

## 5단계: 바닥글에 표 만들기

또한, 푸터에 표와 같은 더 복잡한 요소를 추가하여 데이터를 더 효과적으로 구성할 수 있습니다.

```csharp
// 푸터용 테이블 생성
Table tab2 = new Table();
hfFoot.Paragraphs.Add(tab2);
tab2.ColumnWidths = "165 172 165";

// 표의 행과 셀을 만듭니다
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();

// 각 셀에 대한 정렬 설정
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;

// 표 셀에 내용 추가
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
```

이 코드 블록은 바닥글에 3열로 된 표를 만듭니다. 각 열은 생성 날짜, 보고서 이름, 페이지 번호와 같은 다른 정보를 포함합니다.

## 6단계: 페이지에 콘텐츠 추가

머리글과 바닥글 외에도 PDF 페이지의 본문에 콘텐츠를 추가할 수 있습니다. 여기서는 플레이스홀더 텍스트가 있는 표를 추가합니다.

```csharp
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
page.Paragraphs.Add(table);

// 테이블 내용 추가
for (int i = 0; i <= 10; i++)
{
    Row row = table.Rows.Add();
    for (int c = 0; c <= 2; c++)
    {
        Cell cell = row.Cells.Add("Content " + c);
        cell.Margin = new MarginInfo { Left = 30, Top = 10, Bottom = 10 };
    }
}
```

이 코드는 페이지에 세 개의 열이 있는 간단한 표를 추가합니다. 귀하의 특정 요구 사항에 맞게 수정할 수 있습니다.

## 7단계: PDF 저장

모든 것이 설정되면 마지막 단계는 원하는 위치에 PDF 문서를 저장하는 것입니다.

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("Symbols replaced successfully in header and footer. File saved at " + dataDir);
```

 파일 경로를 지정하고 다음을 사용하여 문서를 저장합니다.`doc.Save()`. 그게 다입니다! 사용자 지정 헤더와 푸터가 있는 PDF를 성공적으로 만들었습니다.

## 결론

Aspose.PDF for .NET을 사용하여 헤더와 푸터의 심볼을 바꾸는 것은 간단할 뿐만 아니라 강력합니다. 위의 단계별 가이드를 따르면 페이지 번호, 보고서 이름, 날짜와 같은 동적 콘텐츠로 PDF를 쉽게 사용자 지정할 수 있습니다. 이 방법은 매우 유연하여 표를 삽입하고, 서식을 조정하고, 특정 요구 사항에 맞게 레이아웃을 제어할 수 있습니다.

## 자주 묻는 질문

### 머리글과 바닥글의 글꼴을 사용자 정의할 수 있나요?  
네, 머리글과 바닥글의 텍스트에 대한 글꼴, 크기, 색상 및 스타일을 완전히 사용자 지정할 수 있습니다.

### 헤더와 푸터에 이미지를 추가하려면 어떻게 해야 하나요?  
 사용할 수 있습니다`ImageStamp` 헤더와 푸터에 이미지를 삽입합니다.

### 헤더나 푸터에 하이퍼링크를 추가할 수 있나요?  
 네, 사용할 수 있습니다`TextFragment` 하이퍼링크를 설정하여`Hyperlink` 재산.

### 홀수 페이지와 짝수 페이지에 다른 머리글을 사용할 수 있나요?  
네, Aspose.PDF를 사용하면 홀수 및 짝수 페이지에 대해 다른 머리글과 바닥글을 지정할 수 있습니다.

### 헤더와 푸터 위치를 어떻게 조정합니까?  
여백과 정렬 속성을 조정하여 머리글과 바닥글의 위치를 제어할 수 있습니다.