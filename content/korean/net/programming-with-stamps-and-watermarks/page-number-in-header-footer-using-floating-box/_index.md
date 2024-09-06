---
title: 플로팅 박스를 사용하여 헤더 푸터에 페이지 번호 추가
linktitle: 플로팅 박스를 사용하여 헤더 푸터에 페이지 번호 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서의 머리글과 바닥글에 페이지 번호를 추가하는 방법을 알아보세요.
type: docs
weight: 150
url: /ko/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
이 튜토리얼에서는 Aspose.PDF for .NET과 함께 FloatingBox를 사용하여 PDF 문서의 머리글과 바닥글에 페이지 번호를 추가하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 사용하여 PDF 문서를 만들고, 페이지를 추가하고, FloatingBox를 만들고, 위치를 설정하고, 페이지 번호를 추가한 다음 수정된 PDF 문서를 저장합니다.

## 1단계: 환경 설정

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 개발 환경이 설치되어 있습니다.
- 프로젝트에서 다운로드하여 참조할 수 있는 .NET용 Aspose.PDF 라이브러리입니다.

## 2단계: PDF 문서 만들기 및 페이지 추가

첫 번째 단계는 PDF 문서의 인스턴스를 만들고 여기에 페이지를 추가하는 것입니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF 문서 인스턴스화
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// PDF 문서에 페이지 추가
Aspose.Pdf.Page page = pdf.Pages.Add();
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서를 저장하려는 디렉토리의 실제 경로로 바꿔야 합니다.

## 3단계: FloatingBox 만들기 및 페이지 번호 추가

이제 페이지가 PDF 문서에 추가되었으므로 FloatingBox를 만들고 위치를 설정하고 페이지 번호를 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 너비가 140이고 높이가 80인 FloatingBox를 만듭니다.
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// 문단의 왼쪽 위치 설정
box1. Left = 2;

// 문단의 상단 위치 설정
box1. Top = 10;

// FloatingBox에 페이지 번호를 추가합니다.
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// 페이지에 FloatingBox를 추가합니다
page.Paragraphs.Add(box1);
```

위의 코드는 너비가 140이고 높이가 80인 FloatingBox를 만듭니다. 다음으로, left 및 top 값을 지정하여 위치를 설정합니다. 마지막으로, 현재 페이지 번호와 총 페이지 수로 대체될 구문 "($p/ $P )"를 포함하는 TextFragment를 사용하여 FloatingBox에 페이지 번호를 추가합니다.

## 4단계: 수정된 PDF 문서 저장

FloatingBox를 사용하여 머리글이나 바닥글에 페이지 번호를 추가하면 수정된 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 수정된 PDF 문서를 저장합니다.
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

위 코드는 편집된 PDF 문서를 지정된 디렉토리에 저장합니다.

### Aspose.PDF for .NET을 사용하여 플로팅 박스를 사용한 헤더 푸터의 페이지 번호에 대한 샘플 소스 코드 
```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 인스턴스화
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

// PDF 문서에 페이지 추가
Aspose.Pdf.Page page = pdf.Pages.Add();

// FloatingBox 클래스의 새 인스턴스를 초기화합니다.
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

// 문단의 왼쪽 위치를 나타내는 Float 값
box1.Left = 2;

// 문단의 최상위 위치를 나타내는 Float 값
box1.Top = 10;

// FloatingBox의 문단 컬렉션에 매크로를 추가합니다.
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

// 페이지에 floatingBox를 추가합니다
page.Paragraphs.Add(box1);

// 문서를 저장하세요
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## 결론

축하합니다! Aspose.PDF for .NET과 함께 FloatingBox를 사용하여 PDF 문서의 머리글과 바닥글에 페이지 번호를 추가하는 방법을 배웠습니다. 이제 페이지 번호와 같은 동적 정보를 추가하여 머리글과 바닥글을 사용자 지정할 수 있습니다.

### 자주 묻는 질문

#### 질문: FloatingBox란 무엇이고, PDF 문서의 머리글이나 바닥글에 페이지 번호를 추가하는 데 어떻게 사용되나요?

