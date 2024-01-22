---
title: PDF 파일의 단락으로 텍스트 및 이미지
linktitle: PDF 파일의 단락으로 텍스트 및 이미지
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 텍스트와 이미지를 인라인 단락으로 추가하는 방법을 알아보세요.
type: docs
weight: 530
url: /ko/net/programming-with-text/text-and-image-as-paragraph/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 텍스트와 이미지를 인라인 단락으로 추가하는 방법을 설명합니다. 제공된 C# 소스 코드는 프로세스를 단계별로 보여줍니다.

## 전제조건

튜토리얼을 진행하기 전에 다음 사항을 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- .NET 라이브러리용 Aspose.PDF가 설치되었습니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

## 1단계: 프로젝트 설정

선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 생성하고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하는 것으로 시작하세요.

## 2단계: 필요한 네임스페이스 가져오기

필수 네임스페이스를 가져오려면 C# 파일 시작 부분에 다음 using 지시문을 추가하세요.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Drawing;
```

## 3단계: 문서 디렉터리 경로 설정

 다음을 사용하여 문서 디렉토리의 경로를 설정하십시오.`dataDir` 변하기 쉬운:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

## 4단계: 새 문서 및 페이지 만들기

 새로 만들기`Document` 개체를 만들고 해당 페이지 컬렉션에 페이지를 추가합니다.

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 5단계: TextFragment를 만들고 단락으로 추가

 만들기`TextFragment` 개체를 만들어 페이지의 단락 컬렉션에 추가합니다.

```csharp
TextFragment text = new TextFragment("Hello World.. ");
page.Paragraphs.Add(text);
```

## 6단계: 이미지를 인라인 단락으로 추가

 만들기`Aspose.Pdf.Image` 개체를 삭제하고 이전 단락 바로 뒤에 나타나도록 인라인 단락으로 설정합니다.

```csharp
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
image.IsInLineParagraph = true;
image.File = dataDir + "aspose-logo.jpg";
image.FixHeight = 30; // 선택사항: 이미지 높이 설정
image.FixWidth = 100; // 선택사항: 이미지 너비 설정
page.Paragraphs.Add(image);
```

 바꾸다`"aspose-logo.jpg"` 실제 이미지 파일 이름을 사용하고 선택적 이미지 높이와 너비를 원하는 대로 조정합니다.

## 7단계: 다른 TextFragment를 인라인 단락으로 추가

 다시 초기화하세요.`TextFragment` 다른 내용을 가진 객체를 인라인 단락으로 추가합니다.

```csharp
text = new TextFragment(" Hello Again..");
text.IsInLineParagraph = true;
page.Paragraphs.Add(text);
```

## 8단계: PDF 문서 저장

수정된 PDF 문서를 저장합니다.

```csharp
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
```

 꼭 교체하세요`"TextAndImageAsParagraph_out.pdf"` 원하는 출력 파일 이름으로.

### .NET용 Aspose.PDF를 사용하여 단락으로 텍스트 및 이미지를 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 인스턴스 인스턴스화
Document doc = new Document();
// Document 인스턴스의 페이지 컬렉션에 페이지 추가
Page page = doc.Pages.Add();
// TextFragmnet 만들기
TextFragment text = new TextFragment("Hello World.. ");
// 페이지 개체의 단락 컬렉션에 텍스트 조각 추가
page.Paragraphs.Add(text);
// 이미지 인스턴스 만들기
Aspose.Pdf.Image image = new Aspose.Pdf.Image();
// 바로 뒤에 표시되도록 이미지를 인라인 단락으로 설정
// 이전 단락 객체(TextFragment)
image.IsInLineParagraph = true;
// 이미지 파일 경로 지정
image.File = dataDir + "aspose-logo.jpg";
// 이미지 높이 설정(선택 사항)
image.FixHeight = 30;
// 이미지 너비 설정(선택 사항)
image.FixWidth = 100;
// 페이지 개체의 단락 컬렉션에 이미지 추가
page.Paragraphs.Add(image);
// 다른 내용으로 TextFragment 객체를 다시 초기화합니다.
text = new TextFragment(" Hello Again..");
// TextFragment를 인라인 단락으로 설정
text.IsInLineParagraph = true;
// 페이지의 단락 컬렉션에 새로 생성된 TextFragment를 추가합니다.
page.Paragraphs.Add(text);
dataDir = dataDir + "TextAndImageAsParagraph_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nText and image added successfully as an inline paragraphs.\nFile saved at " + dataDir);
```

