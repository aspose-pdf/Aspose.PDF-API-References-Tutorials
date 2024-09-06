---
title: PDF 파일에서 페이지 영역에서 텍스트 추출
linktitle: PDF 파일에서 페이지 영역에서 텍스트 추출
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일의 특정 페이지에서 텍스트를 추출하는 방법을 알아보세요.
type: docs
weight: 190
url: /ko/net/programming-with-text/extract-text-from-page-region/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일의 특정 영역에서 텍스트를 추출하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구 사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio나 다른 C# 컴파일러가 설치되어 있어야 합니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새로운 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필요한 네임스페이스 가져오기
텍스트를 추출하려는 코드 파일에서 다음 using 지시문을 파일 맨 위에 추가합니다.

```csharp
using Aspose.Pdf;
using System.IO;
```

## 3단계: 문서 디렉토리 설정
 코드에서 다음 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 그리고 교체하다`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리 경로를 포함합니다.

## 4단계: PDF 문서 열기
 기존 PDF 문서를 열려면 다음을 사용하세요.`Document` 생성자를 사용하고 입력 PDF 파일의 경로를 전달합니다.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## 5단계: 페이지 영역에서 텍스트 추출
 생성하다`TextAbsorber` 문서에서 텍스트를 추출하는 개체입니다. 구성`TextSearchOptions` 사각형으로 정의된 특정 페이지 영역으로 검색을 제한합니다.

```csharp
TextAbsorber absorb = new TextAbsorber();
absorb.TextSearchOptions.LimitToPageBounds = true;
absorb.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
pdfDocument.Pages[1].Accept(absorb);
```

## 6단계: 추출된 텍스트 가져오기
 추출된 텍스트에 액세스하세요`TextAbsorber` 물체.

```csharp
string extractedText = absorb.Text;
```

## 7단계: 추출된 텍스트 저장
 생성하다`TextWriter` 추출된 텍스트를 저장할 파일을 엽니다. 추출된 텍스트를 파일에 쓰고 스트림을 닫습니다.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### .NET용 Aspose.PDF를 사용하여 페이지 영역에서 텍스트 추출을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// 텍스트를 추출하기 위해 TextAbsorber 객체를 생성합니다.
TextAbsorber absorber = new TextAbsorber();
absorber.TextSearchOptions.LimitToPageBounds = true;
absorber.TextSearchOptions.Rectangle = new Aspose.Pdf.Rectangle(100, 200, 250, 350);
// 첫 번째 페이지에 흡수체를 수용합니다.
pdfDocument.Pages[1].Accept(absorber);
// 추출된 텍스트를 가져옵니다
string extractedText = absorber.Text;
// 작성자를 생성하고 파일을 엽니다.
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// 파일에 텍스트 한 줄을 쓰세요
tw.WriteLine(extractedText);
// 스트림을 닫습니다
tw.Close();
```

## 결론
Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지에서 특정 영역의 텍스트를 성공적으로 추출했습니다. 추출된 텍스트는 지정된 출력 파일에 저장되었습니다.

### 자주 묻는 질문

#### 질문: 이 튜토리얼의 목적은 무엇인가요?

A: 이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일의 특정 영역에서 텍스트를 추출하는 과정을 안내합니다. 첨부된 C# 소스 코드는 이 작업을 완료하기 위한 단계별 지침을 제공합니다.

#### 질문: 어떤 네임스페이스를 가져와야 합니까?

A: 텍스트를 추출하려는 코드 파일에서 파일 시작 부분에 다음 using 지시문을 포함하세요.

```csharp
using Aspose.Pdf;
using System.IO;
```

#### 질문: 문서 디렉토리를 어떻게 지정하나요?

 A: 라인을 찾으세요`string dataDir = "YOUR DOCUMENT DIRECTORY";` 코드에서 교체`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 포함합니다.

#### 질문: 기존 PDF 문서를 어떻게 열 수 있나요?

 A: 4단계에서는 다음을 사용하여 기존 PDF 문서를 엽니다.`Document` 생성자를 사용하고 입력 PDF 파일에 대한 경로를 제공합니다.

#### 질문: 특정 페이지 영역에서 텍스트를 추출하려면 어떻게 해야 하나요?

 A: 5단계에는 다음을 만드는 것이 포함됩니다.`TextAbsorber`PDF 문서에서 텍스트를 추출하는 개체입니다. 그런 다음 다음을 구성합니다.`TextSearchOptions` 좌표를 사용하여 페이지에서 특정 직사각형 영역을 정의합니다.

#### 질문: 추출된 텍스트에 어떻게 접근하나요?

 A: 6단계에서는 추출된 텍스트에 액세스하는 방법을 안내합니다.`TextAbsorber` 물체.

#### 질문: 추출한 텍스트를 파일로 저장하려면 어떻게 해야 하나요?

 A: 7단계에서는 다음을 생성합니다.`TextWriter`, 추출된 텍스트를 저장할 파일을 열고, 추출된 텍스트를 파일에 쓴 다음 스트림을 닫습니다.

#### 질문: 이 튜토리얼의 주요 내용은 무엇인가요?

A: 이 튜토리얼을 따라가면 Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지에서 특정 영역에서 텍스트를 추출하는 방법을 배웠습니다. 추출된 텍스트는 지정된 출력 파일에 저장되어 원하는 텍스트 콘텐츠를 정확하게 타겟팅하고 분석할 수 있습니다.