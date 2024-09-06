---
title: DOM 및 PDF 덮어쓰기를 사용하여 HTML 추가
linktitle: DOM을 사용하여 HTML 추가 및 덮어쓰기
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET에서 DOM과 PDF 덮어쓰기를 사용하여 HTML 콘텐츠를 추가하는 방법을 알아보세요.
type: docs
weight: 50
url: /ko/net/programming-with-text/add-html-using-dom-and-overwrite/
---
이 튜토리얼은 Aspose.PDF for .NET에서 DOM(Document Object Model)을 사용하여 HTML 콘텐츠를 추가하는 과정을 안내합니다. 또한 HTML 콘텐츠의 스타일을 덮어쓰는 방법도 알아봅니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구 사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio나 다른 C# 컴파일러가 설치되어 있어야 합니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새로운 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기
HTML 콘텐츠를 추가하려는 코드 파일에서 파일 맨 위에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉토리 및 출력 파일 경로 설정
 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리 경로를 포함합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 4단계: 새 문서 개체 만들기
 새로운 인스턴스화`Document` 다음 코드 줄을 추가하여 객체를 만듭니다.

```csharp
Document doc = new Document();
```

## 5단계: 문서에 페이지 추가
 문서에 새 페이지를 추가하려면 다음을 사용하세요.`Add` 의 방법`Pages`컬렉션. 제공된 코드에서 새 페이지는 변수에 할당됩니다.`page`.

```csharp
Page page = doc.Pages.Add();
```

## 6단계: HTML 콘텐츠로 HtmlFragment 만들기
 인스턴스화`HtmlFragment` 객체를 만들고 원하는 HTML 콘텐츠를 제공합니다. 제공된 코드에서 HTML 콘텐츠는 변수에 할당됩니다.`title`필요에 따라 HTML 콘텐츠를 수정할 수 있습니다.

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

## 7단계: HTML 콘텐츠의 스타일 덮어쓰기
 HTML 콘텐츠의 스타일을 덮어쓰려면 다음을 수정할 수 있습니다.`TextState` 의 속성`HtmlFragment` 객체. 제공된 코드에서 글꼴 패밀리는 "Arial"로 변경되고 글꼴 크기는 20으로 설정됩니다.

```csharp
title. TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

## 8단계: 여백 정보 설정
필요한 경우 HTML 조각의 하단 및 상단 여백을 조정합니다. 제공된 코드에서 하단 여백은 10으로 설정되고 상단 여백은 400으로 설정됩니다.

```csharp
title. Margin. Bottom = 10;
title. Margin. Top = 400;
```

## 9단계: 페이지에 HtmlFragment 추가
 추가하다`HtmlFragment` 페이지의 문단 컬렉션에 대한 이의 제기.

```csharp
page.Paragraphs.Add(title);
```

## 10단계: PDF 문서 저장
 PDF 문서를 저장하려면 다음을 사용하세요.`Save` 의 방법`Document` 객체. 3단계에서 설정한 출력 파일 경로를 지정하세요.

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 DOM을 사용하여 HTML을 추가하고 덮어쓰기 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Document 객체 인스턴스화
Document doc = new Document();
// PDF 파일의 페이지 컬렉션에 페이지 추가
Page page = doc.Pages.Add();
// HTML 콘텐츠로 HtmlFragment 인스턴스화
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
//'Verdana'의 글꼴 패밀리가 'Arial'로 재설정됩니다.
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
// 하단 여백 정보 설정
title.Margin.Bottom = 10;
// 상단 여백 정보 설정
title.Margin.Top = 400;
// 페이지의 문단 컬렉션에 HTML 조각 추가
page.Paragraphs.Add(title);
// PDF 파일 저장
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
// PDF 파일 저장
doc.Save(dataDir);
```

## 결론
Aspose.PDF for .NET에서 DOM을 사용하여 HTML 콘텐츠를 성공적으로 추가하고 HTML 콘텐츠의 스타일을 덮어썼습니다. 결과 PDF 파일은 이제 지정된 출력 파일 경로에서 찾을 수 있습니다.

