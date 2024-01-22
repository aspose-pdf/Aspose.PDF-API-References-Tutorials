---
title: 머리글 바닥글 섹션의 이미지 및 페이지 번호
linktitle: 머리글 바닥글 섹션의 이미지 및 페이지 번호
second_title: .NET API 참조용 Aspose.PDF
description: Aspose를 사용하여 PDF 문서의 머리글과 바닥글에 이미지와 페이지 번호를 추가하는 방법을 알아보세요.
type: docs
weight: 110
url: /ko/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 머리글과 바닥글 섹션에 이미지와 페이지 번호를 추가하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 사용하여 페이지를 만들고, 머리글과 바닥글을 설정하고, 머리글에 이미지를 추가하고, 문서 바닥글 PDF에 페이지 번호가 있는 텍스트를 추가하는 방법을 보여 드리겠습니다.

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// 문서에 페이지 만들기
Aspose.Pdf.Page page = doc.Pages.Add();
```

위의 코드는 PDF 문서에 새 Document 개체와 빈 페이지를 만듭니다.

## 3단계: 이미지와 함께 헤더 추가

이제 페이지가 생성되었으므로 이미지가 포함된 헤더 섹션을 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 헤더 섹션 만들기
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// 페이지 헤더 설정
page. Header = header;

// 이미지 객체 생성
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// 이미지 경로 설정
image1.File = dataDir + "aspose-logo.jpg";

// PDF 문서의 페이지 헤더에 이미지 추가
header.Paragraphs.Add(image1);
```

위의 코드는 헤더 섹션을 생성하고, 이 섹션으로 페이지 헤더를 설정하고, 헤더에 이미지를 추가합니다.

## 4단계: 페이지 번호가 포함된 바닥글 추가

이제 머리글이 추가되었으므로 페이지 번호가 있는 바닥글 섹션을 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 바닥글 섹션 만들기
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// PDF 문서의 바닥글 정의
page. Footer = footer;

// TextFragment 객체 생성
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P)");

// PDF 문서의 바닥글에 페이지 번호와 함께 텍스트를 추가합니다.
footer.Paragraphs.Add(txt);
```

위의 코드는 바닥글 섹션을 만들고, 이 섹션으로 페이지의 바닥글을 설정하고, "페이지: ($p of $P )" 텍스트가 포함된 TextFragment를 추가합니다.

  페이지 번호를 표시합니다.

## 5단계: 수정된 PDF 문서 저장

머리글과 바닥글이 추가되면 수정된 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 수정된 PDF 문서 저장
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");
```

위 코드는 편집된 PDF 문서를 지정된 디렉토리에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 머리글 바닥글 섹션의 이미지 및 페이지 번호에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

// 문서 개체에 페이지 만들기
Aspose.Pdf.Page page = doc.Pages.Add();

// 문서의 헤더 섹션 만들기
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();

// PDF 파일의 헤더 설정
page.Header = header;

// 페이지에 이미지 개체 만들기
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

// 이미지 파일 경로 설정
image1.File = dataDir + "aspose-logo.jpg";

// PDF 파일의 헤더 페이지에 이미지 추가
header.Paragraphs.Add(image1);

//문서의 바닥글 섹션 만들기
Aspose.Pdf.HeaderFooter footer = new Aspose.Pdf.HeaderFooter();

// PDF 파일의 바닥글 설정
page.Footer = footer;

// 텍스트 개체 만들기
Aspose.Pdf.Text.TextFragment txt = new Aspose.Pdf.Text.TextFragment("Page: ($p of $P ) ");

// PDF 파일의 헤더 섹션에 텍스트 추가
footer.Paragraphs.Add(txt);

// PDF 파일 저장
doc.Save(dataDir + "ImageAndPageNumberInHeaderFooter_out.pdf");

