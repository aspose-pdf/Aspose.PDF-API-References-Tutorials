---
title: PDF 파일에 숫자 스타일 적용
linktitle: PDF 파일에 숫자 스타일 적용
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 제목에 번호 매기기 스타일을 적용하는 방법을 알아보세요. 단계별 가이드.
type: docs
weight: 10
url: /ko/net/programming-with-headings/apply-number-style/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에 번호 매기기 스타일을 적용하기 위해 다음 C# 소스 코드를 단계별로 안내합니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

### 1단계: 문서 디렉터리 설정

제공된 소스 코드에서 생성된 PDF 파일을 저장할 디렉터리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉터리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2단계: PDF 문서 만들기

지정된 크기와 여백을 사용하여 새 PDF 문서를 만듭니다.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

### 3단계: 페이지 및 부동 컨테이너 만들기

문서에 페이지를 추가하고 콘텐츠를 정리하기 위해 플로팅 컨테이너를 만듭니다.

```csharp
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
```

### 4단계: 번호를 매겨 제목 추가

지정된 번호로 헤더를 생성하고 이를 플로팅 컨테이너에 추가합니다.

```csharp
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading. IsInList = true;
heading. StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading. IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);

Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "Listing 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);

Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "The value, at the effective date of the plan, of the assets to be distributed under the plan

";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
```

### 5단계: PDF 문서 저장

생성된 PDF 문서를 지정된 디렉토리에 저장합니다.

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style successfully applied to headers.\nFile saved as: " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 숫자 스타일 적용에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.Page pdfPage = pdfDoc.Pages.Add();
pdfPage.PageInfo.Width = 612.0;
pdfPage.PageInfo.Height = 792.0;
pdfPage.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfPage.PageInfo.Margin.Left = 72;
pdfPage.PageInfo.Margin.Right = 72;
pdfPage.PageInfo.Margin.Top = 72;
pdfPage.PageInfo.Margin.Bottom = 72;
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox();
floatBox.Margin = pdfPage.PageInfo.Margin;
pdfPage.Paragraphs.Add(floatBox);
TextFragment textFragment = new TextFragment();
TextSegment segment = new TextSegment();
Aspose.Pdf.Heading heading = new Aspose.Pdf.Heading(1);
heading.IsInList = true;
heading.StartNumber = 1;
heading.Text = "List 1";
heading.Style = NumberingStyle.NumeralsRomanLowercase;
heading.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading);
Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
heading2.IsInList = true;
heading2.StartNumber = 13;
heading2.Text = "List 2";
heading2.Style = NumberingStyle.NumeralsRomanLowercase;
heading2.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading2);
Aspose.Pdf.Heading heading3 = new Aspose.Pdf.Heading(2);
heading3.IsInList = true;
heading3.StartNumber = 1;
heading3.Text = "the value, as of the effective date of the plan, of property to be distributed under the plan onaccount of each allowed";
heading3.Style = NumberingStyle.LettersLowercase;
heading3.IsAutoSequence = true;
floatBox.Paragraphs.Add(heading3);
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumber style applied successfully in headings.\nFile saved at " + dataDir);  
          
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 제목에 번호 매기기 스타일을 적용하는 방법을 설명했습니다. 이제 이 지식을 사용하여 제목에 사용자 정의 번호를 매긴 PDF 문서를 만들 수 있습니다.

### PDF 파일의 번호 스타일 적용에 대한 FAQ

#### Q: PDF 문서의 번호 매기기 스타일은 무엇입니까?

답변: 번호 매기기 스타일은 PDF 문서에서 제목이나 섹션에 번호를 매기는 형식을 나타냅니다. 계층 구조를 제공하기 위해 숫자, 문자 또는 기타 문자를 포함할 수 있습니다.

#### Q: PDF 문서의 제목에 번호 매기기 스타일을 적용해야 하는 이유는 무엇입니까?

A: 제목에 번호 매기기 스타일을 적용하면 PDF 문서의 가독성과 구성이 향상됩니다. 이는 독자가 콘텐츠의 계층 구조를 쉽게 탐색하고 이해하는 데 도움이 됩니다.

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: Aspose.PDF for .NET은 개발자가 .NET 애플리케이션에서 프로그래밍 방식으로 PDF 파일을 작업할 수 있도록 하는 라이브러리입니다. PDF 문서 생성, 편집, 변환 및 조작을 위한 광범위한 기능을 제공합니다.

#### Q: C# 프로젝트에 필요한 라이브러리를 어떻게 가져오나요?

A: C# 프로젝트에 필요한 라이브러리를 가져오려면 다음 가져오기 지시문을 포함하세요.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

이러한 지시어를 사용하면 PDF 문서 작업 및 번호 매기기 스타일 적용에 필요한 클래스 및 메서드에 액세스할 수 있습니다.

#### Q: 생성된 PDF 파일을 저장할 디렉터리를 어떻게 지정합니까?

A: 제공된 소스 코드에서 "dataDir" 변수를 수정하여 생성된 PDF 파일을 저장할 디렉터리를 지정하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 실제 디렉토리 경로와 함께.

#### 질문: 지정된 크기와 여백을 가진 PDF 문서를 어떻게 만듭니까?

A: 지정된 크기와 여백을 가진 PDF 문서를 만들려면 다음 코드를 사용하십시오.

```csharp
Document pdfDoc = new Document();
pdfDoc.PageInfo.Width = 612.0;
pdfDoc.PageInfo.Height = 792.0;
pdfDoc.PageInfo.Margin = new Aspose.Pdf.MarginInfo();
pdfDoc.PageInfo.Margin.Left = 72;
pdfDoc.PageInfo.Margin.Right = 72;
pdfDoc.PageInfo.Margin.Top = 72;
pdfDoc.PageInfo.Margin.Bottom = 72;
```

#### Q: 번호 매기기 스타일이 있는 제목을 PDF 문서에 어떻게 추가합니까?

A: 번호 매기기 스타일이 있는 제목을 PDF 문서에 추가하려면 제공된 코드 샘플을 사용하여 제목을 만들고 번호 매기기 스타일을 사용자 정의하십시오. 필요에 따라 텍스트, 번호 매기기 스타일, 시작 번호, 자동 순서 등의 속성을 조정합니다.

#### Q: 생성된 PDF 문서를 어떻게 저장합니까?

 A: 생성된 PDF 문서를 저장하려면`Save` 의 방법`pdfDoc` 물체:

```csharp
dataDir = dataDir + "ApplyNumberStyle_out.pdf";
pdfDoc.Save(dataDir);
Console.WriteLine("\nNumbering style applied to headers.\nFile saved as: " + dataDir);
```

#### Q: 번호 매기기 스타일이 적용되었는지 어떻게 확인할 수 있나요?

A: 생성된 PDF 파일을 열어 지정된 번호 매기기 스타일이 제목에 적용되었는지 확인하세요.

#### Q: 번호 매기기 스타일을 추가로 사용자 정의할 수 있나요?

 A: 예, 속성을 조정하여 번호 매기기 스타일을 추가로 사용자 정의할 수 있습니다.`Heading` 번호 매기기 스타일 유형, 시작 번호, 자동 시퀀스 등의 개체입니다.

#### Q: 문서의 섹션별로 서로 다른 번호 매기기 스타일을 적용할 수 있나요?

A: 예, 여러 개의 번호를 생성하여 문서의 다양한 섹션에 다양한 번호 매기기 스타일을 적용할 수 있습니다.`Heading` 다양한 스타일과 순서를 가진 객체.