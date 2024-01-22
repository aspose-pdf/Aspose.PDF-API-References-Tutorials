---
title: PDF 파일에서 열 텍스트 추출
linktitle: PDF 파일에서 열 텍스트 추출
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 열 텍스트를 추출하는 방법을 알아보세요.
type: docs
weight: 150
url: /ko/net/programming-with-text/extract-columns-text/
---
이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일에서 열 텍스트를 추출하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

## 요구사항
시작하기 전에 다음 사항이 있는지 확인하세요.

- 컴퓨터에 Visual Studio 또는 기타 C# 컴파일러가 설치되어 있습니다.
- .NET 라이브러리용 Aspose.PDF. 공식 Aspose 웹사이트에서 다운로드하거나 NuGet과 같은 패키지 관리자를 사용하여 설치할 수 있습니다.

## 1단계: 프로젝트 설정
1. 원하는 개발 환경에서 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.PDF에 대한 참조를 추가합니다.

## 2단계: 필수 네임스페이스 가져오기
열 텍스트를 추출하려는 코드 파일에서 파일 상단에 다음 using 지시문을 추가합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

## 3단계: 문서 디렉터리 설정
 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리의 경로를 사용하세요.

## 4단계: PDF 문서 열기
 다음을 사용하여 기존 PDF 문서를 엽니다.`Document`생성자를 생성하고 입력 PDF 파일에 대한 경로를 전달합니다.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");
```

## 5단계: 글꼴 크기 조정
가독성을 높이고 열 형식 텍스트를 더 잘 표현하기 위해 텍스트 조각의 글꼴 크기를 0.7배로 줄입니다.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach(TextFragment tf in tfc)
{
     tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
```

## 6단계: 열에서 텍스트 추출
 수정된 PDF 문서를 메모리 스트림에 저장하고 새 문서로 다시 로드합니다. 그런 다음`TextAbsorber` 열에서 텍스트를 추출하는 클래스입니다.

```csharp
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument);
```

## 7단계: 추출된 텍스트 저장
추출된 텍스트를 지정된 출력 파일 경로의 텍스트 파일에 저장합니다.

```csharp
dataDir = dataDir + "ExtractColumnsText_out.txt";
File.WriteAllText(dataDir, extractedText);
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

### .NET용 Aspose.PDF를 사용하여 열 텍스트 추출을 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "ExtractTextPage.pdf");                
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
pdfDocument.Pages.Accept(tfa);
TextFragmentCollection tfc = tfa.TextFragments;
foreach (TextFragment tf in tfc)
{
	// 글꼴 크기를 70% 이상 줄여야 합니다.
	tf.TextState.FontSize = tf.TextState.FontSize * 0.7f;
}
Stream st = new MemoryStream();
pdfDocument.Save(st);
pdfDocument = new Document(st);
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
String extractedText = textAbsorber.Text;
textAbsorber.Visit(pdfDocument); 
dataDir = dataDir + "ExtractColumnsText_out.txt";
System.IO.File.WriteAllText(dataDir, extractedText);           
Console.WriteLine("\nColumns text extracted successfully from Pages of PDF Document.\nFile saved at " + dataDir);
```

## 결론
.NET용 Aspose.PDF를 사용하여 PDF 문서에서 열 텍스트를 성공적으로 추출했습니다. 추출된 텍스트가 지정된 출력 파일에 저장되었습니다.

### FAQ

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 텍스트 열을 추출하는 방법에 대한 단계별 가이드를 제공합니다. 함께 제공되는 C# 소스 코드는 필요한 절차에 대한 실제 데모를 제공합니다.

#### Q: 어떤 네임스페이스를 가져와야 합니까?

A: 텍스트 열을 추출하려는 코드 파일에서 파일 시작 부분에 다음 using 지시문을 포함합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System.IO;
```

#### Q: 문서 디렉터리를 어떻게 지정합니까?

 A: 줄을 찾아보세요`string dataDir = "YOUR DOCUMENT DIRECTORY";` 코드에서 교체`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

#### Q: 기존 PDF 문서를 어떻게 열 수 있나요?

 A: 4단계에서는 다음을 사용하여 기존 PDF 문서를 엽니다.`Document` 생성자를 생성하고 입력 PDF 파일에 대한 경로를 제공합니다.

#### Q: 글꼴 크기가 조정되는 이유는 무엇입니까?

답변: 5단계에서는 텍스트 조각의 글꼴 크기를 0.7배로 줄이는 작업이 포함됩니다. 이 조정을 통해 가독성이 향상되고 열 형식 텍스트를 더 정확하게 표현합니다.

#### Q: 열에서 텍스트를 추출하려면 어떻게 해야 합니까?

 답변: 6단계는 수정된 PDF 문서를 메모리 스트림에 저장하고 새 문서로 다시 로드한 다음`TextAbsorber` 열에서 텍스트를 추출하는 클래스입니다.

#### Q: 추출된 텍스트를 저장하는 목적은 무엇인가요?

A: 7단계에서는 추출된 텍스트를 지정된 출력 파일 경로의 텍스트 파일에 저장합니다.

#### Q: 추출하기 전에 글꼴 크기를 줄이는 이유는 무엇입니까?

A: 글꼴 크기를 줄이면 추출된 텍스트가 열 내에서 적절하게 정렬되어 원본 레이아웃을 보다 정확하게 표현할 수 있습니다.

#### Q: 이 튜토리얼의 핵심 내용은 무엇입니까?

A: 이 튜토리얼을 따르면 Aspose.PDF for .NET을 사용하여 PDF 문서에서 텍스트 열을 추출하는 데 필요한 지식과 기술을 습득하게 됩니다. 결과 텍스트가 지정된 출력 파일에 저장되었습니다.