---
title: PDF 파일에 텍스트 스탬프 추가
linktitle: PDF 파일에 텍스트 스탬프 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 텍스트 스탬프를 쉽게 추가하는 방법을 알아보세요.
type: docs
weight: 50
url: /ko/net/programming-with-stamps-and-watermarks/add-text-stamp/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 텍스트 스탬프를 추가하는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 사용하여 PDF 파일의 특정 페이지에 사용자 지정 텍스트 스탬프를 추가하는 방법을 보여드리겠습니다.

## 1단계: 환경 설정

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 개발 환경이 설치되어 있습니다.
- 프로젝트에서 다운로드하여 참조할 수 있는 .NET용 Aspose.PDF 라이브러리입니다.

## 2단계: PDF 문서 로딩

첫 번째 단계는 기존 PDF 문서를 프로젝트에 로드하는 것입니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 엽니다
Document pdfDocument = new Document(dataDir + "AddTextStamp.pdf");
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서가 있는 디렉토리의 실제 경로로 바꿔야 합니다.

## 3단계: 텍스트 버퍼 생성

이제 PDF 문서를 업로드했으므로 추가할 텍스트 스탬프를 만들 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 텍스트 버퍼를 생성합니다
TextStamp textStamp = new TextStamp("Example Stamp");
```

위 코드는 지정된 텍스트를 포함하는 새로운 텍스트 버퍼를 만듭니다.

## 4단계: 텍스트 스탬프 속성 구성

PDF 문서에 텍스트 스탬프를 추가하기 전에 배경, 위치, 회전, 글꼴, 크기 등 스탬프의 다양한 속성을 구성할 수 있습니다. 방법은 다음과 같습니다.

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

귀하의 요구 사항에 맞게 이러한 속성을 조정할 수 있습니다.

## 5단계: PDF에 텍스트 스탬프 추가

이제 텍스트 스탬프가 준비되었으므로 PDF 문서의 특정 페이지에 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
//특정 페이지에 텍스트 버퍼 추가
pdfDocument.Pages[1].AddStamp(textStamp);
```

위의 코드는 PDF 문서의 첫 페이지에 텍스트 스탬프를 추가합니다. 필요한 경우 다른 페이지를 지정할 수 있습니다.

## 6단계: 출력 문서 저장

텍스트 스탬프를 추가한 후에는 편집된 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 출력 문서 저장
pdfDocument.Save(dataDir);
```

위 코드는 수정된 PDF 문서를 지정된 디렉토리에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 텍스트 스탬프 추가를 위한 샘플 소스 코드 
```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir+ "AddTextStamp.pdf");

// 텍스트 스탬프 생성
TextStamp textStamp = new TextStamp("Sample Stamp");

// 스탬프를 배경으로 할지 설정
textStamp.Background = true;

// 원점 설정
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

축하합니다! Aspose.PDF for .NET을 사용하여 텍스트 스탬프를 추가하는 방법을 배웠습니다. 이제 이 지식을 자신의 프로젝트에 적용하여 PDF 문서에 사용자 정의 텍스트 스탬프를 추가할 수 있습니다.

### PDF 파일에 텍스트 스탬프 추가에 대한 FAQ

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 파일에 텍스트 스탬프를 추가하는 목적은 무엇입니까?

A: 텍스트 스탬프를 추가하면 PDF 문서의 특정 페이지에 사용자 지정 텍스트를 배치할 수 있습니다. 이 기능은 레이블, 주석, 워터마크 또는 기타 텍스트 정보를 추가하여 문서의 내용을 향상시키고 추가 컨텍스트를 제공하는 데 유용합니다.

#### 질문: 텍스트 스탬프의 글꼴, 크기, 색상, 회전 등 모양을 사용자 지정할 수 있나요?

 A: 네, 텍스트 스탬프의 모양을 완전히 사용자 지정할 수 있습니다. 제공된 C# 소스 코드는 다양한 속성을 설정하는 방법을 보여줍니다.`TextStamp` 글꼴, 글꼴 크기, 글꼴 스타일, 텍스트 색상, 배경색 및 회전을 포함한 개체입니다.

#### 질문: 같은 PDF 문서의 여러 페이지에 여러 개의 텍스트 스탬프를 추가할 수 있나요?

A: 물론입니다. 동일한 PDF 문서의 여러 페이지에 여러 텍스트 스탬프를 추가할 수 있습니다. 튜토리얼에서 제공하는 코드를 사용하면 텍스트 스탬프를 추가할 대상 페이지를 지정할 수 있으므로 문서 내의 여러 페이지에 다양하게 활용할 수 있습니다.

#### 질문: PDF 문서 내에서 텍스트 스탬프의 위치를 어떻게 지정합니까?

 A: 텍스트 스탬프의 위치를 수정하여 사용자 정의할 수 있습니다.`XIndent` 그리고`YIndent` 의 속성`TextStamp` 객체. 이러한 속성은 페이지의 원점을 기준으로 스탬프의 왼쪽 상단 모서리의 좌표를 정의합니다.

#### 질문: 이 방법을 기존 PDF 문서에 적용해 텍스트 스탬프를 추가할 수 있나요?

A: 네, 이 방법을 기존 PDF 문서에 적용하여 텍스트 스탬프를 추가할 수 있습니다. 튜토리얼에서 제공하는 코드는 기존 PDF 문서를 로드하고 특정 페이지에 텍스트 스탬프를 추가하는 방법을 보여줍니다.

#### 질문: 텍스트 스탬프에 배경색과 전경색을 모두 추가할 수 있나요?

 A: 네, 텍스트 스탬프에 배경색과 전경색을 모두 추가할 수 있습니다.`Background` 재산에`true` , 텍스트 스탬프에 컬러 배경을 제공할 수 있습니다. 또한, 다음을 설정할 수 있습니다.`TextState.ForegroundColor` 텍스트 자체의 색상을 지정하는 속성입니다.

#### 질문: 텍스트 스탬프가 PDF 문서의 기본 내용을 가리지 않도록 하려면 어떻게 해야 하나요?

A: 텍스트 스탬프를 추가할 때는 중요한 정보를 가리거나 문서의 가독성에 부정적인 영향을 미치지 않도록 배치를 주의하세요.`XIndent` 그리고`YIndent` 텍스트 스탬프를 적절하게 배치하려면 속성을 사용합니다.

#### 질문: 이 방법을 사용해 텍스트 외에 이미지나 로고 등 스탬프를 추가할 수 있나요?

A: 이 특정 튜토리얼은 텍스트 스탬프를 추가하는 데 중점을 두고 있지만, Aspose.PDF for .NET을 사용하여 이미지나 로고와 같은 다른 유형의 스탬프를 추가할 수도 있습니다. 이 프로세스에는 적절한 스탬프 객체를 만들고 속성을 구성하는 것이 포함됩니다.

#### 질문: 여러 PDF 문서에 텍스트 스탬프를 추가하는 프로세스를 자동화하려면 어떻게 해야 하나요?

답변: 여러 PDF 문서에 텍스트 스탬프를 추가하는 프로세스를 자동화하려면 문서 목록을 반복하고 각 문서에 동일한 텍스트 스탬핑 프로세스를 적용하는 스크립트나 프로그램을 만들면 됩니다.