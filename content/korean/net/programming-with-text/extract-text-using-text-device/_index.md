---
title: 텍스트 장치를 사용하여 텍스트 추출
linktitle: 텍스트 장치를 사용하여 텍스트 추출
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF의 텍스트 장치를 사용하여 PDF 문서에서 텍스트를 추출하는 방법을 알아보세요.
type: docs
weight: 210
url: /ko/net/programming-with-text/extract-text-using-text-device/
---
이 튜토리얼은 .NET용 Aspose.PDF의 텍스트 장치를 사용하여 PDF 문서에서 텍스트를 추출하는 과정을 안내합니다. 제공된 C# 소스 코드는 필요한 단계를 보여줍니다.

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
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

## 3단계: 문서 디렉터리 설정
 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서가 저장된 디렉토리의 경로를 사용하세요.

## 4단계: PDF 문서 열기
 다음을 사용하여 기존 PDF 문서를 엽니다.`Document`생성자를 생성하고 입력 PDF 파일에 대한 경로를 전달합니다.

```csharp
Document pdfDocument = new Document(dataDir + "input.pdf");
```

## 5단계: 텍스트 장치를 사용하여 텍스트 추출
 만들기`StringBuilder` 추출된 텍스트를 담는 객체입니다. 문서의 각 페이지를 반복하고`TextDevice` 각 페이지에서 텍스트를 추출합니다.

```csharp
StringBuilder builder = new StringBuilder();
string extractedText = "";
foreach(Page pdfPage in pdfDocument.Pages)
{
using (MemoryStream textStream = new MemoryStream())
{
TextDevice textDevice = new TextDevice();
TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
textDevice.ExtractionOptions = textExtOptions;
textDevice.Process(pdfPage, textStream);
textStream. Close();
extractedText = Encoding.Unicode.GetString(textStream.ToArray());
}
builder. Append(extractedText);
}
```

## 6단계: 추출된 텍스트 저장
 출력 파일 경로를 지정하고 추출된 텍스트를 다음을 사용하여 텍스트 파일에 저장합니다.`File.WriteAllText` 방법.

```csharp
dataDir = dataDir + "input_Text_Extracted_out.txt";
File.WriteAllText(dataDir, builder.ToString());
```

### .NET용 Aspose.PDF를 사용하여 텍스트 장치를 사용하여 텍스트 추출에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document( dataDir + "input.pdf");
System.Text.StringBuilder builder = new System.Text.StringBuilder();
//추출된 텍스트를 보관할 문자열
string extractedText = "";
foreach (Page pdfPage in pdfDocument.Pages)
{
	using (MemoryStream textStream = new MemoryStream())
	{
		// 텍스트 장치 만들기
		TextDevice textDevice = new TextDevice();
		// 텍스트 추출 옵션 설정 - 텍스트 추출 모드 설정(Raw 또는 Pure)
		TextExtractionOptions textExtOptions = new
		TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
		textDevice.ExtractionOptions = textExtOptions;
		// 특정 페이지를 변환하고 텍스트를 스트림에 저장
		textDevice.Process(pdfPage, textStream);
		// 특정 페이지를 변환하고 텍스트를 스트림에 저장
		textDevice.Process(pdfDocument.Pages[1], textStream);
		// 메모리 스트림 닫기
		textStream.Close();
		// 메모리 스트림에서 텍스트 가져오기
		extractedText = Encoding.Unicode.GetString(textStream.ToArray());
	}
	builder.Append(extractedText);
}
dataDir = dataDir + "input_Text_Extracted_out.txt";
// 추출된 텍스트를 텍스트 파일에 저장
File.WriteAllText(dataDir, builder.ToString());
Console.WriteLine("\nText extracted successfully using text device from page of PDF Document.\nFile saved at " + dataDir);
```

## 결론
.NET용 Aspose.PDF의 텍스트 장치를 사용하여 PDF 문서에서 텍스트를 성공적으로 추출했습니다. 추출된 텍스트가 지정된 출력 파일에 저장되었습니다.

### FAQ

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼은 .NET용 Aspose.PDF의 텍스트 장치 기능을 사용하여 PDF 문서에서 텍스트를 추출하는 방법에 대한 지침을 제공합니다. 함께 제공되는 C# 소스 코드는 이 작업을 수행하는 데 필요한 단계를 보여줍니다.

#### Q: 어떤 네임스페이스를 가져와야 합니까?

A: 텍스트를 추출하려는 코드 파일에서 파일 시작 부분에 다음 using 지시문을 포함합니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Devices;
using System.IO;
using System.Text;
```

#### Q: 문서 디렉터리를 어떻게 지정합니까?

 A: 코드에서 다음과 같은 줄을 찾으세요.`string dataDir = "YOUR DOCUMENT DIRECTORY";` 교체하고`"YOUR DOCUMENT DIRECTORY"` 문서 디렉토리의 실제 경로를 사용하십시오.

#### Q: 기존 PDF 문서를 어떻게 열 수 있나요?

 A: 4단계에서는 다음을 사용하여 기존 PDF 문서를 엽니다.`Document` 생성자를 생성하고 입력 PDF 파일에 대한 경로를 제공합니다.

#### Q: 텍스트 장치를 사용하여 텍스트를 추출하려면 어떻게 해야 합니까?

 A: 5단계에서는`StringBuilder` 추출된 텍스트를 담는 객체입니다. 그런 다음 문서의 각 페이지를 반복하고`TextDevice` 와 함께`TextExtractionOptions` 각 페이지에서 텍스트를 추출합니다.

#### Q: 추출된 텍스트를 파일에 어떻게 저장하나요?

 A: 6단계에서는 출력 파일 경로를 지정하고`File.WriteAllText`추출된 텍스트를 텍스트 파일로 저장하는 방법입니다.

#### Q: 이 튜토리얼의 핵심 내용은 무엇입니까?

A: 이 튜토리얼을 따라 .NET용 Aspose.PDF의 텍스트 장치 기능을 활용하여 PDF 문서에서 텍스트를 추출하는 방법을 배웠습니다. 추출된 텍스트는 지정된 출력 파일에 저장되므로 필요에 따라 추출된 내용을 조작하고 활용할 수 있습니다.