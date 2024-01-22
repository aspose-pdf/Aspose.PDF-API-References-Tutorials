---
title: 다중 열 PDF 생성
linktitle: 다중 열 PDF 생성
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 다중 열 PDF를 만드는 방법을 알아보세요.
type: docs
weight: 110
url: /ko/net/programming-with-text/create-multi-column-pdf/
---
이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 다중 열 PDF를 만드는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio 또는 기타 C# 컴파일러가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필수 네임스페이스 가져오기
다중 열 PDF를 생성하려는 코드 파일에서 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## 3단계: 문서 디렉터리 설정
 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리의 경로를 사용하세요.

## 4단계: 새 문서 인스턴스 만들기
 새 인스턴스화`Document` 다음 코드 줄을 추가하여 객체를 생성합니다.

```csharp
Document doc = new Document();
```

## 5단계: 페이지 여백 설정
 다음을 사용하여 PDF 파일의 왼쪽 및 오른쪽 여백 정보를 지정합니다.`PageInfo.Margin` 의 재산`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## 6단계: 문서에 페이지 추가
 다음을 사용하여 문서에 새 페이지를 추가합니다.`Add` 의 방법`Pages`수집. 제공된 코드에서 새 페이지는 변수에 할당됩니다.`page`.

```csharp
Page page = doc.Pages.Add();
```

## 7단계: 그래프 개체 만들기 및 선 추가
 새로 만들기`Graph` 특정 치수의 개체를 선택하고 여기에 선을 추가합니다. 그런 다음`Graph` 에 반대하다`Paragraphs` 페이지의 컬렉션입니다.

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## 8단계: HTML 형식으로 제목 텍스트 추가
 만들기`HtmlFragment` 개체를 선택하고 그 내용을 원하는 HTML 텍스트로 설정합니다. 그런 다음 조각을`Paragraphs` 페이지의 컬렉션입니다.

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## 9단계: 여러 열이 있는 FloatingBox 만들기
 만들기`FloatingBox` 개체를 선택하고 열 수와 열 간격을 설정합니다. 그런 다음 텍스트 조각과 한 줄을`Paragraphs` 의 컬렉션`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## 10단계: PDF 문서 저장
 다음을 사용하여 PDF 문서를 저장합니다.`Save` 의 방법`Document` 물체.

```csharp
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 다중 열 PDF 만들기의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
// PDF 파일의 왼쪽 여백 정보 지정
doc.PageInfo.Margin.Left = 40;
//PDF 파일의 오른쪽 여백 정보를 지정합니다.
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
// 섹션 개체의 단락 모음에 줄을 추가합니다.
page.Paragraphs.Add(graph1);
// 선의 좌표를 지정하세요
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
// html 태그가 포함된 텍스트로 문자열 변수 만들기
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
// HTML 텍스트가 포함된 텍스트 단락 만들기
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
// 섹션에 4개의 열을 추가하세요.
box.ColumnInfo.ColumnCount = 2;
// 열 사이의 간격 설정
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
// 그래프 개체를 만들어 선을 그립니다.
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
// 선의 좌표를 지정하세요
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
// 섹션 개체의 단락 컬렉션에 줄을 추가합니다.
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
// PDF 파일 저장
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## 결론
.NET용 Aspose.PDF를 사용하여 다중 열 PDF를 성공적으로 만들었습니다. 이제 결과 PDF 파일을 지정된 출력 파일 경로에서 찾을 수 있습니다.

### FAQ

#### Q: 이 튜토리얼의 초점은 무엇입니까?

이 튜토리얼은 .NET 라이브러리용 Aspose.PDF를 사용하여 다중 열 PDF를 만드는 과정을 안내하는 데 중점을 두고 있습니다. 제공된 C# 소스 코드는 이를 달성하는 데 필요한 단계를 보여줍니다.

#### Q: 이 튜토리얼에서는 어떤 네임스페이스를 가져와야 합니까?

A: 다중 열 PDF를 생성하려는 코드 파일에서 파일 시작 부분에 다음 네임스페이스를 가져옵니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### Q: 문서 디렉터리를 어떻게 지정합니까?

 A: 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

#### Q: 새 문서 인스턴스를 어떻게 생성합니까?

 A: 4단계에서는 새 인스턴스를 생성합니다.`Document` 제공된 코드를 사용하여 객체를 생성합니다.

#### Q: 페이지 여백은 어떻게 설정하나요?

 A: 5단계에서는`PageInfo.Margin` 의 재산`Document` PDF 파일의 왼쪽 및 오른쪽 여백 정보를 지정합니다.

#### Q: 문서에 페이지를 어떻게 추가하나요?

 A: 6단계에서는 다음을 사용하여 문서에 새 페이지를 추가합니다.`Add` 의 방법`Pages` 수집.

#### Q: 그래프 개체를 생성하고 선을 추가하려면 어떻게 해야 합니까?

 A: 7단계에서는 새`Graph` 개체에 줄을 추가한 다음`Graph` 에 반대하다`Paragraphs` 페이지의 컬렉션입니다.

#### Q: HTML 형식으로 제목 텍스트를 어떻게 추가합니까?

 A: 8단계에서는`HtmlFragment` 개체를 선택하고 그 내용을 원하는 HTML 텍스트로 설정한 다음 조각을`Paragraphs` 페이지의 컬렉션입니다.

#### Q: 여러 열이 있는 FloatingBox를 어떻게 생성합니까?

 A: 9단계에서는`FloatingBox` 여러 열과 열 간격이 있는 개체를 만든 다음 텍스트 조각과 한 줄을 개체에 추가합니다.`Paragraphs` 의 컬렉션`FloatingBox`.

#### Q: PDF 문서를 어떻게 저장하나요?

 A: 10단계에서는 다음을 사용하여 PDF 문서를 저장합니다.`Save` 의 방법`Document` 물체.

#### Q: 이 튜토리얼의 주요 내용은 무엇입니까?

A: 이 튜토리얼을 따라 .NET용 Aspose.PDF를 사용하여 다중 열 PDF 문서를 만드는 방법을 배웠습니다. 이는 체계적이고 정리된 레이아웃으로 콘텐츠를 표시하는 데 유용할 수 있습니다.