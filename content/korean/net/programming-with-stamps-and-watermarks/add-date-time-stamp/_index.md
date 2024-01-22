---
title: PDF 파일에 날짜 시간 스탬프 추가
linktitle: PDF 파일에 날짜 시간 스탬프 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 날짜 및 시간 스탬프를 쉽게 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-stamps-and-watermarks/add-date-time-stamp/
---
이 기사에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 날짜 및 시간 스탬프를 추가하는 방법을 단계별로 설명합니다. 제공된 C# 소스 코드를 사용하여 기존 PDF 파일에 날짜 및 시간 스탬프를 추가하는 방법을 보여 드리겠습니다.

## 요구사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- 설치된 .NET 개발 환경.
- .NET용 Aspose.PDF 라이브러리가 다운로드되어 프로젝트에서 참조됩니다.

## 1단계: 환경 설정

PDF 문서에 날짜 및 시간 스탬프를 추가하려면 먼저 개발 환경을 설정해야 합니다. 따라야 할 단계는 다음과 같습니다.

1. 즐겨찾는 IDE(통합 개발 환경)를 엽니다.
2. 새 C# 프로젝트를 만듭니다.
3. .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가했는지 확인하세요.

## 2단계: Aspose.PDF 라이브러리 추가

프로젝트에서 PDF 문서를 작업하려면 .NET용 Aspose.PDF 라이브러리가 필요합니다.

## 3단계: PDF 문서 로드

날짜 및 시간 스탬프를 추가하는 첫 번째 단계는 기존 PDF 문서를 프로젝트에 로드하는 것입니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서가 있는 디렉토리의 실제 경로로 바꾸십시오.

## 4단계: 날짜 및 타임스탬프 만들기

이제 문서를 업로드했으므로

  PDF에 추가할 날짜 및 시간 스탬프를 생성할 수 있습니다. 수행 방법은 다음과 같습니다.

```csharp
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt");

// 텍스트 버퍼 만들기
TextStamp textStamp = new TextStamp(annotationText);
```

위의 코드는 현재 날짜와 시간을 포함하는 새 텍스트 버퍼를 만듭니다.

## 5단계: 스탬프 속성 구성

PDF 문서에 스탬프를 추가하기 전에 여백, 가로 및 세로 정렬 등과 같은 스탬프의 다양한 속성을 구성할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 버퍼 속성 설정
textStamp.BottomMargin = 10;
textStamp. RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;
```

필요에 따라 이러한 속성을 조정할 수 있습니다.

## 6단계: PDF에 스탬프 추가

이제 날짜 및 시간 스탬프가 준비되었으므로 PDF 문서의 특정 페이지에 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 페이지의 우표 컬렉션에 우표를 추가하세요.
pdfDocument.Pages[1].AddStamp(textStamp);
```

위의 코드는 PDF 문서의 첫 번째 페이지에 스탬프를 추가합니다. 필요한 경우 다른 페이지를 지정할 수 있습니다.

## 7단계: 출력 문서 저장