## 결론

축하해요! .NET용 Aspose.PDF를 사용하여 PDF 문서에 텍스트와 이미지를 인라인 단락으로 추가하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 프로젝트 설정부터 수정된 문서 저장까지 단계별 가이드를 제공했습니다. 이제 이 코드를 자신의 C# 프로젝트에 통합하여 PDF 파일의 텍스트 및 이미지 레이아웃을 사용자 지정할 수 있습니다.

### FAQ

#### Q: "PDF 파일의 단락으로 텍스트 및 이미지" 튜토리얼의 목적은 무엇입니까?

A: "PDF 파일의 단락으로 텍스트 및 이미지" 튜토리얼의 목적은 .NET용 Aspose.PDF를 사용하여 PDF 문서 내에서 텍스트와 이미지를 인라인 단락으로 추가하는 방법을 사용자에게 안내하는 것입니다. 이 자습서에서는 프로세스를 보여주기 위한 단계별 지침과 C# 코드 샘플을 제공합니다.

#### Q: 이 튜토리얼은 텍스트와 이미지를 인라인 단락으로 추가하는 데 어떻게 도움이 됩니까?

A: 이 튜토리얼은 사용자가 .NET용 Aspose.PDF를 사용하여 PDF 문서 내의 인라인 단락으로 텍스트와 이미지를 모두 통합하는 방법을 이해하는 데 도움이 됩니다. 제공된 단계와 코드 예제를 따르면 사용자는 텍스트와 이미지를 결합한 사용자 정의 레이아웃이 포함된 PDF 파일을 만들 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 어떤 전제 조건이 필요합니까?

A: 자습서를 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있어야 합니다. 또한 .NET용 Aspose.PDF 라이브러리가 설치되어 있어야 합니다. Aspose 웹사이트에서 얻거나 NuGet을 사용하여 프로젝트에 설치할 수 있습니다.

#### Q: 이 튜토리얼을 따르려면 프로젝트를 어떻게 설정해야 합니까?

A: 시작하려면 선호하는 IDE(통합 개발 환경)에서 새 C# 프로젝트를 만들고 .NET용 Aspose.PDF 라이브러리에 대한 참조를 추가하세요. 이를 통해 PDF 문서, 텍스트 조각 및 이미지 작업에 라이브러리 기능을 활용할 수 있습니다.

#### 질문: 이 튜토리얼을 사용하여 PDF에 여러 텍스트 및 이미지 단락을 추가할 수 있습니까?

A: 예, 제공된 코드 샘플을 사용하여 동일한 PDF 문서 내에서 텍스트 및 이미지 단락의 여러 인스턴스를 추가할 수 있습니다. 이 튜토리얼에서는 인라인 단락을 만들어 텍스트와 이미지의 다양한 조합을 쉽게 포함하는 방법을 보여줍니다.

#### Q: 텍스트 단락과 이미지의 내용과 모양을 어떻게 지정합니까?

 A: 튜토리얼에서는 다음을 생성하는 방법을 보여줍니다.`TextFragment`텍스트 단락을 나타내는 개체 및`Aspose.Pdf.Image` 이미지를 표현하는 객체. 제공된 코드 샘플을 사용하여 텍스트와 이미지의 내용, 크기 및 모양을 사용자 정의할 수 있습니다.

#### Q: 인라인 단락의 레이아웃을 조정할 수 있나요?

 A: 예, 페이지 내 위치, 크기 및 순서를 제어하여 인라인 단락의 레이아웃을 조정할 수 있습니다. 튜토리얼에서는 다음과 같은 인라인 속성을 설정하는 방법을 보여줍니다.`IsInLineParagraph`, 텍스트 및 이미지 단락의 레이아웃을 제어합니다.

#### Q: 수정된 PDF 문서를 어떻게 저장합니까?

 A: 수정된 PDF 문서를 저장하려면`Save` 의 방법`Document` 물체. 이 튜토리얼에서는 결과 PDF 문서를 저장하는 방법을 보여주는 코드 샘플을 제공합니다.