```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 PDF 문서의 머리글과 바닥글 섹션에 이미지와 페이지 번호를 추가하는 방법을 배웠습니다. 이제 이 방법을 사용하여 PDF 문서의 머리글과 바닥글을 사용자 정의할 수 있습니다.

### FAQ

#### Q: PDF 문서의 머리글과 바닥글 섹션에 이미지와 페이지 번호를 추가하는 목적은 무엇입니까?

답변: PDF 문서의 머리글 및 바닥글 섹션에 이미지와 페이지 번호를 추가하면 시각적 매력, 브랜딩 및 탐색 요소를 향상시킬 수 있습니다. 이미지는 로고, 워터마크 또는 모든 그래픽 요소를 나타낼 수 있으며, 페이지 번호는 사용자가 진행 상황을 추적하고 특정 페이지를 찾는 데 도움이 됩니다.

#### Q: 제공된 C# 소스 코드는 PDF 문서의 머리글과 바닥글에 이미지와 페이지 번호를 추가하는 데 어떻게 도움이 됩니까?

답변: 제공된 코드는 PDF 문서를 만들고, 페이지를 추가한 다음 머리글 및 바닥글 섹션을 사용자 정의하는 방법을 보여줍니다. 머리글에 이미지를 추가하고 바닥글에 페이지 번호가 있는 텍스트 조각을 추가하는 방법을 보여줍니다.

#### Q: 헤더에 어떤 이미지 형식이든 사용할 수 있으며 해당 경로를 어떻게 지정합니까?

 A: 예, 헤더 이미지에 다양한 이미지 형식(예: JPEG, PNG, GIF 등)을 사용할 수 있습니다. 이미지 경로는 다음을 사용하여 지정됩니다.`File` 의 재산`Aspose.Pdf.Image` 물체.

#### Q: 헤더 섹션에 있는 이미지의 모양과 위치를 어떻게 사용자 정의합니까?

 A: 속성을 조정하여 이미지의 모양과 위치를 사용자 정의할 수 있습니다.`Aspose.Pdf.Image` 헤더 섹션에 추가하기 전에 개체를 삭제하세요. 예를 들어 이미지의 크기, 정렬, 회전, 불투명도 등을 설정할 수 있습니다.

####  Q: 이 프로그램의 목적은 무엇입니까?`TextFragment` object used for the footer?

 답:`TextFragment` 개체는 바닥글 섹션에 표시될 텍스트를 만들고 서식을 지정하는 데 사용됩니다. 제공된 코드에서는 페이지 번호와 전체 페이지 수를 표시하는 데 사용됩니다.

#### Q: 추가 정보나 서식을 포함하도록 바닥글 텍스트를 수정할 수 있습니까?

 A: 예, 내용을 수정하여 바닥글 텍스트를 수정할 수 있습니다.`TextFragment` 물체. 요구 사항에 따라 추가 텍스트를 추가하고 글꼴, 색상 및 서식을 변경할 수 있습니다.

#### 질문: PDF 문서의 다른 페이지에 다른 머리글과 바닥글 내용을 적용할 수 있습니까?

 A: 예, 별도의 생성을 통해 서로 다른 페이지에 서로 다른 머리글과 바닥글 내용을 적용할 수 있습니다.`HeaderFooter` 개체를 사용하여 특정 페이지에 개체를 할당합니다.`Header` 그리고`Footer` 의 속성`Aspose.Pdf.Page` 물체.

#### Q: 글꼴 스타일을 변경하거나 추가 요소를 추가하는 등 머리글과 바닥글을 추가로 사용자 정의하려면 어떻게 해야 합니까?

A: Aspose.PDF for .NET에서 제공하는 다양한 클래스와 속성을 사용하여 머리글과 바닥글을 사용자 정의할 수 있습니다. 예를 들어 다양한 텍스트 서식 옵션을 사용하고 머리글 및 바닥글 섹션에 더 많은 단락, 이미지 또는 표를 추가할 수 있습니다.

#### Q: 필요한 경우 머리글과 바닥글 섹션을 제거하거나 지울 수 있나요?

A: 예. 머리글과 바닥글 섹션을 제거하거나 지울 수 있습니다.`Header` 그리고`Footer` 의 속성`Aspose.Pdf.Page` 반대하다`null`.

#### Q: 추가된 이미지와 페이지 번호가 다양한 장치와 뷰어에서 일관되게 유지되도록 하려면 어떻게 해야 합니까?

A: Aspose.PDF for .NET은 표준화되고 일관된 PDF 문서를 생성하는 기능을 제공하여 추가된 이미지와 페이지 번호가 다양한 장치와 PDF 뷰어에서 일관되게 표시되도록 보장합니다.