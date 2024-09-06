---
title: PDF 파일에 날짜 시간 스탬프 추가
linktitle: PDF 파일에 날짜 시간 스탬프 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 날짜 및 시간 스탬프를 쉽게 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
이 글에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 날짜 및 시간 스탬프를 추가하는 방법을 단계별로 안내해 드리겠습니다. 제공된 C# 소스 코드를 사용하여 기존 PDF 파일에 날짜 및 시간 스탬프를 추가하는 방법을 보여드리겠습니다.

## 요구 사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 개발 환경이 설치되어 있습니다.
- 프로젝트에서 다운로드하여 참조할 수 있는 .NET용 Aspose.PDF 라이브러리입니다.

## 1단계: 환경 설정

PDF 문서에 날짜와 시간 스탬프를 추가하려면 먼저 개발 환경을 설정해야 합니다. 다음 단계를 따르세요.

1. 좋아하는 IDE(통합 개발 환경)를 엽니다.
2. 새로운 C# 프로젝트를 만듭니다.
3. .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가했는지 확인하세요.

## 2단계: Aspose.PDF 라이브러리 추가

프로젝트에서 PDF 문서를 사용하려면 .NET용 Aspose.PDF 라이브러리가 필요합니다.

## 3단계: PDF 문서 로딩

날짜 및 시간 스탬프를 추가하는 첫 번째 단계는 기존 PDF 문서를 프로젝트에 로드하는 것입니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 엽니다
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서가 있는 디렉토리의 실제 경로로 바꿔야 합니다.

## 4단계: 날짜 및 시간 스탬프 생성

이제 문서를 업로드했습니다.

  PDF, 추가할 날짜와 시간 스탬프를 만들 수 있습니다. 방법은 다음과 같습니다.

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// 텍스트 버퍼 생성
TextStamp textStamp = new TextStamp(annotationText);
```

위 코드는 현재 날짜와 시간을 포함하는 새로운 텍스트 버퍼를 만듭니다.

## 5단계: 스탬프 속성 구성

PDF 문서에 스탬프를 추가하기 전에 여백, 수평 및 수직 정렬 등 스탬프의 다양한 속성을 구성할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 버퍼 속성 설정
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

귀하의 요구 사항에 맞게 이러한 속성을 조정할 수 있습니다.

## 6단계: PDF에 스탬프 추가

이제 날짜와 시간 스탬프가 준비되었으므로 PDF 문서의 특정 페이지에 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 페이지의 스탬프 컬렉션에 스탬프를 추가하세요
pdfDocument.Pages[1].AddStamp(textStamp);
```

위의 코드는 PDF 문서의 첫 페이지에 스탬프를 추가합니다. 필요한 경우 다른 페이지를 지정할 수 있습니다.

## 7단계: 출력 문서 저장

날짜와 시간 스탬프를 추가한 후에는 수정된 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 출력 문서 저장
pdfDocument.Save(dataDir);
```

위 코드는 편집된 PDF 문서를 지정된 디렉토리에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 날짜 시간 스탬프 추가를 위한 샘플 소스 코드 
```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// 텍스트 스탬프 생성
TextStamp textStamp = new TextStamp(annotationText);

// 스탬프의 속성 설정
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// 우표수집에 우표추가
pdfDocument.Pages[1].AddStamp(textStamp);
DefaultAppearance default_appearance = new DefaultAppearance("Arial", 6, System.Drawing.Color.Black);
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(0, 0, 0, 0), default_appearance);
textAnnotation.Name = "Stamp";
textAnnotation.Accept(new AnnotationSelector(textAnnotation));
textAnnotation.Contents = textStamp.Value;

Border border = new Border(textAnnotation);
border.Width = 0;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(0, 0, 0, 0);
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddDateTimeStamp_out.pdf";

// 출력 문서 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nDate time stamp added successfully.\nFile saved at " + dataDir);  
          
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 날짜 및 시간 스탬프를 추가하는 방법을 배웠습니다. 이제 이 지식을 자신의 프로젝트에 적용하여 PDF 문서에 날짜 및 시간 스탬프를 추가할 수 있습니다.

