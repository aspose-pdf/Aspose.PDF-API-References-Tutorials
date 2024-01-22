---
title: PDF 파일에 텍스트 스탬프 추가
linktitle: PDF 파일에 텍스트 스탬프 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 텍스트 스탬프를 쉽게 추가하는 방법을 알아보세요.
type: docs
weight: 50
url: /ko/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에 텍스트 스탬프를 추가하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 사용하여 PDF 파일의 특정 페이지에 사용자 정의 텍스트 스탬프를 추가하는 방법을 보여 드리겠습니다.

## 1단계: 환경 설정

시작하기 전에 다음 사항이 있는지 확인하세요.

- 설치된 .NET 개발 환경.
- .NET용 Aspose.PDF 라이브러리가 다운로드되어 프로젝트에서 참조됩니다.

## 2단계: PDF 문서 로드

첫 번째 단계는 기존 PDF 문서를 프로젝트에 로드하는 것입니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서가 있는 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 텍스트 버퍼 생성

이제 PDF 문서를 업로드했으므로 추가할 텍스트 스탬프를 생성할 수 있습니다. 수행 방법은 다음과 같습니다.

```csharp
// 텍스트 버퍼 만들기
TextStamp textStamp = new TextStamp("Example Stamp");
```

위의 코드는 지정된 텍스트를 포함하는 새 텍스트 버퍼를 만듭니다.

## 4단계: 텍스트 스탬프 속성 구성

PDF 문서에 텍스트 스탬프를 추가하기 전에 배경, 위치, 회전, 글꼴, 크기 등과 같은 스탬프의 다양한 속성을 구성할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 텍스트 버퍼 속성 구성
textStamp. Background = true;
textStamp. XIndent = 100;
textStamp. YIndent = 100;
textStamp.Rotate = Rotate.on90;
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold | FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);
```

필요에 따라 이러한 속성을 조정할 수 있습니다.

## 5단계: PDF에 텍스트 스탬프 추가

이제 텍스트 스탬프가 준비되었으므로 PDF 문서의 특정 페이지에 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
//특정 페이지에 텍스트 버퍼 추가
pdfDocument.Pages[1].AddStamp(textStamp);
```

위의 코드는 PDF 문서의 첫 번째 페이지에 텍스트 스탬프를 추가합니다. 필요한 경우 다른 페이지를 지정할 수 있습니다.

## 6단계: 출력 문서 저장

텍스트 스탬프를 추가한 후에는 편집된 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 출력 문서 저장
pdfDocument.Save(dataDir);
```

위의 코드는 수정된 PDF 문서를 지정된 디렉터리에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 텍스트 스탬프 추가에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// 텍스트 스탬프 만들기
TextStamp textStamp = new TextStamp("Sample Stamp");

// 스탬프가 배경인지 여부를 설정합니다.
textStamp.Background = true;

// 원산지 설정
textStamp.XIndent = 100;
textStamp.YIndent = 100;

// 스탬프 회전
textStamp.Rotate = Rotation.on90;

// 텍스트 속성 설정
textStamp.TextState.Font = FontRepository.FindFont("Arial");
textStamp.TextState.FontSize = 14.0F;
textStamp.TextState.FontStyle = FontStyles.Bold;
textStamp.TextState.FontStyle = FontStyles.Italic;
textStamp.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Aqua);

// 특정 페이지에 스탬프 추가
pdfDocument.Pages[1].AddStamp(textStamp);
dataDir = dataDir + "AddTextStamp_out.pdf";

// 출력 문서 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nText stamp added successfully.\nFile saved at " + dataDir);            

```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 텍스트 스탬프를 추가하는 방법을 배웠습니다. 이제 이 지식을 자신의 프로젝트에 적용하여 PDF 문서에 사용자 정의 텍스트 스탬프를 추가할 수 있습니다.

### PDF 파일에 텍스트 스탬프 추가에 대한 FAQ

#### Q: Aspose.PDF for .NET을 사용하여 PDF 파일에 텍스트 스탬프를 추가하는 목적은 무엇입니까?

