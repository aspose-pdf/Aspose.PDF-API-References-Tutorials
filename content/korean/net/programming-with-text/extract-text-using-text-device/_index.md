---
title: 텍스트 장치를 사용하여 텍스트 추출
linktitle: 텍스트 장치를 사용하여 텍스트 추출
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET의 텍스트 장치를 사용하여 PDF 문서에서 텍스트를 추출하는 방법을 알아보세요.
type: docs
weight: 210
url: /ko/net/programming-with-text/extract-text-using-text-device/
---
## 소개

PDF에서 텍스트를 추출하는 것은 까다로울 수 있습니다. 특히 다양한 형식, 내장된 글꼴 또는 복잡한 레이아웃이 있는 문서를 다룰 때 더욱 그렇습니다. 하지만 Aspose.PDF for .NET을 사용하면 이 프로세스가 아주 쉬워집니다! 추가 분석을 위해 PDF 페이지를 일반 텍스트로 변환하든 특정 섹션을 추출해야 하든 Aspose.PDF가 해결해 드립니다. 이 튜토리얼에서는 Aspose.PDF의 TextDevice 클래스를 사용하여 PDF에서 텍스트를 추출하는 방법을 단계별로 설명합니다. 또한 명확한 설명을 제공하므로 동일한 방법을 자신의 프로젝트에도 쉽게 적용할 수 있습니다.

## 필수 조건

코드로 넘어가기 전에 따라할 수 있는 모든 것이 준비되어 있는지 확인하세요. 필요한 것은 다음과 같습니다.

1.  .NET용 Aspose.PDF: 다음에서 최신 버전을 다운로드하세요.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net/).
2. 개발 환경: Visual Studio 또는 기타 C# 개발 환경.
3. .NET Framework: 프로젝트가 .NET Framework 4.x 이상을 타겟팅하고 있는지 확인하세요.
4. 입력 PDF 파일: 텍스트 추출에 사용할 PDF 파일입니다. 이것을 컴퓨터의 디렉토리에 넣습니다(이것을`YOUR DOCUMENT DIRECTORY`).

## 패키지 가져오기

코드 맨 위에서 Aspose.PDF 작업을 위해 필요한 네임스페이스를 가져와야 합니다.

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Devices;
using System;
using System.Text;
```

## 1단계: PDF 문서 로드

 텍스트를 추출하기 전에 PDF 문서를 메모리에 로드해야 합니다. 이 단계에서는 Aspose.PDF의`Document` 클래스. 이렇게 하면 파일 내의 모든 페이지와 콘텐츠에 액세스할 수 있습니다.

```csharp
// PDF 문서 경로를 정의하세요
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF 문서를 로드합니다
Document pdfDocument = new Document(dataDir + "input.pdf");
```

 여기서 우리는 사용하고 있습니다`Document pdfDocument = new Document(dataDir + "input.pdf");` PDF를 로드하려면.`dataDir` 변수는 PDF 파일의 디렉토리 경로를 보유합니다. 이를 통해 전체 문서에 액세스할 수 있어 페이지를 반복하고 콘텐츠를 추출할 수 있습니다.

## 2단계: 텍스트 저장을 위한 문자열 빌더 설정

 이제 문서가 로드되었으므로 추출된 텍스트를 저장할 방법이 필요합니다. 이를 위해 다음을 사용합니다.`StringBuilder` 이를 통해 효율적인 문자열 연결이 가능합니다.

```csharp
// 추출된 텍스트를 보관하는 StringBuilder
StringBuilder builder = new StringBuilder();
```

 우리는 초기화합니다`StringBuilder`인스턴스는 각 페이지에서 추출된 텍스트를 수집합니다. 루프에서 일반적인 문자열 연결에 비해 큰 문자열을 처리하는 더 효율적인 방법입니다.

## 3단계: PDF 페이지 반복

 다음으로 PDF 문서의 각 페이지를 반복하여 텍스트를 추출합니다. 각 페이지를 개별적으로 처리합니다.`TextDevice` PDF 콘텐츠를 텍스트 형식으로 변환하는 역할을 하는 클래스입니다.

```csharp
// PDF의 모든 페이지를 반복합니다.
foreach (Page pdfPage in pdfDocument.Pages)
{
    // 각 페이지를 처리하여 텍스트 추출
}
```

이 루프는 PDF의 모든 페이지를 통과합니다.`pdfDocument.Pages` ). 각 페이지에서 텍스트를 추출하여 추가합니다.`StringBuilder`.

## 4단계: 각 페이지에서 텍스트 추출

 이제 각 페이지에 대한 텍스트 추출 프로세스를 설정합니다. 여기서는 다음을 만듭니다.`TextDevice` 객체를 사용하여 PDF 페이지를 처리합니다.`TextDevice` 설정한 추출 옵션에 따라 원시 텍스트나 서식이 지정된 텍스트를 추출합니다.

```csharp
using (MemoryStream textStream = new MemoryStream())
{
    // 텍스트 추출을 위한 텍스트 장치 생성
    TextDevice textDevice = new TextDevice();
    
    // 텍스트 추출 옵션을 'Pure' 모드로 설정하세요
    TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);
    textDevice.ExtractionOptions = textExtOptions;

    //현재 페이지에서 텍스트를 추출하여 메모리 스트림에 저장합니다.
    textDevice.Process(pdfPage, textStream);

    // 메모리 스트림을 텍스트로 변환
    string extractedText = Encoding.Unicode.GetString(textStream.ToArray());

    // 추출된 텍스트를 StringBuilder에 추가합니다.
    builder.Append(extractedText);
}
```

- `TextDevice textDevice = new TextDevice();` : 그`TextDevice` 클래스는 PDF에서 텍스트를 추출하는 데 사용됩니다.
- `TextExtractionOptions textExtOptions = new TextExtractionOptions(TextExtractionOptions.TextFormattingMode.Pure);` : 이 옵션은 글꼴이나 위치와 같은 서식을 유지하지 않고 원시 텍스트를 추출합니다. 또한 다음을 사용할 수 있습니다.`TextFormattingMode.Raw` 서식을 보다 세부적으로 제어해야 하는 경우
- `textDevice.Process(pdfPage, textStream);` : 이것은 PDF의 각 페이지를 처리하고 추출된 텍스트를 저장합니다.`MemoryStream`.
-  마지막으로, 우리는 텍스트를 변환합니다`MemoryStream` 문자열에 추가하고`StringBuilder`.

## 5단계: 추출된 텍스트를 파일에 저장

 모든 페이지를 처리한 후 텍스트는 다음 위치에 저장됩니다.`StringBuilder`마지막 단계는 추출된 텍스트를 파일에 저장하는 것입니다.

```csharp
// 텍스트 파일의 출력 경로를 정의합니다
dataDir = dataDir + "input_Text_Extracted_out.txt";

