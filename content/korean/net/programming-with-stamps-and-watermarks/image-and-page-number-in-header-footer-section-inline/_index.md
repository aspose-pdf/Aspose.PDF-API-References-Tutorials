---
title: 헤더 푸터 섹션 인라인의 이미지 및 페이지 번호
linktitle: 헤더 푸터 섹션 인라인의 이미지 및 페이지 번호
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF의 머리글 섹션에 이미지와 페이지 번호를 직접 추가하는 방법을 알아보세요.
type: docs
weight: 120
url: /ko/net/programming-with-stamps-and-watermarks/image-and-page-number-in-header-footer-section-inline/
---
## 소개

Aspose.PDF for .NET은 PDF 파일을 조작하고 생성하는 광범위한 기능을 제공하는 강력한 도구입니다. 이미지를 추가하거나, 머리글과 바닥글을 사용자 지정하거나, 텍스트를 관리해야 할 때 Aspose.PDF가 해결해 드립니다. 이 튜토리얼에서는 PDF 문서의 머리글이나 바닥글에 이미지와 페이지 번호를 인라인으로 추가하는 방법을 살펴보겠습니다. 바로 들어가서 단계별로 프로세스를 분석해 보겠습니다.

## 필수 조건

코드로 들어가기 전에 먼저 따라할 수 있는 모든 것이 준비되었는지 확인해 보겠습니다.

