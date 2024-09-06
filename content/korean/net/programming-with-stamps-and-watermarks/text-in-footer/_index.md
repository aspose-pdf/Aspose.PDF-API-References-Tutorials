---
title: PDF 파일의 바닥글에 있는 텍스트
linktitle: PDF 파일의 바닥글에 있는 텍스트
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 바닥글에 텍스트를 추가하는 방법을 알아보세요.
type: docs
weight: 180
url: /ko/net/programming-with-stamps-and-watermarks/text-in-footer/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일의 푸터에 텍스트를 추가하는 방법을 알아봅니다. 아래 단계를 따르세요.

## 1단계: 프로젝트 준비

.NET용 Aspose.PDF를 설치하고 C# 프로젝트를 생성했는지 확인하세요.

## 2단계: 네임스페이스 가져오기

C# 소스 파일에 다음 네임스페이스를 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: 문서 열기

제공된 경로를 사용하여 기존 PDF 문서를 엽니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document pdfDocument = new Document(dataDir + "TextinFooter.pdf");
```

"YOUR DOCUMENTS DIRECTORY"를 실제 문서 디렉토리 경로로 바꿔야 합니다.

## 4단계: 바닥글 텍스트 만들기

바닥글에 추가하려는 텍스트로 새 텍스트 스탬프를 만듭니다.

```csharp
TextStamp textStamp = new TextStamp("footer text");
```

아래쪽 여백, 가로 정렬, 세로 정렬 등의 속성을 변경하여 텍스트를 사용자 지정할 수 있습니다.

## 5단계: 모든 페이지에 바닥글 텍스트 추가

PDF 문서의 모든 페이지를 살펴보고 바닥글에 텍스트 스탬프를 추가합니다.

```csharp
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(textStamp);
}
```

## 6단계: PDF 문서 저장

모든 페이지에 바닥글 텍스트를 추가한 후 업데이트된 PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "TextinFooter_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at: " + dataDir);
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서를 저장하려는 디렉토리의 실제 경로로 바꿔야 합니다.

### .NET용 Aspose.PDF를 사용한 Textin Footer의 샘플 소스 코드 
```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir+ "TextinFooter.pdf");

// 푸터 만들기
TextStamp textStamp = new TextStamp("Footer Text");

// 스탬프의 속성 설정
textStamp.BottomMargin = 10;
textStamp.HorizontalAlignment = HorizontalAlignment.Center;
textStamp.VerticalAlignment = VerticalAlignment.Bottom;

// 모든 페이지에 바닥글 추가
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(textStamp);
}
dataDir = dataDir + "TextinFooter_out.pdf";

// 업데이트된 PDF 파일을 저장하세요
pdfDocument.Save(dataDir);
Console.WriteLine("\nText in footer added successfully.\nFile saved at " + dataDir);

```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 문서의 바닥글에 텍스트를 추가하는 방법을 배웠습니다. 이제 PDF 문서에 추가 텍스트를 추가하여 바닥글을 사용자 지정할 수 있습니다.

### PDF 파일 바닥글의 텍스트에 대한 FAQ

#### 질문: PDF 문서의 바닥글에 텍스트를 추가하는 목적은 무엇입니까?

답변: PDF 문서의 바닥글에 텍스트를 추가하면 저작권 고지, 페이지 번호, 문서 버전 또는 각 페이지 하단에 일관되게 표시하려는 다른 텍스트와 같은 중요한 정보를 포함할 수 있습니다.

#### 질문: 제공된 C# 소스 코드를 사용해 PDF 문서의 바닥글에 텍스트를 추가하는 방법은 무엇인가요?

답변: 이 코드는 기존 PDF 문서를 열고, 원하는 바닥글 텍스트로 텍스트 스탬프를 만들고, 텍스트 속성을 사용자 지정하고, 모든 페이지에 텍스트 스탬프를 추가하고, 마지막으로 추가된 바닥글 텍스트로 업데이트된 PDF 문서를 저장하는 과정을 보여줍니다.

#### 질문: 바닥글 텍스트의 글꼴, 크기, 색상, 정렬 등을 수정할 수 있나요?

 A: 예, 바닥글 텍스트의 모양을 사용자 정의하려면 속성을 수정하면 됩니다.`TextStamp` 객체. 코드 예제에는 하단 여백, 수평 정렬 및 수직 정렬과 같은 속성 설정이 포함됩니다. 글꼴, 크기, 색상 및 기타 텍스트 관련 속성도 조정할 수 있습니다.

#### 질문: 각 페이지의 바닥글에 다른 텍스트를 추가할 수 있나요?

 A: 예, 별도로 만들어서 각 페이지의 바닥글에 다른 텍스트를 추가할 수 있습니다.`TextStamp` 다양한 텍스트 내용이나 속성을 가진 객체를 생성한 다음 필요에 따라 특정 페이지에 추가합니다.

#### 질문: PDF 문서의 모든 페이지에 바닥글 텍스트가 일관되게 표시되도록 하려면 어떻게 해야 하나요?

답변: PDF 문서의 모든 페이지를 반복하는 루프를 사용하고 각 페이지에 동일한 텍스트 스탬프를 추가하면 바닥글 텍스트가 모든 페이지에 일관되게 표시됩니다.

#### 질문: 여러 줄의 텍스트를 추가하거나, 바닥글 텍스트에 줄 바꿈을 적용할 수 있나요?

 A: 네, 텍스트 문자열에 줄 바꿈을 포함하여 푸터에 여러 줄의 텍스트를 추가할 수 있습니다. 예를 들어, 이스케이프 시퀀스를 사용할 수 있습니다.`\n` 텍스트에서 줄 바꿈을 나타냅니다.

#### 질문: 같은 PDF 문서의 머리글과 바닥글에 다른 내용을 추가하려면 어떻게 해야 하나요?

A: 헤더와 푸터 섹션에 다른 콘텐츠를 추가하려면 두 섹션에 대해 비슷한 단계를 따라야 합니다. 이 코드는 푸터에 텍스트를 추가하는 방법을 보여줍니다. 비슷한 접근 방식을 사용하여 헤더에 텍스트를 추가할 수 있습니다.

#### 질문: 이 방법을 사용하면 바닥글 텍스트와 함께 이미지나 다른 요소를 추가할 수 있나요?

A: 제공된 코드는 구체적으로 바닥글에 텍스트를 추가하는 방법을 보여주지만 Aspose.PDF 라이브러리를 사용하면 바닥글 섹션에 이미지, 선, 도형 또는 기타 콘텐츠와 같은 다른 요소를 추가하는 방식으로 접근 방식을 확장할 수 있습니다.