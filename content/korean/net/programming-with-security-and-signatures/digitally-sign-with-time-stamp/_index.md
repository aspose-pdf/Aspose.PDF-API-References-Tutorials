---
title: PDF 파일에 타임스탬프를 포함한 디지털 서명
linktitle: PDF 파일에 타임스탬프를 포함한 디지털 서명
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 타임스탬프가 포함된 디지털 서명을 수행하는 방법을 알아보세요.
type: docs
weight: 50
url: /ko/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 타임스탬프가 있는 PDF 파일에 디지털 서명하는 과정을 안내해 드리겠습니다. 타임스탬프가 있는 디지털 서명은 타임스탬프가 있는 전자 지문을 추가하여 문서의 진위성과 무결성을 보장합니다.

## 1단계: 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 컴퓨터에 Visual Studio 설치하기
- .NET용 Aspose.PDF 라이브러리 설치됨

## 2단계: 환경 설정

시작하려면 다음 단계에 따라 개발 환경을 설정하세요.

1. Visual Studio를 열고 새로운 C# 프로젝트를 만듭니다.
2. 필요한 네임스페이스를 코드 파일에 가져옵니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## 3단계: 타임스탬프가 포함된 디지털 서명

첫 번째 단계는 PDF 파일에 타임스탬프가 있는 디지털 서명을 수행하는 것입니다. 제공된 코드는 .NET용 Aspose.PDF로 이 서명을 달성하는 방법을 보여줍니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

이 코드는 PDF 파일을 로드하고, PFX 파일(개인 키)과 지정된 타임스탬프 매개변수를 사용하여 타임스탬프가 있는 디지털 서명을 만듭니다. 그런 다음 서명이 PDF 파일에 추가되고 접미사 "_밖으로".

### .NET용 Aspose.PDF를 사용하여 타임스탬프가 있는 디지털 서명을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); // 사용자/비밀번호 생략 가능
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		// 3가지 서명 유형 중 하나를 만드세요
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		// 출력 PDF 파일 저장
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 파일에 타임스탬프가 있는 디지털 서명을 성공적으로 수행했습니다. 이 튜토리얼은 서명을 만드는 것부터 업데이트된 PDF 파일을 저장하는 것까지의 단계별 프로세스를 다루었습니다. 이제 이 기능을 사용하여 타임스탬프가 있는 디지털 서명을 PDF 파일에 추가할 수 있습니다.

### PDF 파일에 타임스탬프를 사용하여 디지털 서명하기 위한 FAQ

#### 질문: 타임스탬프로 디지털 서명하는 목적은 무엇인가요?

답변: 타임스탬프로 디지털 서명하면 타임스탬프가 포함된 전자 지문이 PDF 파일에 추가되어 특정 시점에서 문서의 진위성과 무결성이 보장됩니다.

#### 질문: 이 튜토리얼을 시작하려면 어떤 전제 조건이 필요합니까?

A: 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있는지, Visual Studio가 설치되어 있는지, 그리고 .NET용 Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요.

#### 질문: 개발 환경을 어떻게 설정할 수 있나요?

대답: Visual Studio에서 새 C# 프로젝트를 만들고 필요한 네임스페이스를 가져오는 것을 포함하여, 제공된 단계에 따라 개발 환경을 설정하세요.

#### 질문: PDF에 타임스탬프가 포함된 디지털 서명을 추가하려면 어떻게 해야 하나요?

답변: 제공된 샘플 코드는 PDF 파일을 로드하고, PFX 파일(개인 키)과 지정된 타임스탬프 설정을 사용하여 타임스탬프가 포함된 디지털 서명을 만들고, PDF 파일에 서명을 추가하고, 업데이트된 파일을 저장하는 방법을 보여줍니다.

#### 질문: PFX 파일이란 무엇이고, 이 예에서 사용된 이유는 무엇입니까?

A: PFX(Personal Exchange Format) 파일에는 개인 키와 인증서가 들어 있습니다. 여기서는 디지털 서명에 대한 암호화 기능을 제공하는 데 사용됩니다. 자리 표시자를 PFX 파일과 비밀번호로 바꿔야 합니다.

#### 질문: TimestampSettings은 무엇인가요?

A: TimestampSettings는 서명에 전자 타임스탬프를 추가하는 데 사용되는 타임스탬프 서버에 대한 설정을 정의합니다. 여기에는 타임스탬프 서버 URL과 선택적 사용자 자격 증명이 포함됩니다.

#### 질문: 예시에 나온 것 외에 다른 타임스탬프 서버를 사용할 수 있나요?
 A: 네, 호환되는 타임스탬프 서버를 사용할 수 있습니다. URL을 바꾸고 필요한 경우 적절한 사용자 자격 증명을 제공하세요.`TimestampSettings` 물체.

#### 질문: 서명 사각형을 지정하는 목적은 무엇입니까?

A: 서명 사각형은 PDF 페이지에서 디지털 서명 모양의 위치와 크기를 정의합니다. 이러한 값을 조정하여 원하는 대로 서명을 배치합니다.

#### 질문: 서명하는 동안 타임스탬프 서버를 사용할 수 없는 경우 어떻게 되나요?

A: 서명하는 동안 타임스탬프 서버를 사용할 수 없는 경우 프로세스가 실패하거나 더 오래 걸릴 수 있습니다. 타임스탬프 서버가 안정적이고 액세스 가능한지 확인하세요.

#### 질문: 서명된 PDF에 타임스탬프가 있는지 어떻게 확인할 수 있나요?

 A: 제공된 샘플 코드를 사용하여 서명된 PDF를 검사할 수 있습니다.`TimestampSettings` 서명할 때 사용한 정보는 서명 세부 정보에서 확인할 수 있습니다.

#### 질문: 타임스탬프가 포함된 디지털 서명은 법적 구속력이 있습니까?

A: 타임스탬프가 있는 디지털 서명은 많은 관할권에서 법적 가치를 지니고 있으며, 간단한 디지털 서명보다 더 신뢰할 수 있는 것으로 간주됩니다. 특정 규정에 대해서는 관할권의 법률 전문가에게 문의하세요.

#### 질문: 타임스탬프가 포함된 여러 개의 디지털 서명을 PDF에 추가할 수 있나요?

A: 네, 서명 생성 프로세스를 여러 번 호출하여 타임스탬프가 있는 여러 디지털 서명을 PDF 파일에 추가할 수 있습니다. 각 서명에는 고유한 타임스탬프가 있습니다.