답변: 텍스트 스탬프를 추가하면 PDF 문서의 특정 페이지에 사용자 정의 텍스트를 배치할 수 있습니다. 이 기능은 레이블, 설명, 워터마크 또는 기타 텍스트 정보를 추가하여 문서의 내용을 향상시키고 추가 컨텍스트를 제공하는 데 유용합니다.

#### Q: 글꼴, 크기, 색상, 회전 등 텍스트 스탬프의 모양을 사용자 정의할 수 있나요?

 A: 예, 텍스트 스탬프의 모양을 완전히 사용자 정의할 수 있습니다. 제공된 C# 소스 코드는 다양한 속성을 설정하는 방법을 보여줍니다.`TextStamp` 글꼴, 글꼴 크기, 글꼴 스타일, 텍스트 색상, 배경색 및 회전을 포함한 개체.

#### Q: 동일한 PDF 문서의 다른 페이지에 여러 텍스트 스탬프를 추가할 수 있습니까?

A: 물론, 동일한 PDF 문서의 서로 다른 페이지에 여러 개의 텍스트 스탬프를 추가할 수 있습니다. 튜토리얼에서 제공하는 코드를 사용하면 텍스트 스탬프를 추가하기 위한 대상 페이지를 지정할 수 있으므로 문서 내의 다양한 페이지에 다목적으로 사용할 수 있습니다.

#### Q: PDF 문서 내에서 텍스트 스탬프의 위치를 어떻게 지정합니까?

 A: 텍스트 스탬프의 위치를 수정하여 사용자 정의할 수 있습니다.`XIndent` 그리고`YIndent` 의 속성`TextStamp` 물체. 이러한 속성은 페이지 원점을 기준으로 스탬프의 왼쪽 위 모서리 좌표를 정의합니다.

#### Q: 기존 PDF 문서에 이 방법을 적용하여 텍스트 스탬프를 추가할 수 있습니까?

A: 예, 기존 PDF 문서에 이 방법을 적용하여 텍스트 스탬프를 추가할 수 있습니다. 튜토리얼에서 제공되는 코드는 기존 PDF 문서를 로드하고 특정 페이지에 텍스트 스탬프를 추가하는 방법을 보여줍니다.

#### Q: 텍스트 스탬프에 배경색과 전경색을 모두 추가할 수 있나요?

 A: 예, 텍스트 스탬프에 배경색과 전경색을 모두 추가할 수 있습니다. 설정하여`Background` 재산`true` 를 사용하면 텍스트 스탬프에 컬러 배경을 제공할 수 있습니다. 또한 다음을 설정할 수 있습니다.`TextState.ForegroundColor` 속성은 텍스트 자체의 색상을 지정합니다.

#### 질문: 텍스트 스탬프가 PDF 문서의 기본 내용을 가리지 않도록 하려면 어떻게 해야 합니까?

 A: 텍스트 스탬프를 추가할 때 중요한 정보를 방해하거나 문서의 가독성에 부정적인 영향을 미치지 않도록 위치에 주의하세요. 당신은 조정할 수 있습니다`XIndent` 그리고`YIndent` 속성을 사용하여 텍스트 스탬프를 적절하게 배치합니다.

#### Q: 이 방법을 사용하여 이미지나 로고 등 텍스트 이외의 스탬프를 추가할 수 있나요?

A: 이 특정 튜토리얼은 텍스트 스탬프 추가에 중점을 두고 있지만 마찬가지로 .NET용 Aspose.PDF를 사용하여 이미지나 로고와 같은 다른 유형의 스탬프를 추가할 수도 있습니다. 이 프로세스에는 적절한 스탬프 개체를 만들고 해당 속성을 구성하는 작업이 포함됩니다.

#### Q: 여러 PDF 문서에 텍스트 스탬프를 추가하는 프로세스를 자동화하려면 어떻게 해야 합니까?

답변: 문서 목록을 반복하고 각 문서에 동일한 텍스트 스탬프 프로세스를 적용하는 스크립트나 프로그램을 만들어 여러 PDF 문서에 텍스트 스탬프를 추가하는 프로세스를 자동화할 수 있습니다.