날짜와 시간 스탬프를 추가하고 나면 수정된 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 출력 문서 저장
pdfDocument.Save(dataDir);
```

위 코드는 편집된 PDF 문서를 지정된 디렉토리에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 날짜 시간 스탬프 추가에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");
string annotationText = string.Empty;
annotationText = DateTime.Now.ToString("MM/dd/yy hh:mm:ss tt ");

// 텍스트 스탬프 만들기
TextStamp textStamp = new TextStamp(annotationText);

// 스탬프 속성 설정
textStamp.BottomMargin = 10;
textStamp.RightMargin = 20;
textStamp.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// 우표 수집에 우표 추가하기
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

축하합니다! .NET용 Aspose.PDF를 사용하여 날짜 및 시간 스탬프를 추가하는 방법을 배웠습니다. 이제 이 지식을 자신의 프로젝트에 적용하여 PDF 문서에 날짜 및 시간 스탬프를 추가할 수 있습니다.

### PDF 파일에 날짜 타임스탬프 추가에 대한 FAQ

#### Q: Aspose.PDF for .NET을 사용하여 PDF 문서에 날짜 및 시간 스탬프를 추가하는 목적은 무엇입니까?

답변: PDF 문서에 날짜 및 시간 스탬프를 추가하면 문서가 수정되거나 생성된 시기를 표시하여 정보 가치가 향상됩니다. 이 기능은 문서 변경 사항을 추적하고 문서 기록에 대한 참조 지점을 제공하는 데 유용합니다.

#### Q: 특정 요구 사항에 맞게 날짜 및 시간 스탬프 형식을 사용자 정의할 수 있습니까?

 A: 예, 원하는 대로 날짜 및 시간 스탬프 형식을 사용자 정의할 수 있습니다. 제공된 C# 소스 코드는`DateTime.Now.ToString()` 특정 형식의 타임스탬프를 생성하는 방법입니다. 필요에 따라 이 코드를 수정하여 타임스탬프 형식을 지정할 수 있습니다.

#### Q: PDF 페이지의 특정 위치에 날짜와 시간 스탬프를 추가할 수 있습니까?

 A: 물론입니다. PDF 페이지의 속성을 수정하여 PDF 페이지의 날짜 및 시간 스탬프 위치를 조정할 수 있습니다.`TextStamp` 물체. 자습서에 제공된 코드는 여백, 정렬, 세로 위치 지정과 같은 속성을 설정하는 방법을 보여줍니다.

#### 질문: 동일한 PDF 문서의 서로 다른 페이지에 여러 날짜 및 시간 스탬프를 추가할 수 있습니까?

 A: 예, 동일한 PDF 문서의 여러 페이지에 여러 날짜 및 시간 스탬프를 추가할 수 있습니다. 단순히 생성 과정을 반복하면 됩니다.`TextStamp` 개체를 만들고 원하는 각 페이지에 대한 속성을 구성합니다.

#### Q: 날짜 및 시간 스탬프 텍스트의 글꼴, 크기 또는 색상을 어떻게 변경할 수 있습니까?

 A: 날짜 및 시간 스탬프 텍스트의 글꼴, 크기 또는 색상을 수정하려면`DefaultAppearance` 생성하는 데 사용된 객체`TextStamp`. 원하는 모양을 얻으려면 글꼴 이름, 크기 및 색상 값을 조정하십시오.

#### Q: Aspose.PDF for .NET을 사용하여 PDF 문서에 다른 유형의 주석이나 스탬프를 추가할 수 있습니까?

답변: 예, .NET용 Aspose.PDF는 텍스트 주석, 스탬프, 선, 모양 등을 포함하여 PDF 문서에 추가할 수 있는 광범위한 주석 유형을 제공합니다. 주석 작업에 대한 자세한 내용은 Aspose.PDF 문서를 참조하세요.

#### Q: PDF 문서에 날짜 및 시간 스탬프를 추가할 때 제한 사항이나 고려 사항이 있습니까?

A: 날짜 및 타임스탬프를 추가하는 것은 간단하지만 문서의 레이아웃 및 기존 콘텐츠와 같은 요소를 고려하십시오. 스탬프 배치로 인해 중요한 정보가 흐려지거나 문서의 가독성에 영향을 주지 않는지 확인하십시오.

#### Q: 이 방법을 내 프로젝트에 통합하여 PDF 문서에 날짜 및 시간 스탬프를 추가하려면 어떻게 해야 합니까?

A: 이 방법을 통합하려면 제공된 단계를 따르고 프로젝트 구조에 맞게 코드를 조정하세요. 기존 PDF 문서에 날짜 및 시간 스탬프를 추가하여 유용성을 높이고 명확한 변경 일정을 제공할 수 있습니다.

#### 질문: 여러 PDF 문서에 날짜 및 시간 스탬프를 추가하는 프로세스를 자동화할 수 있습니까?

A: 예, 문서 목록을 반복하고 각 문서에 동일한 스탬프 프로세스를 적용하는 스크립트나 프로그램을 만들어 여러 PDF 문서에 날짜 및 시간 스탬프를 추가하는 프로세스를 자동화할 수 있습니다.