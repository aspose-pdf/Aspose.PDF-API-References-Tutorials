---
title: PDF 파일에서 텍스트 페이지 추출
linktitle: PDF 파일에서 텍스트 페이지 추출
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 특정 페이지에서 텍스트를 추출하는 방법을 알아보세요.
type: docs
weight: 200
url: /ko/net/programming-with-text/extract-text-page/
---
이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 PDF 파일의 특정 페이지에서 텍스트를 추출하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio 또는 기타 C# 컴파일러가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필수 네임스페이스 가져오기
텍스트를 추출하려는 코드 파일에서 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using System.IO;
```

## 3단계: 문서 디렉터리 설정
 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리의 경로를 사용하세요.

## 4단계: PDF 문서 열기
 다음을 사용하여 기존 PDF 문서를 엽니다.`Document`생성자를 생성하고 입력 PDF 파일에 대한 경로를 전달합니다.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 5단계: 특정 페이지에서 텍스트 추출
 만들기`TextAbsorber` 문서에서 텍스트를 추출하는 개체입니다. 원하는 페이지에 대한 흡수체를 다음을 통해 액세스하여 수락합니다.`Pages` 의 컬렉션`pdfDocument`.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages[1].Accept(textAbsorber);
```

## 6단계: 추출된 텍스트 가져오기
 다음에서 추출된 텍스트에 액세스합니다.`TextAbsorber` 물체.

```csharp
string extractedText = textAbsorber.Text;
```

## 7단계: 추출된 텍스트 저장
 만들기`TextWriter` 추출된 텍스트를 저장할 파일을 엽니다. 추출된 텍스트를 파일에 쓰고 스트림을 닫습니다.

```csharp
dataDir = dataDir + "extracted-text_out.txt";
TextWriter tw = new StreamWriter(dataDir);
tw.WriteLine(extractedText);
tw. Close();
```

### .NET용 Aspose.PDF를 사용하여 텍스트 추출 페이지의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
// 텍스트를 추출하기 위해 TextAbsorber 개체 만들기
TextAbsorber textAbsorber = new TextAbsorber();
//특정 페이지에 대한 흡수체 수락
pdfDocument.Pages[1].Accept(textAbsorber);
// 추출된 텍스트 가져오기
string extractedText = textAbsorber.Text;
dataDir = dataDir + "extracted-text_out.txt";
// 작성자를 만들고 파일을 엽니다.
TextWriter tw = new StreamWriter(dataDir);
// 파일에 텍스트 한 줄 쓰기
tw.WriteLine(extractedText);
// 스트림 닫기
tw.Close();
Console.WriteLine("\nText extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## 결론
.NET용 Aspose.PDF를 사용하여 PDF 문서의 특정 페이지에서 텍스트를 성공적으로 추출했습니다. 추출된 텍스트가 지정된 출력 파일에 저장되었습니다.

### FAQ

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 PDF 파일의 특정 페이지에서 텍스트를 추출하는 과정을 안내합니다. 함께 제공되는 C# 소스 코드는 이 작업을 수행하는 데 필요한 단계를 보여줍니다.

#### Q: 어떤 네임스페이스를 가져와야 합니까?

A: 텍스트를 추출하려는 코드 파일에서 파일 시작 부분에 다음 using 지시문을 포함합니다.

```csharp
using Aspose.Pdf;
using System.IO;
```

#### Q: 문서 디렉터리를 어떻게 지정합니까?

 A: 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

#### Q: 기존 PDF 문서를 어떻게 열 수 있나요?

 A: 4단계에서는 다음을 사용하여 기존 PDF 문서를 엽니다.`Document` 생성자를 생성하고 입력 PDF 파일에 대한 경로를 제공합니다.

#### Q: 특정 페이지에서 텍스트를 추출하려면 어떻게 해야 합니까?

 A: 5단계에서는`TextAbsorber` PDF 문서에서 텍스트를 추출하는 개체입니다. 그런 다음 다음을 통해 액세스하여 원하는 페이지에 대한 흡수체를 수락합니다.`Pages` 의 컬렉션`pdfDocument`.

#### Q: 추출된 텍스트에 어떻게 액세스합니까?

 A: 6단계에서는 추출된 텍스트에 액세스하는 과정을 안내합니다.`TextAbsorber` 물체.

#### Q: 추출된 텍스트를 파일에 어떻게 저장하나요?

 A: 7단계에서는`TextWriter`, 추출된 텍스트를 저장할 파일을 열고 추출된 텍스트를 파일에 쓴 다음 스트림을 닫습니다.

#### Q: 이 튜토리얼의 핵심 내용은 무엇입니까?

A: 이 튜토리얼을 따라 .NET용 Aspose.PDF를 사용하여 PDF 문서의 특정 페이지에서 텍스트를 추출하는 방법을 배웠습니다. 추출된 텍스트는 지정된 출력 파일에 저장되어 특정 페이지의 텍스트 내용을 대상으로 지정하고 분석할 수 있습니다.