A: FloatingBox는 Aspose.PDF의 다재다능한 레이아웃 요소로, 텍스트와 이미지를 포함한 다양한 콘텐츠를 보관할 수 있습니다. 이 튜토리얼에서는 페이지 번호에 대한 컨테이너를 만드는 데 사용되어 현재 페이지 번호와 총 페이지 수를 헤더나 푸터에 동적으로 삽입할 수 있습니다.

#### 질문: 제공된 C# 소스 코드는 FloatingBox를 사용하여 페이지 번호를 추가하는 방법을 어떻게 구현합니까?

A: 코드 조각은 PDF 문서를 만들고, 페이지를 추가하고, FloatingBox를 만들고, 페이지 내에서 위치를 설정하고, TextFragment를 사용하여 페이지 번호를 삽입하는 방법을 보여줍니다. TextFragment의 구문 "($p/ $P )"는 현재 페이지 번호와 총 페이지 수로 대체됩니다.

#### 질문: FloatingBox를 사용하여 추가된 페이지 번호의 모양과 서식을 사용자 지정할 수 있나요?

A: 네, FloatingBox 내의 TextFragment 속성을 수정하여 페이지 번호의 모양을 사용자 지정할 수 있습니다. 글꼴 크기, 색상, 스타일, 정렬 및 기타 서식 옵션을 변경할 수 있습니다.

#### 질문: 비슷한 방법을 사용해 헤더나 푸터에 날짜, 시간 등의 다양한 동적 요소를 추가하는 게 가능할까요?

A: 물론입니다. FloatingBox 내의 TextFragment 콘텐츠를 수정하여 날짜, 시간, 문서 메타데이터 또는 사용자 지정 텍스트와 같은 다양한 동적 요소를 추가할 수 있습니다. 페이지 번호의 경우 "($p/ $P )" 또는 현재 날짜의 경우 "($date)"와 같은 매크로를 사용할 수 있습니다.

#### 질문: 헤더나 푸터 섹션에서 FloatingBox의 위치를 어떻게 지정합니까?
 A: 제공된 코드는 다음을 사용하여 FloatingBox의 위치를 설정합니다.`Left` 그리고`Top` 속성. 이 값을 조정하여 헤더 또는 푸터 섹션 내에서 FloatingBox를 원하는 대로 배치할 수 있습니다.

#### 질문: 머리글이나 바닥글의 페이지 번호에 다른 글꼴이나 스타일을 사용할 수 있나요?

대답: 네, FloatingBox 내의 TextFragment 속성을 수정하여 페이지 번호 텍스트의 글꼴, 스타일 및 기타 서식 속성을 사용자 정의할 수 있습니다.

#### 질문: FloatingBox의 콘텐츠가 크기를 초과하면 어떻게 되나요?

A: FloatingBox 내의 콘텐츠가 크기를 초과하면 잘리거나 레이아웃 문제가 발생할 수 있습니다. FloatingBox의 크기가 콘텐츠를 수용하기에 적합한지 확인하고 필요한 경우 페이지 레이아웃을 조정하는 것을 고려하세요.

#### 질문: 같은 페이지의 헤더나 푸터에 서로 다른 내용이 담긴 여러 개의 FloatingBox를 추가할 수 있나요?

대답: 네, 같은 페이지의 머리글이나 바닥글에 서로 다른 내용이 담긴 여러 개의 FloatingBox를 추가할 수 있습니다. 이렇게 하려면 별도의 FloatingBox 인스턴스를 만들고 이를 해당 페이지의 Paragraphs 컬렉션에 추가하면 됩니다.

#### 질문: FloatingBox 방식을 사용하여 본문이나 여백 등 PDF 문서의 다른 섹션에 콘텐츠를 추가할 수 있나요?

답변: FloatingBox는 일반적으로 머리글과 바닥글에 사용되지만, 페이지 내에서 다른 섹션(예: 본문이나 여백)에 콘텐츠를 추가하는 데에도 사용할 수 있습니다.