---
title: PDF 파일에 디지털로 로그인
linktitle: PDF 파일에 디지털로 로그인
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에 디지털 서명하는 방법을 알아보세요.
type: docs
weight: 40
url: /ko/net/programming-with-security-and-signatures/digitally-sign/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 디지털 서명하는 과정을 안내해 드리겠습니다. 디지털 서명은 고유한 전자 지문을 추가하여 문서의 신뢰성과 무결성을 보장합니다.

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
using System.Collections.Generic;
```

## 3단계: 디지털 서명

첫 번째 단계는 PDF 파일에 디지털 서명을 하는 것입니다. 제공된 코드는 Aspose.PDF for .NET으로 디지털 서명을 만드는 방법을 보여줍니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = "";
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
using (Document document = new Document(inFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
         DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
         signature.Certify(1, "Reason for signing", "Contact", "Location", true, rect, docMdpSignature);
         signature.Save(outFile);
     }
}
```

이 코드는 PDF 파일을 로드하고, 지정된 모양의 디지털 서명을 만든 다음, 추가된 서명이 포함된 PDF 파일을 저장합니다.

## 4단계: 서명 확인

디지털 서명을 추가한 후 PDF 파일에 유효한 서명이 포함되어 있는지 확인할 수 있습니다.

```csharp
using(Document document = new Document(outFile))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         IList<string> sigNames = signature. GetSignNames();
         if (sigNames.Count > 0)
         {
             if (signature.VerifySigned(sigNames[0] as string))
             {
                 if (signature.IsCertified)
                 {
                     if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms)
                     {
                         // 뭔가를 하세요
                     }
                 }
             }
         }
     }
}
```

이 코드는 PDF 파일의 첫 번째 서명을 확인하고, 서명이 인증되었고 특정 권한이 있는 경우 추가 작업을 수행합니다.

### .NET용 Aspose.PDF를 사용하여 Digitally Sign을 위한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENTS DIRECTORY";
	string pbxFile = "";
	string inFile = dataDir + @"DigitallySign.pdf";
	string outFile = dataDir + @"DigitallySign_out.pdf";
	using (Document document = new Document(inFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			PKCS7 pkcs = new PKCS7(pbxFile, "WebSales"); // PKCS7/PKCS7Detached 객체 사용
			DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
			System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
			// 서명 모양 설정
			signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
			// 3가지 서명 유형 중 하나를 만드세요
			signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
			// 출력 PDF 파일 저장
			signature.Save(outFile);
		}
	}
	using (Document document = new Document(outFile))
	{
		using (PdfFileSignature signature = new PdfFileSignature(document))
		{
			IList<string> sigNames = signature.GetSignNames();
			if (sigNames.Count > 0) // 서명이 있나요?
			{
				if (signature.VerifySigned(sigNames[0] as string)) // 첫 번째 것을 확인하세요
				{
					if (signature.IsCertified) // 인증됨?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // 접근 권한 얻기
						{
							// 뭔가를 하세요
						}
					}
				}
			}
		}
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 파일에 디지털 서명을 성공적으로 수행했습니다. 이 튜토리얼에서는 디지털 서명을 추가하는 것부터 유효성을 확인하는 것까지 단계별 프로세스를 다루었습니다. 이제 이 기능을 사용하여 디지털 서명으로 PDF 파일을 보호할 수 있습니다.

### 자주 묻는 질문

#### 질문: 이 튜토리얼의 목적은 무엇인가요?

A: 이 튜토리얼은 Aspose.PDF for .NET을 사용하여 PDF 파일에 디지털 서명하는 과정을 안내합니다. 디지털 서명은 전자 지문을 추가하여 문서의 신뢰성과 무결성을 보장합니다.

#### 질문: 시작하기 전에 어떤 전제 조건이 필요한가요?

A: 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있는지, Visual Studio가 설치되어 있는지, 그리고 .NET용 Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요.

#### 질문: 개발 환경을 어떻게 설정하나요?

대답: Visual Studio에서 새 C# 프로젝트를 만들고 필요한 네임스페이스를 가져오는 것을 포함하여 개발 환경을 설정하려면 제공된 단계를 따르세요.

#### 질문: PDF 파일에 디지털 서명을 추가하려면 어떻게 해야 하나요?

 A: 제공된 샘플 코드는 PDF 파일을 로드하고, 디지털 서명을 만들고, 모양을 지정하고, 서명된 PDF 파일을 저장하는 방법을 보여줍니다. 디지털 서명은 다음을 사용하여 추가됩니다.`Certify` 의 방법`PdfFileSignature` 물체.

#### 질문: 디지털 서명의 유효성을 어떻게 확인하나요?

A: 디지털 서명을 추가한 후 샘플 코드를 사용하여 서명의 유효성을 확인할 수 있습니다. 서명이 인증되었는지, 특정 액세스 권한이 있는지 확인합니다.

####  Q: 무슨 일이야?`PKCS7` object represent?

 A: 그`PKCS7` 객체는 디지털 서명에 대한 암호화 기능을 제공하는 데 사용됩니다. 제공된 샘플 코드에서 디지털 서명을 만드는 데 사용됩니다.

#### 질문: 디지털 서명의 모양을 사용자 지정할 수 있나요?

 A: 예, 이미지 경로를 지정하여 디지털 서명의 모양을 사용자 정의할 수 있습니다.`SignatureAppearance` 의 속성`PdfFileSignature` 물체.

#### 질문: 서명이 유효하지 않으면 어떻게 되나요?

답변: 서명이 유효하지 않으면 검증 프로세스가 실패하고, 검증 코드 블록 내의 해당 동작이 실행되지 않습니다.

#### 질문: 디지털 서명의 보안을 어떻게 보장할 수 있나요?

A: 디지털 서명은 설계상 안전하며 암호화 기술을 사용하여 진위성과 무결성을 보장합니다. 개인 키를 안전하게 보관하고 디지털 서명을 처리하기 위한 모범 사례를 따르세요.

#### 질문: PDF에 여러 개의 디지털 서명을 추가할 수 있나요?

 A: 예, 다음을 사용하여 PDF 파일에 여러 개의 디지털 서명을 추가할 수 있습니다.`PdfFileSignature` 사물`Sign` 또는`Certify` 방법. 각 서명은 고유한 모양과 구성을 갖습니다.