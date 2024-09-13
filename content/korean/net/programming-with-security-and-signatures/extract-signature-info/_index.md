---
title: 서명 정보 추출
linktitle: 서명 정보 추출
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에서 디지털 서명과 인증서 정보를 추출하는 방법을 알아보세요. C# 개발자를 위한 완전한 단계별 가이드입니다.
type: docs
weight: 80
url: /ko/net/programming-with-security-and-signatures/extract-signature-info/
---
## 소개

오늘날의 디지털 세계에서 문서의 보안과 무결성을 보장하는 것은 매우 중요합니다. PDF를 보호하는 데 사용되는 일반적인 방법 중 하나는 디지털 서명을 추가하는 것입니다. 그러나 서명의 세부 정보를 검색하고 확인하는 것은 때때로 어려울 수 있으며, 특히 다양한 인증서를 다루는 경우 더욱 그렇습니다. 이 가이드에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 서명 정보를 추출하는 과정을 안내하여 작업을 쉽게 만들어드립니다. 서명 필드에 액세스하고, 인증서 정보를 추출하고, 파일에 저장하는 방법을 알아봅니다.

## 필수 조건

시작하기에 앞서, 시작하는 데 필요한 모든 것이 준비되었는지 확인하세요.

-  .NET 라이브러리용 Aspose.PDF: 아직 없다면 다음에서 다운로드할 수 있습니다.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net/). 
- .NET 개발 환경: Visual Studio와 같은 IDE가 필요합니다.
- 기본 C# 지식: C#에 대한 지식이 있으면 이 튜토리얼의 코드 조각을 이해하는 데 도움이 됩니다.
- 디지털 서명이 포함된 PDF 문서: 테스트 목적으로, 최소한 하나의 디지털 서명이 포함된 PDF 파일이 있는지 확인하세요.

## 필요한 네임스페이스 가져오기

코드로 넘어가기 전에 필요한 네임스페이스를 가져오는 것이 중요합니다. 이러한 네임스페이스를 사용하면 Aspose.PDF 기능에 액세스하고 PDF 문서로 작업할 수 있습니다.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

이제 기본적인 사항을 설정했으니, PDF에서 서명 정보를 추출하는 실제 과정으로 넘어가겠습니다.

## 1단계: 문서 디렉토리 설정

 PDF 문서에서 작업하기 전에 사용할 파일의 위치를 지정해야 합니다. 다음을 바꿀 수 있습니다.`"YOUR DOCUMENT DIRECTORY"` PDF가 저장된 디렉토리의 실제 경로를 사용합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

여기서 PDF 파일이 들어 있는 디렉토리와 파일 이름 자체를 지정합니다. 파일이 해당 디렉토리에 있는지 확인하세요!

## 2단계: PDF 문서 로딩

 이제 디렉토리를 설정했으므로 다음 단계는 다음을 사용하여 PDF 문서를 로드하는 것입니다.`Document` Aspose.PDF의 클래스입니다.

```csharp
using (Document pdfDocument = new Document(input))
{
    // 여기에서 PDF를 처리합니다.
}
```

 이 코드 줄은 다음을 초기화합니다.`Document`PDF 파일을 나타내는 객체입니다.`using` 이 명령문은 문서가 처리된 후 리소스가 정리되도록 보장합니다.

## 3단계: 양식 필드 액세스

이 단계에서는 PDF 문서의 모든 양식 필드를 반복합니다. 서명은 일반적으로 양식 필드로 저장되므로 이 단계는 서명 필드를 식별하는 데 도움이 됩니다.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // 여기에 서명 필드를 식별하세요.
}
```

 반복을 통해`Form` 의 속성`Document` 객체를 사용하면 각 양식 필드를 조사하여 서명 필드인지 확인할 수 있습니다.

## 4단계: 서명 필드 식별

 양식 필드에 액세스한 후 다음 단계는 어떤 필드가 서명 필드인지 식별하는 것입니다. 각 필드를 다음으로 캐스팅하여 이를 수행할 수 있습니다.`SignatureField` 물체.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // 서명 정보를 추출합니다.
}
```

 여기서 우리는 다음을 사용합니다.`as` 각 양식 필드를 캐스팅하려고 시도하는 키워드`SignatureField`. 캐스트가 성공적이면 필드가 서명이라는 것을 알 수 있습니다.

## 5단계: 인증서 추출

이제 서명 필드를 식별했으므로 다음 작업은 서명에서 인증서를 추출하는 것입니다. 인증서에는 서명자와 서명의 유효성에 대한 중요한 정보가 포함되어 있습니다.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 그만큼`ExtractCertificate` 메서드는 다음을 반환합니다.`Stream` 인증서 데이터를 포함하는 객체. 이 스트림은 추가 분석 또는 저장을 위해 인증서를 저장하는 데 사용할 수 있습니다.

## 6단계: 인증서를 파일에 저장

 인증서를 추출한 후 마지막 단계는 인증서를 파일에 저장하는 것입니다. 이 경우 인증서를 파일로 저장합니다.`.cer` 파일.

```csharp
if (cerStream != null)
{
    using (cerStream)
    {
        byte[] bytes = new byte[cerStream.Length];
        using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
        {
            cerStream.Read(bytes, 0, bytes.Length);
            fs.Write(bytes, 0, bytes.Length);
        }
    }
}
```

이 코드 블록에서 우리는:

1. 인증서 스트림이 null이 아닌지 확인합니다.
2. 인증서 데이터를 바이트 배열로 읽습니다.
3.  바이트 배열을 다음에 쓰세요.`.cer` 문서 디렉토리에 있는 파일입니다.

## 결론

Aspose.PDF for .NET을 사용하여 PDF 문서에서 디지털 서명과 관련 인증서 정보를 추출하는 것은 간단한 단계로 나누면 매우 간단합니다. 문서를 감사하든, 서명을 확인하든, 단순히 인증서를 보관하든, 이 튜토리얼은 효율적으로 이를 수행하는 데 필요한 지식을 제공합니다. 오늘날의 디지털 세계에서 문서를 보호하고 확인하는 것은 매우 중요하며, Aspose.PDF for .NET과 같은 도구를 사용하면 처리하기가 훨씬 쉬워집니다.

## 자주 묻는 질문

### Aspose.PDF for .NET을 사용하여 PDF에서 여러 개의 서명을 추출할 수 있습니까?
네, 코드는 문서의 모든 양식 필드를 순환하여 여러 개의 서명이 있는 경우 이를 추출할 수 있습니다.

### PDF에서 서명이 발견되지 않으면 어떻게 되나요?
서명 필드가 없으면 코드는 오류를 발생시키지 않고 해당 필드를 건너뜁니다.

### 이 방법을 사용하면 서명의 유효성을 확인할 수 있나요?
인증서를 추출할 수는 있지만 서명의 유효성을 확인하려면 인증서의 신뢰 체인을 확인하는 등의 추가 단계가 필요합니다.

### Aspose.PDF for .NET을 사용하여 다른 양식 필드 데이터를 추출하는 것이 가능합니까?
네, Aspose.PDF를 사용하면 서명 필드뿐 아니라 PDF의 다양한 유형의 양식 필드에 액세스하고 조작할 수 있습니다.

### 추출된 인증서의 세부 정보를 어떻게 볼 수 있나요?
 인증서가 저장되면`.cer` 이 파일은 인증서 뷰어를 이용해 열거나, 추가 검사를 위해 시스템 인증서 저장소로 가져올 수 있습니다.