---
title: 머리글 바닥글 섹션 인라인의 이미지 및 페이지 번호
linktitle: 머리글 바닥글 섹션 인라인의 이미지 및 페이지 번호
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF에서 인라인 단락을 사용하여 머리글과 바닥글에 이미지와 페이지 번호를 추가하는 방법을 알아보세요.
type: docs
weight: 120
url: /ko/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 머리글 및 바닥글 섹션에 이미지와 페이지 번호를 추가하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 사용하여 페이지를 만들고, 머리글과 바닥글을 설정하고, PDF 문서 머리글의 인라인 단락을 사용하여 이미지와 텍스트를 추가합니다.

## 1단계: 환경 설정

시작하기 전에 다음 사항이 있는지 확인하세요.

- 설치된 .NET 개발 환경.
- .NET용 Aspose.PDF 라이브러리가 다운로드되어 프로젝트에서 참조됩니다.

## 2단계: PDF 문서 및 페이지 만들기

첫 번째 단계는 PDF 문서에 새 문서 개체와 페이지를 만드는 것입니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 새 문서 개체 만들기
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// 문서에 페이지 만들기
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

위의 코드는 PDF 문서에 새 Document 개체와 빈 페이지를 만듭니다.

## 3단계: 이미지와 인라인 텍스트가 포함된 헤더 추가

이제 페이지가 생성되었으므로 인라인 단락을 사용하여 이미지와 텍스트가 포함된 헤더 섹션을 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 헤더 섹션 만들기
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// 페이지 헤더 설정
page. Header = header;

// 첫 번째 인라인 텍스트에 대한 TextFragment 객체를 만듭니다.
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a robust component developed by");

// 텍스트 색상 지정
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// 이미지에 대한 Image 객체 생성
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// 이미지 경로 설정
image1.File = dataDir + "aspose-logo.jpg";

// 이미지의 크기 정의
image1.FixWidth = 50;
image1.FixHeight = 20;

// 첫 번째 인라인 텍스트가 이미지임을 나타냅니다.
image1.IsInLineParagraph = true;

// 두 번째 인라인 텍스트 만들기
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;

// 헤더에 항목 추가
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

위의 코드는 헤더 섹션을 만들고, 이 섹션으로 페이지 헤더를 설정하고, 인라인 텍스트와 인라인 Image 개체가 있는 TextFragment를 추가합니다.

## 4단계: 수정된 PDF 문서 저장

이미지와 인라인 텍스트가 포함된 헤더가 추가되면 수정된 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 수정된 PDF 문서 저장
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

위 코드는 편집된 PDF 문서를 지정된 디렉토리에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 머리글 바닥글 섹션의 이미지 및 페이지 번호에 대한 샘플 소스 코드 인라인 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 빈 생성자를 호출하여 Document 객체를 인스턴스화합니다.
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();

// PDF 개체에 페이지 만들기
Aspose.Pdf.Page page = pdf1.Pages.Add();

// 문서의 헤더 섹션 만들기
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// PDF 파일의 헤더 설정
page.Header = header;

// 텍스트 개체 만들기
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");

// 색상을 지정하세요
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;

// 섹션에 이미지 개체 만들기
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// 이미지 파일 경로 설정
image1.File = dataDir + "aspose-logo.jpg";

// 이미지 너비 정보 설정
image1.FixWidth = 50;
image1.FixHeight = 20;

// seg1의 InlineParagraph가 이미지임을 나타냅니다.
image1.IsInLineParagraph = true;
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);

// PDF 저장
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");

