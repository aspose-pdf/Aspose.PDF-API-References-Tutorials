---
title: PDF 파일에 하이퍼링크 추가
linktitle: PDF 파일에 하이퍼링크 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 대화형 하이퍼링크를 쉽게 추가하세요.
type: docs
weight: 10
url: /ko/net/programming-with-links-and-actions/add-hyperlink/
---
PDF 파일에 하이퍼링크를 추가하면 문서의 다른 페이지, 웹 사이트 또는 대상에 대한 대화형 하이퍼링크를 만들 수 있습니다. .NET용 Aspose.PDF를 사용하면 다음 소스 코드에 따라 하이퍼링크를 쉽게 추가할 수 있습니다.

## 1단계: 필수 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 import 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
```

## 2단계: 문서 폴더 경로 설정

이 단계에서는 하이퍼링크를 추가하려는 PDF 파일이 포함된 폴더의 경로를 지정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"`다음 코드에 문서 폴더의 실제 경로를 입력하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 3단계: PDF 문서 열기

이제 다음 코드를 사용하여 하이퍼링크를 추가하려는 PDF 문서를 엽니다.

```csharp
Document document = new Document(dataDir + "AddHyperlink.pdf");
```

## 4단계: 링크 만들기

 이 단계에서는 다음을 사용하여 하이퍼링크를 만듭니다.`LinkAnnotation` 주석. 당사는 링크의 연락처 및 영역, 링크 유형 및 링크 내용을 명시합니다. 해당 코드는 다음과 같습니다.

```csharp
Page page = document.Pages[1];
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
Border border = new Border(link);
border. Width = 0;
link. Border = border;
link. Action = new GoToURIAction("www.aspose.com");
page.Annotations.Add(link);
```

## 5단계: 추가 텍스트 추가

 하이퍼링크 외에도 다음을 사용하여 추가 텍스트를 추가할 수도 있습니다.`FreeTextAnnotation` 주석. 좌표, 텍스트 모양 및 텍스트 내용을 지정합니다. 해당 코드는 다음과 같습니다.

```csharp
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System .Drawing.Color.Blue));
textAnnotation.Contents = "Link to Aspose website";
textAnnotation. Border = border;
document.Pages[1].Annotations.Add(textAnnotation);
```

## 6단계: 업데이트된 파일 저장

 이제 다음을 사용하여 업데이트된 PDF 파일을 저장해 보겠습니다.`Save` 의 방법`document` 물체. 해당 코드는 다음과 같습니다.

```csharp
dataDir = dataDir + "AddHyperlink_out.pdf";
document. Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 하이퍼링크 추가에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document document = new Document(dataDir + "AddHyperlink.pdf");
// 링크 만들기
Page page = document.Pages[1];
// 링크 주석 객체 생성
LinkAnnotation link = new LinkAnnotation(page, new Aspose.Pdf.Rectangle(100, 100, 300, 300));
// LinkAnnotation에 대한 테두리 객체 생성
Border border = new Border(link);
// 테두리 너비 값을 0으로 설정
border.Width = 0;
// LinkAnnotation의 테두리 설정
link.Border = border;
// 링크 유형을 원격 URI로 지정
link.Action = new GoToURIAction("www.aspose.com");
//PDF 파일 첫 페이지의 주석 컬렉션에 링크 주석 추가
page.Annotations.Add(link);
// 자유 텍스트 주석 생성
FreeTextAnnotation textAnnotation = new FreeTextAnnotation(document.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), new DefaultAppearance(Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman"), 10, System.Drawing.Color.Blue));
// 자유 텍스트로 추가할 문자열
textAnnotation.Contents = "Link to Aspose website";
// 자유 텍스트 주석의 테두리 설정
textAnnotation.Border = border;
// 문서 첫 페이지의 주석 모음에 FreeText 주석 추가
document.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddHyperlink_out.pdf";
// 업데이트된 문서 저장
document.Save(dataDir);
Console.WriteLine("\nHyperlink added successfully.\nFile saved at " + dataDir);            
```

## 결론

축하합니다! 이제 .NET용 Aspose.PDF를 사용하여 하이퍼링크를 추가하는 단계별 가이드가 제공됩니다. 이 코드를 사용하여 PDF 문서에 대화형 링크를 만들 수 있습니다.

### PDF 파일에 하이퍼링크 추가에 대한 FAQ

#### 질문: 내 PDF 파일에 하이퍼링크 추가를 고려해야 하는 이유는 무엇입니까?

A: PDF 파일에 하이퍼링크를 추가하면 독자가 문서 내의 다른 페이지, 웹 사이트 또는 대상으로 쉽게 이동할 수 있으므로 사용자 경험이 향상됩니다. 추가 리소스나 관련 정보에 액세스할 수 있는 원활한 방법을 제공합니다.

#### Q: Aspose.PDF for .NET은 초보자에게 적합합니까?

A: 예, .NET용 Aspose.PDF는 초보자에게 친숙합니다. 이 가이드에 제공된 단계별 튜토리얼은 PDF 파일에 하이퍼링크를 추가하는 과정을 단순화하여 다양한 기술 수준의 개발자가 액세스할 수 있도록 해줍니다.

#### Q: 하이퍼링크의 모양을 사용자 정의할 수 있습니까?

답: 물론이죠! .NET용 Aspose.PDF는 텍스트 색상, 스타일 및 서식을 포함하여 하이퍼링크 모양에 대한 사용자 정의 옵션을 제공합니다. 이를 통해 하이퍼링크를 문서의 전체 디자인과 일치시킬 수 있습니다.

#### Q: 모든 유형의 PDF 문서에서 하이퍼링크가 지원됩니까?

A: 예, 텍스트 기반 문서, 이미지, 멀티미디어 기능이 풍부한 파일을 비롯한 다양한 유형의 PDF 문서에 하이퍼링크를 추가할 수 있습니다. .NET용 Aspose.PDF는 하이퍼링크가 다양한 PDF 형식에서 작동하도록 보장합니다.

#### Q: Aspose.PDF for .NET은 어떤 다른 기능을 제공합니까?

A: .NET용 Aspose.PDF는 PDF 생성, 조작, 변환 및 추출을 포함한 광범위한 기능을 제공하는 강력한 라이브러리입니다. 텍스트, 이미지, 주석 등의 작업을 지원하므로 PDF 관련 작업을 위한 다목적 도구입니다.

#### Q: 문서 내의 특정 섹션에 하이퍼링크를 추가할 수 있습니까?

 A: 네,`LinkAnnotation` 주석을 사용하면 사용자를 PDF 문서 내의 특정 섹션으로 안내하는 하이퍼링크를 만들 수 있습니다. 이 기능은 대화형 목차나 참조 링크를 만드는 데 특히 유용합니다.

#### Q: PDF 파일에 하이퍼링크를 추가하는 데 제한이 있나요?

A: .NET용 Aspose.PDF는 포괄적인 하이퍼링크 기능을 제공하지만 링크된 콘텐츠에 액세스할 수 있고 최신 상태로 유지하는 것이 중요합니다. 링크가 끊어지지 않도록 외부 웹사이트에 대한 하이퍼링크를 정기적으로 확인해야 합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 외부 파일에 대한 하이퍼링크를 만들 수 있습니까?

A: 예, 웹 URL 외에도 다른 PDF 문서, 이미지 또는 멀티미디어 파일과 같은 외부 파일로 연결되는 하이퍼링크를 생성할 수 있습니다. .NET용 Aspose.PDF는 다양한 유형의 리소스에 연결할 수 있는 유연성을 제공합니다.