-  .NET용 Aspose.PDF: 다음에서 최신 버전을 다운로드하세요.[Aspose PDF 다운로드 페이지](https://releases.aspose.com/pdf/net/).
- 개발 환경: Visual Studio와 같은 C# IDE가 필요합니다.
-  라이센스: 아직 라이센스가 없다면 다음을 얻을 수 있습니다.[여기 임시 면허증](https://purchase.aspose.com/temporary-license/) 또는 전체 제품을 구매하세요[아스포즈 매장](https://purchase.aspose.com/buy).

이제 필수 조건을 갖추었으니 시작해 보겠습니다.

## 패키지 가져오기

코딩을 시작하기 전에 필요한 네임스페이스를 가져와야 합니다.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이 패키지를 사용하면 PDF 파일과 텍스트 조작이 가능합니다.

## 1단계: 문서 디렉토리 설정

가장 먼저 해야 할 일은 PDF 파일이 저장될 디렉토리 경로를 정의하는 것입니다. 이 경로는 프로젝트 폴더나 머신의 어느 위치에나 사용자 정의할 수 있습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 이 변수는 문서가 저장될 위치를 보유합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 실제 경로와 함께.

## 2단계: PDF 문서 인스턴스화

 이 단계에서는 새 인스턴스를 만듭니다.`Aspose.Pdf.Document` 객체. 이 객체는 PDF 파일의 백본 역할을 합니다.

```csharp
// 빈 생성자를 호출하여 Document 객체를 인스턴스화합니다.
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

여기서는 나중에 콘텐츠를 채울 수 있는 빈 PDF 파일을 만들고 있습니다.

## 3단계: PDF에 페이지 추가

PDF에는 머리글, 바닥글, 콘텐츠를 추가할 수 있는 페이지가 최소 한 개 필요합니다. 문서에 빈 페이지를 추가해 보겠습니다.

```csharp
// Pdf 객체에 페이지 생성
Aspose.Pdf.Page page = pdf1.Pages.Add();
```

 전화로`pdf1.Pages.Add()`머리글과 바닥글을 사용자 정의할 수 있는 새 페이지가 문서에 추가되었습니다.

## 4단계: 헤더 만들기 및 설정

이제 문서의 헤더를 만들 시간입니다. 여기서 텍스트, 이미지, 페이지 번호를 추가합니다.

```csharp
// 문서의 머리글 섹션 만들기
Aspose.Pdf.HeaderFooter header = new Aspose.Pdf.HeaderFooter();
// PDF 파일의 헤더를 설정합니다
page.Header = header;
```

 우리는 만듭니다`HeaderFooter` 객체를 생성하고 이를 할당합니다.`Header` 페이지의 속성을 변경하여 헤더에 추가하는 모든 내용이 페이지 맨 위에 나타나도록 합니다.

## 5단계: 헤더에 인라인 텍스트 추가

 텍스트를 추가하는 것은 다음을 만드는 것만큼 간단합니다.`TextFragment` 그리고 속성을 지정합니다. 헤더에 색깔 있는 텍스트를 추가해 보겠습니다.

```csharp
// 텍스트 객체 생성
Aspose.Pdf.Text.TextFragment txt1 = new Aspose.Pdf.Text.TextFragment("Aspose.Pdf is a Robust component by");
// 색상을 지정하세요
txt1.TextState.ForegroundColor = Color.Blue;
txt1.IsInLineParagraph = true;
```

 이 단계에서는 다음을 생성합니다.`TextFragment` "Aspose.Pdf는 강력한 구성 요소입니다"라는 내용으로 색상을 파란색으로 설정합니다.`IsInLineParagraph` 속성은 텍스트가 인라인인지 확인합니다. 즉, 다른 요소(예: 이미지와 추가 텍스트)와 같은 줄에 표시됩니다.

## 6단계: 헤더에 인라인 이미지 삽입

헤더를 시각적으로 매력적으로 만들려면 텍스트와 함께 이미지를 추가할 수 있습니다. 이는 회사 로고나 다른 그래픽일 수 있습니다.

```csharp
// 섹션에 이미지 객체를 생성합니다
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
// 이미지 파일의 경로를 설정하세요
image1.File = dataDir + "aspose-logo.jpg";
// 이미지 너비 정보 설정
image1.FixWidth = 50;
image1.FixHeight = 20;
// seg1의 InlineParagraph가 이미지임을 나타냅니다.
image1.IsInLineParagraph = true;
```

 여기서 헤더에 이미지를 추가합니다.`Image` 객체, 경로 설정, 너비 및 높이 조정.`IsInLineParagraph` 이미지가 텍스트에 맞춰 정렬되도록 합니다.

## 7단계: 헤더를 완성하기 위해 추가 인라인 텍스트 추가

인라인 헤더를 완성하기 위해 텍스트를 더 추가해 보겠습니다.

```csharp
Aspose.Pdf.Text.TextFragment txt2 = new Aspose.Pdf.Text.TextFragment(" Pty Ltd.");
txt2.IsInLineParagraph = true;
txt2.TextState.ForegroundColor = Color.Maroon;
header.Paragraphs.Add(txt1);
header.Paragraphs.Add(image1);
header.Paragraphs.Add(txt2);
```

 이 부분에서는 또 다른 것을 만듭니다.`TextFragment` "Pty Ltd."라는 내용으로 색상을 적갈색으로 설정합니다. 텍스트 조각과 이미지가 모두 헤더에 추가됩니다.

## 8단계: PDF 저장

헤더를 설정한 후에는 PDF를 저장할 차례입니다.

```csharp
// PDF 저장
pdf1.Save(dataDir + "ImageAndPageNumberInHeaderFooter_UsingInlineParagraph_out.pdf");
```

 그만큼`Save` 이 방법은 최종 PDF 파일을 지정된 위치에 씁니다.

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서의 머리글에 이미지와 텍스트를 성공적으로 추가했습니다. 이 튜토리얼은 문서 만들기, 페이지 추가, 머리글 삽입, 텍스트 및 이미지와 같은 인라인 콘텐츠 배치를 포함한 필수 단계를 안내했습니다. Aspose.PDF는 머리글, 바닥글 또는 복잡한 콘텐츠를 조작하든 PDF를 관리하는 데 놀라운 유연성을 제공합니다. 

## 자주 묻는 질문

### 머리글에도 페이지 번호를 추가할 수 있나요?
 네! 다음을 사용하여 페이지 번호를 쉽게 추가할 수 있습니다.`TextFragment` 클래스와 필요에 따라 포맷팅합니다. 헤더 섹션에 인라인 콘텐츠로 삽입하기만 하면 됩니다.

### 헤더에 배경 이미지를 설정하려면 어떻게 해야 하나요?
 당신은 사용할 수 있습니다`BackgroundImage` 의 속성`HeaderFooter` 배경 이미지를 설정하는 클래스입니다. 그러나 이것은 인라인 콘텐츠가 아니며 전체 헤더 영역을 덮습니다.

### JPEG 외에 다른 이미지 포맷을 사용할 수 있나요?
물론입니다! Aspose.PDF는 PNG, BMP, GIF 등 다양한 이미지 형식을 지원합니다.

### 헤더의 텍스트 글꼴을 사용자 지정할 수 있나요?
 네, 사용할 수 있습니다`TextState`텍스트의 글꼴, 크기, 스타일을 변경합니다.

### Aspose.PDF for .NET을 사용하려면 라이선스가 필요합니까?
 예, Aspose.PDF는 프로덕션 사용을 위해 라이선스가 필요하지만 다음과 같이 시작할 수 있습니다.[무료 체험은 여기를 클릭하세요](https://releases.aspose.com/).