// 추출된 텍스트를 파일에 저장
File.WriteAllText(dataDir, builder.ToString());

Console.WriteLine("\nText extracted successfully from PDF document.\nFile saved at " + dataDir);
```

- `File.WriteAllText(dataDir, builder.ToString());` : 이것은 전체 내용을 작성합니다.`StringBuilder` 텍스트 파일로.
- 출력 파일의 경로는 파일 이름을 추가하여 설정됩니다.`"input_Text_Extracted_out.txt"` )에게`dataDir` 길.

## 결론

Aspose.PDF for .NET을 사용하여 PDF에서 텍스트를 추출하는 것은 간단하고 효율적인 프로세스입니다. 이 가이드에 설명된 단계를 따르면 PDF 문서를 쉽게 열고, 페이지를 반복하고, 텍스트를 텍스트 파일로 추출할 수 있습니다. 이는 특히 대량의 PDF 데이터를 처리하거나, 텍스트 분석을 수행하거나, 추가 조작을 위해 문서를 변환하는 데 유용합니다.

Aspose.PDF를 사용하면 텍스트 추출에 국한되지 않습니다. 주석을 처리하고, 이미지를 조작하거나, 심지어 PDF를 HTML이나 Word와 같은 다른 형식으로 변환할 수도 있습니다. 이 라이브러리의 유연성과 강력함은 .NET 애플리케이션에서 PDF 관리를 위한 귀중한 도구가 됩니다.

## 자주 묻는 질문

### Aspose.PDF는 이미지 기반 PDF에서 텍스트를 추출할 수 있나요?
아니요, Aspose.PDF는 콘텐츠 기반 PDF에서 텍스트를 추출하도록 설계되었습니다. 이미지 기반 PDF의 경우 OCR 기술이 필요합니다.

### Aspose.PDF는 텍스트를 추출할 때 서식을 유지합니까?
기본적으로 텍스트는 서식 없이 추출되지만, 일부 서식을 유지하려는 경우 추출 옵션을 조정할 수 있습니다.

### 특정 페이지 범위에서 텍스트를 추출할 수 있나요?
네, 모든 페이지 대신 특정 범위의 페이지에 걸쳐 반복하도록 코드를 수정할 수 있습니다.

### Aspose.PDF의 텍스트 추출 모드는 무엇입니까?
Aspose.PDF는 Raw와 Pure의 두 가지 모드를 제공합니다. Raw 모드는 원래 레이아웃을 유지하려고 하는 반면 Pure 모드는 서식 없이 텍스트만 추출합니다.

### .NET용 Aspose.PDF는 .NET Core와 호환됩니까?
네, .NET용 Aspose.PDF는 .NET Core 및 .NET Framework와 완벽하게 호환됩니다.