### 자주 묻는 질문

#### 질문: 이 튜토리얼의 초점은 무엇인가요?

A: 이 튜토리얼은 Aspose.PDF for .NET에서 문서 개체 모델(DOM)을 사용하여 PDF 문서에 HTML 콘텐츠를 추가하는 과정을 안내하기 위해 설계되었습니다. 또한 HTML 콘텐츠의 스타일을 덮어쓰는 방법을 배우게 되며, 이를 통해 모양을 사용자 정의할 수 있습니다. 이 튜토리얼은 필요한 단계를 보여주는 C# 소스 코드 조각을 제공합니다.

#### 질문: 이 튜토리얼에서는 어떤 네임스페이스를 가져와야 하나요?

A: HTML 콘텐츠를 추가하려는 코드 파일에서 다음 네임스페이스를 파일 시작 부분에 가져옵니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### 질문: 문서 디렉토리와 출력 파일 경로를 어떻게 지정합니까?

 A: 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

#### 질문: Document 객체를 어떻게 만듭니까?

 A: 4단계에서는 새 인스턴스를 생성합니다.`Document` 다음 코드 줄을 사용하여 객체를 만듭니다.

```csharp
Document doc = new Document();
```

#### 질문: 문서에 페이지를 추가하려면 어떻게 해야 하나요?

 A: 5단계에서는 다음을 사용하여 문서에 새 페이지를 추가합니다.`Add` 의 방법`Pages` 수집:

```csharp
Page page = doc.Pages.Add();
```

#### 질문: DOM을 사용하여 HTML 콘텐츠를 어떻게 설정할 수 있나요?

 A: 6단계에서는 다음을 생성합니다.`HtmlFragment` 객체를 만들고 원하는 HTML 콘텐츠를 할당합니다. HTML 콘텐츠는 변수에 할당됩니다.`title`:

```csharp
HtmlFragment title = new HtmlFragment("<p style='font-family: Verdana'><b><i>Table contains text</i></b></p>");
```

#### 질문: HTML 콘텐츠의 스타일을 어떻게 덮어쓸 수 있나요?

 A: 7단계에서는 HTML 콘텐츠의 스타일을 수정하여 덮어씁니다.`TextState` 의 속성`HtmlFragment` 객체. 예를 들어, 글꼴 패밀리를 "Arial"로 변경하고 글꼴 크기를 20으로 설정할 수 있습니다.

```csharp
title.TextState = new TextState("Arial");
title.TextState.FontSize = 20;
```

#### 질문: HTML 콘텐츠의 여백을 조정할 수 있나요?

A: 네, 8단계에서 필요에 따라 HTML 조각의 아래쪽과 위쪽 여백을 조정할 수 있습니다.

```csharp
title.Margin.Bottom = 10;
title.Margin.Top = 400;
```

#### 질문: PDF 문서에 HtmlFragment를 추가하려면 어떻게 해야 하나요?

 A: 9단계에서는 다음을 추가합니다.`HtmlFragment` 물체 (`title`) 페이지의 문단 컬렉션으로:

```csharp
page.Paragraphs.Add(title);
```

#### 질문: 생성된 PDF 문서를 어떻게 저장하나요?

 A: HTML 콘텐츠를 추가하고 스타일을 사용자 지정한 후 다음을 사용합니다.`Save` 의 방법`Document` PDF 문서를 저장할 객체:

```csharp
dataDir = dataDir + "AddHTMLUsingDOMAndOverwrite_out.pdf";
doc.Save(dataDir);
```

#### 질문: 이 튜토리얼의 주요 내용은 무엇인가요?

A: 이 튜토리얼을 따라하면 Aspose.PDF for .NET에서 문서 개체 모델(DOM)을 사용하여 HTML 콘텐츠를 통합하는 방법을 성공적으로 배웠습니다. 또한 스타일을 덮어쓰고 결과 PDF 문서 내의 HTML 콘텐츠 모양을 조정하는 기능을 얻었습니다.