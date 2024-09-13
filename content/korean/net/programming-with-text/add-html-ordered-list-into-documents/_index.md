---
title: 문서에 HTML 정렬 목록 추가
linktitle: HTML 정렬 목록을 문서에 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 문서에 HTML 순서가 있는 목록을 추가하는 방법을 알아보세요.
type: docs
weight: 30
url: /ko/net/programming-with-text/add-html-ordered-list-into-documents/
---
이 튜토리얼에서는 Aspose.PDF for .NET 라이브러리를 사용하여 HTML 순서 목록을 문서에 추가하는 방법을 알아봅니다. 제공된 코드는 이 작업을 수행하는 데 필요한 단계를 보여줍니다.

## 요구 사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio나 다른 C# 컴파일러가 설치되어 있어야 합니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새로운 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기
HTML 정렬 목록을 추가하려는 코드 파일에서 다음 using 지시문을 파일 맨 위에 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉토리 및 출력 파일 경로 설정
 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리 경로를 포함합니다.

 다음으로, 다음과 같은 줄을 찾으세요.`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` 그리고 교체하다`"AddHTMLOrderedListIntoDocuments_out.pdf"` 원하는 출력 PDF 파일 이름을 입력합니다.

## 4단계: 새 문서 개체 만들기
 새로운 인스턴스화`Document` 다음 코드 줄을 추가하여 객체를 만듭니다.

```csharp
Document doc = new Document();
```

## 5단계: HTML 콘텐츠를 사용하여 HtmlFragment 개체 만들기
 인스턴스화`HtmlFragment` 문서에 추가하려는 HTML 콘텐츠가 있는 개체입니다. 제공된 코드에서 HTML 콘텐츠는 변수에 할당됩니다.`t`필요에 따라 HTML 콘텐츠를 수정할 수 있습니다.

```csharp
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li >Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
```

## 6단계: 문서에 페이지 추가
 문서에 새 페이지를 추가하려면 다음을 사용하세요.`Add` 의 방법`Pages` 컬렉션. 제공된 코드에서 새 페이지는 변수에 할당됩니다.`page`.

```csharp
Page page = doc.Pages.Add();
```

## 7단계: 페이지에 HtmlFragment 추가
 추가하다`HtmlFragment` 페이지에 대한 반대를 사용하여`Add` 의 방법`Paragraphs` 수집.

```csharp
page.Paragraphs.Add(t);
```

## 8단계: PDF 문서 저장
 결과 PDF 파일을 다음을 사용하여 저장합니다.`Save` 의 방법`Document` 객체. 3단계에서 설정한 출력 파일 경로를 지정하세요.

```csharp
doc.Save(outFile);
```

### .NET용 Aspose.PDF를 사용하여 문서에 HTML 정렬 목록을 추가하기 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 출력 문서의 경로입니다.
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
// Document 객체 인스턴스화
Document doc = new Document();
// 해당 HTML 조각으로 HtmlFragment 객체를 인스턴스화합니다.
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
// 페이지 컬렉션에 페이지 추가
Page page = doc.Pages.Add();
// 페이지 내부에 HtmlFragment 추가
page.Paragraphs.Add(t);
//결과 PDF 파일을 저장합니다
doc.Save(outFile);
```

## 결론
Aspose.PDF for .NET을 사용하여 HTML 정렬 목록을 문서에 성공적으로 추가했습니다. 결과 PDF 파일은 이제 지정된 출력 파일 경로에서 찾을 수 있습니다.

HTML 콘텐츠를 사용자 정의하고 특정 요구 사항에 맞게 코드를 조정하세요.

### 자주 묻는 질문

#### 질문: 이 튜토리얼의 목적은 무엇인가요?

A: 이 튜토리얼은 Aspose.PDF for .NET 라이브러리를 사용하여 HTML 순서 목록을 문서에 추가하는 과정을 안내합니다. 이 작업을 달성하는 데 도움이 되는 단계별 지침과 코드 조각을 제공합니다.

#### 질문: 이 튜토리얼에서는 어떤 네임스페이스를 가져와야 하나요?

A: 코드 파일의 맨 위에 다음 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### 질문: 문서 디렉토리와 출력 파일 경로를 어떻게 지정합니까?

 A: 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로와 함께. 또한 다음 줄을 찾으세요.`string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";` 그리고 교체하다`"AddHTMLOrderedListIntoDocuments_out.pdf"` 원하는 출력 PDF 파일 이름을 입력하세요.

#### 질문: 문서에 추가되는 HTML 콘텐츠를 사용자 정의할 수 있나요?

 A: 물론입니다! 5단계에서는 다음을 생성합니다.`HtmlFragment` 이름이 지정된 객체`t` HTML 콘텐츠를 보관합니다. 백틱 안에 있는 HTML 콘텐츠를 요구 사항에 맞게 수정할 수 있습니다.

#### 질문: 문서의 페이지에 HTML 순서 있는 목록을 추가하려면 어떻게 해야 하나요?

 A: 7단계에서는 다음을 추가합니다.`HtmlFragment` 물체 (`t` )를 사용하여 페이지로 이동`Add` 의 방법`Paragraphs` 컬렉션. 이렇게 하면 HTML 순서 목록을 문서에 원활하게 통합할 수 있습니다.

#### 질문: 생성된 PDF 문서를 어떻게 저장하나요?

 A: HTML 콘텐츠를 추가하고 페이지에 배열한 후에는 다음을 사용하여 PDF 문서를 저장할 수 있습니다.`Save` 의 방법`Document` 객체. 이전에 설정한 올바른 출력 파일 경로를 제공해야 합니다.

#### 질문: 참고할 수 있도록 샘플 소스 코드 요약을 제공해 주실 수 있나요?

A: 물론입니다! 이 튜토리얼에서 제공하는 샘플 소스 코드의 요약 버전은 다음과 같습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddHTMLOrderedListIntoDocuments_out.pdf";
Document doc = new Document();
HtmlFragment t = new HtmlFragment("`<body style='line-height: 100px;'><ul><li>First</li><li>Second</li><li>Third</li><li>Fourth</li><li>Fifth</li></ul>Text after the list.<br/>Next line<br/>Last line</body>`");
Page page = doc.Pages.Add();
page.Paragraphs.Add(t);
doc.Save(outFile);
```

#### 질문: 이 튜토리얼의 주요 내용은 무엇인가요?

A: 이 튜토리얼을 따라하면 Aspose.PDF for .NET 라이브러리를 활용하여 HTML 순서 목록을 문서에 통합하는 방법을 성공적으로 배웠습니다. 이 새롭게 얻은 지식은 문서 생성 및 조작 프로세스를 향상시키는 데 적용할 수 있습니다.