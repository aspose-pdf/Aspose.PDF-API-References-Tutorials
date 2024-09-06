---
title: 태그가 지정된 이미지로 PDF 만들기
linktitle: 태그가 지정된 이미지로 PDF 만들기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 태그가 지정된 이미지로 PDF를 만드는 단계별 가이드입니다.
type: docs
weight: 40
url: /ko/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 태그가 지정된 이미지가 있는 PDF 문서를 만드는 방법에 대한 단계별 가이드를 제공합니다. Aspose.PDF는 PDF 문서를 프로그래밍 방식으로 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다. Aspose.PDF의 태그가 지정된 콘텐츠 구조 기능을 사용하여 PDF 문서에 태그가 지정된 이미지를 추가할 수 있습니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. .NET Framework와 함께 설치된 Visual Studio.
2. .NET용 Aspose.PDF 라이브러리.

## 1단계: 프로젝트 설정

시작하려면 Visual Studio에서 새 프로젝트를 만들고 .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다. Aspose 공식 웹사이트에서 라이브러리를 다운로드하여 컴퓨터에 설치할 수 있습니다.

## 2단계: 필요한 네임스페이스 가져오기

C# 코드 파일에서 Aspose.PDF에서 제공하는 클래스와 메서드에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 3단계: 태그가 지정된 이미지로 PDF 문서 만들기

다음 코드를 사용하여 태그가 지정된 이미지가 있는 PDF 문서를 만듭니다.

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

이 코드는 빈 PDF 문서를 만들고 Aspose.PDF에서 제공하는 방법을 사용하여 태그가 지정된 이미지를 추가합니다. 이미지는 대체 텍스트, 제목 및 태그로 지정됩니다.

## 4단계: PDF 문서 저장

다음 코드를 사용하여 PDF 문서를 저장하세요.

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

이 코드는 태그가 지정된 이미지가 있는 PDF 문서를 지정된 파일에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 태그가 지정된 이미지로 PDF 만들기 샘플 소스 코드 
```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
// 해상도 300 DPI(기본값)의 이미지 추가
figure1.SetImage(dataDir + @"aspose-logo.jpg");
// PDF 문서 저장
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 태그가 지정된 이미지가 있는 PDF 문서를 만드는 방법을 배웠습니다. 태그가 지정된 이미지는 PDF 문서에 추가적이고 구조화된 정보를 추가합니다.

### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET을 사용하여 태그가 지정된 이미지가 포함된 PDF 문서를 만드는 목적은 무엇입니까?

A: Aspose.PDF for .NET을 사용하여 태그가 지정된 이미지가 있는 PDF 문서를 만들면 태그가 지정된 이미지를 문서의 콘텐츠에 추가할 수 있습니다. 태그가 지정된 이미지는 대체 텍스트 및 제목과 같은 구조화된 정보를 제공하여 접근성과 구성을 향상시킵니다.

#### 질문: Aspose.PDF 라이브러리는 태그가 지정된 이미지가 포함된 PDF 문서를 만드는 데 어떻게 도움이 되나요?

A: Aspose.PDF for .NET은 PDF 문서를 프로그래밍 방식으로 만들고, 조작하고, 변환하는 기능을 제공하는 강력한 라이브러리입니다. 이 튜토리얼에서는 라이브러리의 태그가 지정된 콘텐츠 구조 기능을 사용하여 태그가 지정된 이미지를 PDF 문서에 추가합니다.

#### 질문: Aspose.PDF for .NET을 사용하여 태그가 지정된 이미지가 있는 PDF 문서를 만드는 데 필요한 전제 조건은 무엇입니까?

답변: 시작하기 전에 .NET 프레임워크와 함께 Visual Studio가 설치되어 있는지 확인하고 프로젝트에서 .NET용 Aspose.PDF 라이브러리가 참조되었는지 확인하세요.

#### 질문: 제공된 C# 코드는 어떻게 태그가 지정된 이미지가 포함된 PDF 문서를 생성합니까?

A: 이 코드는 PDF 문서를 만들고, 태그가 지정된 이미지 요소를 정의하고, 문서의 콘텐츠에 추가하는 방법을 보여줍니다. 태그가 지정된 이미지에는 Aspose.PDF에서 제공하는 메서드를 사용하여 대체 텍스트, 제목 및 태그가 포함됩니다.

#### 질문: 태그된 이미지에 다른 이미지 형식을 사용할 수 있나요?

A: 네, 태그가 지정된 이미지에 JPEG, PNG, GIF 등 다양한 이미지 형식을 사용할 수 있습니다. 튜토리얼에 제공된 코드 예제에서는 JPEG 이미지를 사용하지만, 원하는 형식의 이미지 파일 경로로 바꿀 수 있습니다.

#### 질문: 태그가 지정된 이미지에서 대체 텍스트(alt 텍스트)는 어떻게 사용되나요?

 A: 대체 텍스트는 시각 장애인 사용자를 위해 화면 판독기에서 소리 내어 읽어주는 이미지의 텍스트 설명을 제공합니다. 제공된 코드에서 대체 텍스트는 다음을 사용하여 설정됩니다.`AlternativeText` 의 속성`IllustrationElement` 태그된 이미지를 나타냅니다.

####  Q: 어떻게`SetTitle` method contribute to the PDF document's tagged image?

 A: 그`SetTitle` 방법은 PDF 문서의 태그가 지정된 콘텐츠의 제목을 설정하여 태그가 지정된 이미지에 대한 추가 컨텍스트를 제공합니다. 이 제목은 태그가 지정된 콘텐츠의 목적이나 주제를 식별하는 데 도움이 될 수 있습니다.

#### 질문: 태그된 이미지의 태그와 제목을 사용자 지정할 수 있나요?

 A: 예, 태그가 지정된 이미지의 태그와 제목을 사용자 정의할 수 있습니다.`SetTag` 그리고`Title` 의 방법`IllustrationElement`. 코드 예제는 태그를 "Fig"로, 제목을 "Picture 1"로 설정하는 방법을 보여줍니다.

#### 질문: 태그된 이미지가 접근 가능하고 접근성 기준을 준수하는지 어떻게 확인할 수 있나요?

A: Aspose.PDF의 태그가 지정된 콘텐츠 구조 기능을 사용하고 대체 텍스트와 기타 관련 정보를 제공함으로써 태그가 지정된 이미지의 접근성에 기여합니다. 접근성 표준을 준수하려면 대체 텍스트와 문서 구조에 대한 모범 사례를 따라야 합니다.

#### 질문: 비슷한 기술을 사용해 동일한 PDF 문서에 여러 개의 태그가 지정된 이미지를 추가하는 것이 가능할까요?

 A: 네, 유사한 기술을 사용하여 동일한 PDF 문서에 태그가 지정된 여러 이미지를 추가할 수 있습니다. 추가`IllustrationElement` 태그가 지정된 각 이미지에 대한 인스턴스를 만들고 필요에 따라 속성을 사용자 정의합니다.