---
title: PDF 파일에서 텍스트와 이미지를 문단으로 사용
linktitle: PDF 파일에서 텍스트와 이미지를 문단으로 사용
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 텍스트와 이미지가 있는 PDF를 만듭니다. 텍스트와 인라인 이미지를 단계별로 추가하는 방법을 알아보세요.
type: docs
weight: 530
url: /ko/net/programming-with-text/text-and-image-as-paragraph/
---
## 소개

오늘날의 디지털 세계에서 PDF는 우리 대부분이 매일 접하는 보편적인 문서 형식입니다. 보고서, 전자책 또는 비즈니스 송장이든 PDF는 다양한 플랫폼에서 정보를 쉽게 공유할 수 있게 해줍니다. 하지만 PDF를 프로그래밍 방식으로 사용자 지정하고 싶다면 어떨까요? 바로 Aspose.PDF for .NET이 그 역할을 합니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 텍스트와 이미지를 인라인 문단으로 삽입하는 방법을 안내합니다.

## 필수 조건

코드를 살펴보기 전에, 순조롭게 따라갈 수 있도록 필요한 모든 것이 있는지 확인해 보겠습니다.

-  Aspose.PDF for .NET 라이브러리: Aspose.PDF for .NET을 설치해야 합니다. 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
- Visual Studio: .NET을 지원하는 모든 버전에서 작동합니다.
- C#에 대한 기본적인 이해: C#에 대해 어느 정도 알고 있으면 도움이 되지만 걱정하지 마세요. 모든 단계를 안내해 드리겠습니다!
- PDF 문서 준비: 사용자 정의 이미지를 추가하려면 미리 준비하세요.

 또한, 도서관의 무료 체험판을 받으실 수 있습니다.[여기](https://releases.aspose.com/) 또는 대규모 프로젝트를 진행 중이라면 구매를 고려하세요.[여기](https://purchase.aspose.com/buy) . 더 자세한 정보가 필요하세요? 설명서를 확인하세요[여기](https://reference.aspose.com/pdf/net/).

## 패키지 가져오기

Aspose.PDF for .NET을 시작하려면 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스를 사용하면 C# 코드가 Aspose.PDF 기능과 상호 작용할 수 있습니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
using System;
```

간단하죠? 이제 재밌는 부분으로 들어가 봅시다. 나만의 PDF 파일을 만드는 것입니다.

## 단계별 가이드: 텍스트와 인라인 이미지가 있는 PDF 만들기

이것을 소화하기 쉬운, 따라하기 쉬운 단계로 나누어 보겠습니다. 퍼즐을 조립한다고 상상해 보세요. 각 단계는 올바른 조각을 찾아 놓는 것과 같습니다.

## 1단계: PDF 문서 초기화

첫 번째 단계는 Aspose.PDF를 사용하여 새 PDF 문서를 초기화하는 것입니다. 이 문서는 텍스트와 이미지를 추가하는 기초가 됩니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스화
Document doc = new Document();
```

 여기서 무슨 일이 일어나고 있습니까? 우리는 단순히 다음을 사용하여 새 문서를 만들고 있습니다.`Document`클래스와 PDF를 저장할 디렉토리를 정의합니다. 마치 걸작을 위한 새로운 캔버스를 여는 것과 같습니다!

## 2단계: PDF에 페이지 추가

페이지가 없으면 문서는 별로 쓸모가 없잖아요, 그렇죠? 문서에 빈 페이지를 추가해 봅시다.

```csharp
// Document 인스턴스의 pages 컬렉션에 페이지 추가
Page page = doc.Pages.Add();
```

이 코드 조각은 문서의 페이지 컬렉션에 새 페이지를 추가합니다. 노트북의 빈 페이지를 펼치는 것처럼 생각하세요.

## 3단계: 텍스트를 문단으로 추가

다음으로, 텍스트 문단을 추가하겠습니다. 여기에 메시지나 제목을 삽입할 수 있습니다.

```csharp
// TextFragment 생성
TextFragment text = new TextFragment("Hello World.. ");
// Page 객체의 문단 컬렉션에 텍스트 조각 추가
page.Paragraphs.Add(text);
```

 여기서 우리는 다음을 생성합니다.`TextFragment` 객체는 "Hello World.."라는 텍스트를 보관하고, 그 텍스트는 페이지에 단락으로 추가됩니다. PDF 문서의 첫 문장을 쓰는 것과 같습니다.

## 4단계: 인라인 문단으로 이미지 추가

이제 텍스트가 있으니 이미지를 인라인 문단으로 추가하여 좀 더 흥미진진하게 만들어 보겠습니다. 인라인 문단은 이미지가 Word 문서에 표시되는 방식과 매우 비슷하게 텍스트 바로 뒤에 나타난다는 것을 의미합니다.

```csharp
// 이미지 인스턴스 생성
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// 이미지를 인라인 문단으로 설정하여 바로 뒤에 나타나도록 합니다.
// 이전 문단 객체(TextFragment)
image.IsInLineParagraph = true;
// 이미지 파일 경로를 지정하세요
image.File = dataDir + "aspose-logo.jpg";
```

 이 스니펫에서는 다음을 생성합니다.`Image` 객체에 텍스트와 일렬로 정렬하도록 지정하고 이미지 파일의 경로를 지정합니다. 이는 문서의 문장 바로 뒤에 이미지를 붙여넣는 것과 같습니다. "aspose-logo.jpg"를 원하는 이미지로 바꿀 수 있습니다.

## 5단계: 이미지 크기 설정(선택 사항)

이미지 크기를 조정하고 싶으신가요? 문제 없습니다. Aspose.PDF는 문서에 추가하기 전에 이미지의 높이와 너비를 조정할 수 있는 옵션을 제공합니다.

```csharp
// 이미지 높이 설정(선택 사항)
image.FixHeight = 30;
// 이미지 너비 설정(선택 사항)
image.FixWidth = 100;
```

이 부분은 선택 사항이지만, PDF에 이미지가 얼마나 크거나 작게 나타나는지 제어하는 데 도움이 됩니다. 인쇄하기 전에 사진 크기를 조정하는 것과 같습니다.

## 6단계: 문단 컬렉션에 이미지 추가

이미지를 준비했습니다. 이제 문서에 인라인 문단으로 삽입해 보겠습니다.

```csharp
// 페이지 객체의 문단 컬렉션에 이미지 추가
page.Paragraphs.Add(image);
```

이 줄은 문단 컬렉션의 텍스트 바로 뒤에 이미지를 추가합니다. 텍스트 편집기에서 "이미지 삽입" 버튼을 누르는 것과 같습니다.

## 7단계: 다른 인라인 텍스트 문단 추가

이미지 바로 뒤에 더 많은 텍스트를 추가하고 싶다면 어떻게 할까요? 다른 인라인 텍스트 조각을 삽입해 보겠습니다.

```csharp
// 다른 내용으로 TextFragment 객체를 다시 초기화합니다.
text = new TextFragment(" Hello Again..");
// TextFragment를 인라인 문단으로 설정
text.IsInLineParagraph = true;
// 새로 생성된 TextFragment를 페이지의 문단 컬렉션에 추가합니다.
page.Paragraphs.Add(text);
```

 우리는 재사용하고 있습니다`TextFragment`여기에 새 텍스트("Hello Again..")를 사용하여 객체를 만들고 이미지 바로 뒤에 인라인으로 삽입합니다. 이렇게 하면 PDF가 흐르고 응집력 있는 모양이 됩니다.

## 8단계: PDF 문서 저장

거의 다 됐어요! 이제 문서를 지정된 디렉토리에 저장해 봅시다.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as inline paragraphs.\nFile saved at " + dataDir);
```

이 마지막 단계는 "TextAndImageAsParagraph_out.pdf"라는 이름으로 디렉토리에 파일을 저장합니다. 축하합니다. 텍스트와 인라인 이미지가 모두 포함된 PDF를 만들었습니다!

## 결론

이제 Aspose.PDF for .NET을 사용하여 텍스트와 이미지를 인라인 문단으로 포함하는 PDF를 만드는 것은 다음 단계를 따르는 것만큼 간단합니다. 몇 줄의 코드만 있으면 PDF 파일에 동적 콘텐츠를 추가하여 시각적으로 매력적이고 전문적으로 만들 수 있습니다. 비즈니스 보고서든 전자책이든 PDF의 레이아웃을 제어하면 큰 차이를 만들 수 있습니다.

## 자주 묻는 질문

### 여러 개의 이미지를 인라인 문단으로 추가할 수 있나요?  
 네, 별도로 생성하여 여러 이미지를 추가할 수 있습니다.`Image` 객체를 사용하여 문단 컬렉션에 추가합니다.

### PDF에서 텍스트와 이미지의 위치를 제어할 수 있나요?  
네, 여백과 같은 속성을 사용하면 텍스트와 이미지의 정확한 위치를 제어할 수 있습니다.

### .NET용 Aspose.PDF는 무료인가요?  
 아니요, 라이센스 제품이지만 다음을 얻을 수 있습니다.[무료 체험](https://releases.aspose.com/) 또는 라이센스를 구매하세요[여기](https://purchase.aspose.com/buy).

### 텍스트에 하이퍼링크를 추가할 수 있나요?  
 네, Aspose.PDF를 사용하면 텍스트 조각 내에 하이퍼링크를 추가할 수 있습니다.[선적 서류 비치](https://reference.aspose.com/pdf/net/) 자세한 내용은.

### 텍스트의 글꼴과 스타일을 사용자 지정할 수 있나요?  
물론입니다! 텍스트 조각의 글꼴, 색상 및 기타 스타일 속성을 쉽게 사용자 지정할 수 있습니다.