```

## 결론

축하합니다! .NET용 Aspose.PDF에서 인라인 단락을 사용하여 PDF 문서의 머리글 및 바닥글 섹션에 이미지와 페이지 번호를 추가하는 방법을 배웠습니다. 이제 PDF 문서의 머리글과 바닥글을 유연하게 사용자 정의할 수 있습니다.

### FAQ

#### Q: PDF 문서의 헤더에 이미지와 텍스트를 추가하기 위해 인라인 단락을 사용하면 어떤 이점이 있습니까?

A: 인라인 단락을 사용하면 동일한 단락 내에서 이미지와 텍스트를 원활하게 통합하여 위치와 서식을 정밀하게 제어할 수 있습니다. 이 방법은 시각적 요소가 포함된 사용자 정의 헤더를 만드는 데 특히 유용합니다.

#### Q: 제공된 C# 소스 코드는 어떻게 PDF 문서의 헤더에 대한 인라인 단락을 구현합니까?

답변: 제공된 코드는 PDF 문서를 생성하고, 페이지를 추가하고, 인라인 단락을 사용하여 헤더를 사용자 정의하는 방법을 보여줍니다. 인라인 텍스트, 인라인 이미지 및 다른 인라인 TextFragment가 포함된 TextFragment를 추가합니다.

#### Q: 헤더의 인라인 텍스트 색상을 어떻게 지정합니까?

 A: 인라인 텍스트의 색상은 다음을 사용하여 지정됩니다.`ForegroundColor` 의 재산`TextState` ~의`TextFragment` 물체.

#### Q: 헤더에 있는 인라인 이미지의 크기를 조정할 수 있나요?

 A: 예, 다음을 사용하여 인라인 이미지의 크기를 조정할 수 있습니다.`FixWidth` 그리고`FixHeight` 의 속성`Image` 물체. 이를 통해 헤더 내 이미지의 너비와 높이를 제어할 수 있습니다.

#### Q: 헤더에 하이퍼링크나 다른 글꼴 스타일과 같은 추가 인라인 요소를 포함할 수 있습니까?

 A: 예. 더 많은 인라인 요소를 생성하여 헤더에 추가 인라인 요소를 포함할 수 있습니다.`TextFragment` 또는`Image` 원하는 속성을 가진 개체. 이를 통해 하이퍼링크, 다양한 글꼴 스타일 또는 기타 시각적 요소를 포함하여 헤더를 추가로 사용자 정의할 수 있습니다.

#### Q: 인라인 이미지와 텍스트가 다양한 장치와 뷰어에서 올바르게 정렬되고 형식이 유지되도록 하려면 어떻게 해야 합니까?

A: .NET용 Aspose.PDF는 인라인 이미지와 텍스트가 올바르게 정렬되고 서식이 지정되도록 보장하여 다양한 장치와 PDF 뷰어에서 일관된 모양을 제공합니다.

#### Q: 바닥글 섹션에도 인라인 단락을 적용할 수 있나요?

 A: 예, 인라인 단락을 사용하는 것과 동일한 기술을 바닥글 섹션에 적용할 수 있습니다.`Footer` 개체에 텍스트, 이미지 등의 인라인 요소를 추가합니다.

#### Q: 인라인 단락을 다른 머리글 또는 바닥글 사용자 정의 방법과 결합할 수 있습니까?

A: 예, 인라인 단락을 Aspose.PDF for .NET에서 제공하는 다른 머리글 또는 바닥글 사용자 정의 방법과 결합하여 보다 복잡하고 맞춤화된 머리글 또는 바닥글 디자인을 만들 수 있습니다.

#### Q: 필요한 경우 헤더에서 인라인 요소를 제거하거나 지울 수 있나요?

 A: 예. 내용을 수정하여 인라인 요소를 제거하거나 지울 수 있습니다.`HeaderFooter` 이의를 제기하고 해당 인라인 단락을 제거합니다.

#### 질문: PDF 문서의 특정 페이지에 인라인 단락을 적용하려면 어떻게 해야 합니까?

 A: 특정 페이지에 인라인 단락을 적용하려면 별도의 단락을 생성하면 됩니다.`HeaderFooter` 각 페이지에 대한 개체를 지정하고`Header` 해당 재산의`Aspose.Pdf.Page` 사물.