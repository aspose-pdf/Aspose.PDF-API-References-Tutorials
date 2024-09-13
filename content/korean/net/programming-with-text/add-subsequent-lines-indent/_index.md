---
title: PDF 파일에 후속 줄 들여쓰기 추가
linktitle: PDF 파일에 후속 줄 들여쓰기 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 텍스트에 후속 줄 들여쓰기를 추가하는 방법을 알아보세요.
type: docs
weight: 60
url: /ko/net/programming-with-text/add-subsequent-lines-indent/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일의 텍스트에 후속 줄 들여쓰기를 추가하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구 사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio나 다른 C# 컴파일러가 설치되어 있어야 합니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새로운 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기
후속 줄 들여쓰기를 추가하려는 코드 파일에서 다음 using 지시문을 파일 맨 위에 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 3단계: 문서 디렉토리 설정
 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리 경로를 포함합니다.

## 4단계: 새 문서 개체 만들기
 새로운 인스턴스화`Document` 다음 코드 줄을 추가하여 객체를 만듭니다.

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

## 5단계: 문서에 페이지 추가
 문서에 새 페이지를 추가하려면 다음을 사용하세요.`Add` 의 방법`Pages` 컬렉션. 제공된 코드에서 새 페이지는 변수에 할당됩니다.`page`.

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

## 6단계: 후속 줄 들여쓰기가 있는 TextFragment 만들기
 인스턴스화`TextFragment` 객체를 만들고 원하는 텍스트를 제공합니다. 제공된 코드에서 텍스트는 변수에 할당됩니다.`text` . 그런 다음 초기화합니다.`TextFormattingOptions` 를 위해`TextFragment` 그리고 지정하세요`SubsequentLinesIndent` 값.

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog." );
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
     SubsequentLinesIndent = 20
};
```

## 7단계: 페이지에 TextFragment 추가
 추가하다`TextFragment` 페이지의 문단 컬렉션에 대한 이의 제기.

```csharp
page.Paragraphs.Add(text);
```

## 8단계: 추가 줄에 대해 6단계와 7단계를 반복합니다.
같은 들여쓰기로 후속 줄을 추가하려면 각 줄에 대해 6단계와 7단계를 반복합니다. 필요에 따라 텍스트 내용을 업데이트합니다.

```csharp
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
```

## 9단계: PDF 문서 저장
 PDF 문서를 저장하려면 다음을 사용하세요.`Save` 의 방법`Document` 객체. 출력 파일 경로를 지정하세요.

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### .NET용 Aspose.PDF를 사용하여 후속 줄 들여쓰기 추가를 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 새 문서 객체 생성
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
Aspose.Pdf.Page page = document.Pages.Add();
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog. A quick brown fox jumped over the lazy dog.");
//텍스트 조각에 대한 TextFormattingOptions를 초기화하고 subsequentlyLinesIndent 값을 지정합니다.
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
	SubsequentLinesIndent = 20
};
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line2");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line3");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line4");
page.Paragraphs.Add(text);
text = new Aspose.Pdf.Text.TextFragment("Line5");
page.Paragraphs.Add(text);
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 결론
Aspose.PDF for .NET을 사용하여 텍스트에 후속 줄 들여쓰기를 성공적으로 추가했습니다. 결과 PDF 파일은 이제 지정된 출력 파일 경로에서 찾을 수 있습니다.

### 자주 묻는 질문

#### 질문: 이 튜토리얼의 초점은 무엇인가요?

A: 이 튜토리얼은 Aspose.PDF for .NET 라이브러리를 사용하여 PDF 파일의 텍스트에 후속 줄 들여쓰기를 추가하는 방법에 대한 포괄적인 가이드를 제공합니다. 여기에는 이를 달성하는 데 필요한 단계를 설명하는 C# 소스 코드 예제가 포함되어 있습니다.

#### 질문: 이 튜토리얼에서는 어떤 네임스페이스를 가져와야 하나요?

A: 후속 줄 들여쓰기를 추가하려는 코드 파일에서 다음 네임스페이스를 파일 시작 부분에 가져옵니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### 질문: 문서 디렉토리를 어떻게 지정하나요?

 A: 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

#### 질문: Document 객체를 어떻게 만듭니까?

 A: 4단계에서는 새 인스턴스를 생성합니다.`Document` 다음 코드 줄을 사용하여 객체를 만듭니다.

```csharp
Aspose.Pdf.Document document = new Aspose.Pdf.Document();
```

#### 질문: 문서에 페이지를 추가하려면 어떻게 해야 하나요?

 A: 5단계에서는 다음을 사용하여 문서에 새 페이지를 추가합니다.`Add` 의 방법`Pages` 수집:

```csharp
Aspose.Pdf.Page page = document.Pages.Add();
```

#### 질문: 텍스트에 다음 줄 들여쓰기를 추가하려면 어떻게 해야 하나요?

 A: 6단계에서는 다음을 생성합니다.`TextFragment` 객체를 만들고 원하는 텍스트를 할당합니다. 그런 다음 초기화합니다.`TextFormattingOptions` 를 위해`TextFragment` 그리고 지정하세요`SubsequentLinesIndent` 값:

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("Your text here");
text.TextState.FormattingOptions = new Aspose.Pdf.Text.TextFormattingOptions()
{
    SubsequentLinesIndent = 20
};
```

#### 질문: PDF 문서에 TextFragment를 추가하려면 어떻게 해야 하나요?

 A: 7단계에서는 다음을 추가합니다.`TextFragment` 물체 (`text`) 페이지의 문단 컬렉션으로:

```csharp
page.Paragraphs.Add(text);
```

#### 질문: 추가 회선에 대해서도 이 과정을 반복할 수 있나요?

A: 예, 8단계에서 새 줄을 만들어 같은 들여쓰기를 가진 추가 줄에 대해 프로세스를 반복할 수 있습니다.`TextFragment` 객체를 추가하여 페이지의 문단 컬렉션에 추가합니다.

#### 질문: 생성된 PDF 문서를 어떻게 저장하나요?

 A: 다음 줄에 들여쓰기를 적용한 텍스트를 추가한 후 다음을 사용합니다.`Save` 의 방법`Document` PDF 문서를 저장할 객체:

```csharp
document.Save(dataDir + "SubsequentIndent_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

#### 질문: 이 튜토리얼의 주요 내용은 무엇인가요?

A: 이 튜토리얼을 따라가면 Aspose.PDF for .NET을 사용하여 후속 줄 들여쓰기를 추가하여 PDF 문서의 텍스트 가독성을 향상시키는 방법을 성공적으로 배웠습니다. 이 기술은 다양한 유형의 문서와 보고서에 유용할 수 있습니다.