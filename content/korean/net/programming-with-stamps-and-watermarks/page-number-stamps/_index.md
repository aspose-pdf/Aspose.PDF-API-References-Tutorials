---
title: PDF 파일의 페이지 번호 스탬프
linktitle: PDF 파일의 페이지 번호 스탬프
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 페이지 번호 스탬프를 추가하는 방법을 알아보세요.
type: docs
weight: 160
url: /ko/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 페이지 번호 스탬프를 추가하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 사용하여 기존 PDF 문서를 열고, 페이지 번호 스탬프를 만들고, 해당 속성을 설정하고, PDF 파일의 특정 페이지에 추가합니다.

## 1단계: 환경 설정

시작하기 전에 다음 사항이 있는지 확인하세요.

- 설치된 .NET 개발 환경.
- .NET용 Aspose.PDF 라이브러리가 다운로드되어 프로젝트에서 참조됩니다.

## 2단계: 기존 PDF 문서 로드

첫 번째 단계는 기존 PDF 문서를 프로젝트에 로드하는 것입니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 기존 PDF 문서 열기
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서가 있는 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 페이지 번호 매기기 스탬프 생성 및 구성

이제 PDF 문서가 로드되었으므로 페이지 번호 매기기 버퍼를 생성하고 필요에 따라 구성할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 페이지 번호 버퍼 만들기
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// 버퍼가 백그라운드에 있는지 여부를 정의합니다.
pageNumberStamp.Background = false;

// 페이지 번호 매기기 버퍼의 형식
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

// 페이지 번호 매기기 버퍼의 아래쪽 여백
pageNumberStamp.BottomMargin = 10;

// 페이지 번호 매기기 버퍼의 가로 정렬
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

// 페이지 번호 매기기 시작 번호
pageNumberStamp.StartingNumber = 1;

// 페이지 번호 버퍼 텍스트 속성 설정
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

위 코드는 페이지 번호 형식, 아래쪽 여백, 가로 정렬, 시작 번호 및 텍스트 속성과 같은 속성을 사용하여 페이지 번호 스탬프를 만듭니다.

## 4단계: 특정 페이지에 페이지 번호 스탬프 추가

페이지 번호 스탬프가 구성되면 PDF 문서의 특정 페이지에 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 특정 페이지에 페이지 번호 버퍼 추가
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

위 코드는 PDF 문서의 첫 번째 페이지에 페이지 번호 스탬프를 추가합니다. 필요에 따라 페이지 번호를 변경할 수 있습니다.

## 5단계: 수정된 PDF 문서 저장

페이지 번호 스탬프가 PDF 문서에 추가되면 수정된 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 수정된 PDF 문서 저장
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

"YOUR DOCUMENTS DIRECTORY"를 편집된 PDF 문서를 저장하려는 디렉토리의 실제 경로로 바꾸십시오.

### .NET용 Aspose.PDF를 사용하는 페이지 번호 스탬프의 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

// 페이지 번호 스탬프 만들기
PageNumberStamp pageNumberStamp = new PageNumberStamp();

// 스탬프가 배경인지 여부
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

// 텍스트 속성 설정
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

// 특정 페이지에 스탬프 추가
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

// 출력 문서 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 PDF 문서에 페이지 번호 스탬프를 추가하는 방법을 배웠습니다. 이제 명확하고 유익한 페이지 번호를 추가하여 PDF 문서를 개인화할 수 있습니다.

### PDF 파일의 페이지 번호 스탬프에 대한 FAQ

#### Q: 페이지 번호 스탬프란 무엇이며 PDF 파일에 페이지 번호를 추가하는 데 어떻게 사용됩니까?

A: 페이지 번호 스탬프는 PDF 문서의 특정 페이지에 동적 페이지 번호를 추가할 수 있는 Aspose.PDF의 기능입니다. 이 자습서에서는 PageNumberStamp 개체를 만들고 해당 속성을 구성한 다음 지정된 페이지에 추가하여 이를 수행합니다.

#### Q: 제공된 C# 소스 코드는 어떻게 PDF 파일에 페이지 번호 스탬프를 추가합니까?

답변: 코드는 기존 PDF 문서를 로드하고, PageNumberStamp를 생성하고, 다양한 속성(예: 형식, 글꼴, 정렬 등)을 설정한 다음 특정 페이지에 스탬프를 추가하는 방법을 보여줍니다. 스탬프는 자동으로 총 페이지 수를 계산하고 올바른 페이지 번호를 삽입합니다.

#### Q: 글꼴 스타일, 색상, 크기 등 페이지 번호의 모양을 사용자 정의할 수 있나요?

A: 물론, 글꼴, 글꼴 크기, 글꼴 스타일(굵게, 기울임꼴 등) 및 텍스트 색상과 같은 속성을 조정하여 페이지 번호 스탬프의 모양을 사용자 정의할 수 있습니다.

#### Q: PDF 문서 내의 여러 페이지에 페이지 번호 스탬프를 추가할 수 있습니까?

A: 예, 여러 PageNumberStamp 개체를 생성하고 각 개체를 원하는 페이지에 추가하여 여러 페이지에 페이지 번호 스탬프를 추가할 수 있습니다.

#### Q: 페이지 번호 스탬프를 페이지 콘텐츠의 일부로 표시할지 아니면 배경 요소로 표시할지 선택할 수 있나요?

 A: 예. 페이지 번호 스탬프를 페이지 콘텐츠의 일부로 표시할지 아니면 배경 요소로 표시할지를 제어할 수 있습니다.`Background` PageNumberStamp의 속성입니다.

#### Q: 총 페이지 수를 포함하여 페이지 번호의 형식을 어떻게 지정합니까?

 A: 코드는 다음을 사용합니다.`Format`PageNumberStamp의 속성을 사용하여 페이지 번호 형식을 지정합니다. 매크로 "# of"는 총 페이지 수를 나타내는 데 사용됩니다.

#### Q: 동일한 페이지 번호 스탬프를 여러 페이지에 추가하면 어떻게 되나요?

A: 동일한 PageNumberStamp 인스턴스를 여러 페이지에 추가하면 각 페이지에 대한 올바른 페이지 번호가 표시됩니다. 스탬프는 페이지 번호와 총 페이지 수를 자동으로 조정합니다.

#### 질문: PDF 문서의 머리글이나 바닥글 섹션에 페이지 번호 스탬프를 추가할 수 있습니까?

A: PageNumberStamp는 일반적으로 페이지 콘텐츠에 직접 추가되지만 FloatingBox 또는 기타 기술을 사용하여 머리글이나 바닥글 섹션에 배치할 수 있습니다.

#### Q: 페이지에서 페이지 번호 스탬프 위치를 어떻게 지정합니까?

 답:`BottomMargin` 그리고`HorizontalAlignment` PageNumberStamp의 속성을 사용하면 페이지 내 스탬프 위치를 제어할 수 있습니다.

#### Q: 1이 아닌 다른 번호로 페이지 번호 매기기를 시작하려면 어떻게 해야 합니까?

 A: 다음을 설정할 수 있습니다.`StartingNumber`PageNumberStamp의 속성을 사용하여 시작 페이지 번호를 지정합니다.