### PDF 파일에 날짜 및 시간 스탬프를 추가하기 위한 FAQ

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서에 날짜 및 타임스탬프를 추가하는 목적은 무엇입니까?

A: PDF 문서에 날짜와 시간 스탬프를 추가하면 문서가 수정되거나 생성된 시점을 표시하여 정보적 가치가 향상됩니다. 이 기능은 문서 변경 사항을 추적하고 문서 내역에 대한 참조 지점을 제공하는 데 유용합니다.

#### 질문: 특정 요구 사항에 맞게 날짜 및 시간 스탬프 형식을 사용자 지정할 수 있습니까?

 A: 네, 날짜 및 시간 스탬프의 형식을 선호도에 따라 사용자 지정할 수 있습니다. 제공된 C# 소스 코드는 다음을 사용합니다.`DateTime.Now.ToString()` 특정 형식으로 타임스탬프를 생성하는 방법입니다. 필요에 따라 타임스탬프를 포맷하도록 이 코드를 수정할 수 있습니다.

#### 질문: PDF 페이지의 특정 위치에 날짜와 시간 스탬프를 추가할 수 있나요?

 A: 물론입니다. PDF 페이지에서 날짜 및 시간 스탬프의 배치를 조정하려면 속성을 수정하면 됩니다.`TextStamp` 객체. 튜토리얼에서 제공하는 코드는 여백, 정렬, 수직 위치와 같은 속성을 설정하는 방법을 보여줍니다.

#### 질문: 같은 PDF 문서의 여러 페이지에 여러 개의 날짜와 시간 스탬프를 추가할 수 있나요?

 A: 네, 동일한 PDF 문서의 다른 페이지에 여러 날짜 및 시간 스탬프를 추가할 수 있습니다. 간단히 생성 프로세스를 반복하면 됩니다.`TextStamp` 객체를 만들고 각 페이지에 대한 속성을 구성합니다.

#### 질문: 날짜 및 타임스탬프 텍스트의 글꼴, 크기 또는 색상을 변경하려면 어떻게 해야 하나요?

 A: 날짜 및 시간 스탬프 텍스트의 글꼴, 크기 또는 색상을 수정하려면 해당 속성을 사용자 정의할 수 있습니다.`DefaultAppearance` 객체를 만드는 데 사용되는`TextStamp`원하는 모양을 얻으려면 글꼴 이름, 크기 및 색상 값을 조정하세요.

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서에 다른 유형의 주석이나 스탬프를 추가할 수 있나요?

A: 네, Aspose.PDF for .NET은 텍스트 주석, 스탬프, 선, 모양 등을 포함하여 PDF 문서에 추가할 수 있는 광범위한 주석 유형을 제공합니다. 주석 작업에 대한 자세한 내용은 Aspose.PDF 설명서를 참조하세요.

#### 질문: PDF 문서에 날짜와 시간 스탬프를 추가할 때 제한 사항이나 고려 사항이 있나요?

A: 날짜 및 시간 스탬프를 추가하는 것은 간단하지만 문서의 레이아웃 및 기존 콘텐츠와 같은 요소를 고려하세요. 스탬프의 배치가 중요한 정보를 가리거나 문서의 가독성에 영향을 미치지 않도록 하세요.

#### 질문: 이 방법을 내 프로젝트에 통합해 PDF 문서에 날짜와 타임스탬프를 추가하려면 어떻게 해야 하나요?

A: 이 방법을 통합하려면 제공된 단계를 따르고 코드를 조정하여 프로젝트 구조에 맞게 조정합니다. 기존 PDF 문서에 날짜 및 시간 스탬프를 추가하여 유용성을 높이고 변경 사항에 대한 명확한 타임라인을 제공할 수 있습니다.

#### 질문: 여러 PDF 문서에 날짜와 시간 스탬프를 추가하는 프로세스를 자동화할 수 있나요?

대답: 네, 여러 PDF 문서에 날짜 및 시간 스탬프를 추가하는 프로세스를 자동화할 수 있습니다. 즉, 문서 목록을 반복하면서 각 문서에 동일한 스탬핑 프로세스를 적용하는 스크립트나 프로그램을 만들면 됩니다.