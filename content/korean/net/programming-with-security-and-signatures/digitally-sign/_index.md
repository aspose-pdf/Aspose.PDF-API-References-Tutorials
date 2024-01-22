---
title: 디지털 로그인 PDF 파일
linktitle: 디지털 로그인 PDF 파일
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 디지털 서명하는 방법을 알아보세요.
type: docs
weight: 40
url: /ko/net/programming-with-security-and-signatures/digitally-sign/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에 디지털 서명하는 과정을 안내합니다. 디지털 서명은 고유한 전자 지문을 추가하여 문서의 신뢰성과 무결성을 보장합니다.

## 1단계: 전제조건

시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 컴퓨터에 Visual Studio 설치
- .NET용 Aspose.PDF 라이브러리 설치됨

## 2단계: 환경 설정

시작하려면 다음 단계에 따라 개발 환경을 설정하세요.

1. Visual Studio를 열고 새 C# 프로젝트를 만듭니다.
2. 필요한 네임스페이스를 코드 파일로 가져옵니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

## 3단계: 디지털 서명

첫 번째 단계는 PDF 파일에 디지털 서명을 하는 것입니다. 제공된 코드는 .NET용 Aspose.PDF를 사용하여 디지털 서명을 만드는 방법을 보여줍니다.

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

이 코드는 PDF 파일을 로드하고 지정된 모양의 디지털 서명을 만든 다음 추가된 서명과 함께 PDF 파일을 저장합니다.

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
                         // 뭔가를 해라
                     }
                 }
             }
         }
     }
}
```

이 코드는 PDF 파일의 첫 번째 서명을 확인하고 서명이 인증되고 특정 권한이 있는 경우 추가 작업을 수행합니다.

### .NET용 Aspose.PDF를 사용하여 디지털 서명을 위한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉터리의 경로입니다.
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
			// 세 가지 서명 유형 중 하나를 만듭니다.
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
				if (signature.VerifySigned(sigNames[0] as string)) // 첫 번째 확인
				{
					if (signature.IsCertified) // 인증을 받았나요?
					{
						if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) // 접근 권한 받기
						{
							// 뭔가를 해라
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

축하합니다! .NET용 Aspose.PDF를 사용하여 PDF 파일에 디지털 서명을 성공적으로 수행했습니다. 이 튜토리얼에서는 디지털 서명 추가부터 유효성 확인까지 단계별 프로세스를 다루었습니다. 이제 이 기능을 사용하여 디지털 서명으로 PDF 파일을 보호할 수 있습니다.

### FAQ

#### Q: 이 튜토리얼의 목적은 무엇입니까?

A: 이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 PDF 파일에 디지털 서명하는 과정을 안내합니다. 디지털 서명은 전자 지문을 추가하여 문서의 신뢰성과 무결성을 보장합니다.

#### Q: 시작하기 전에 어떤 전제 조건이 필요합니까?

A: 시작하기 전에 C# 프로그래밍 언어에 대한 기본적인 이해가 있는지, Visual Studio가 설치되어 있는지, .NET용 Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요.

#### Q: 개발 환경은 어떻게 설정하나요?

A: 제공된 단계에 따라 Visual Studio에서 새 C# 프로젝트 만들기, 필요한 네임스페이스 가져오기 등 개발 환경을 설정하세요.

#### Q: PDF 파일에 디지털 서명을 어떻게 추가합니까?

 답변: 제공된 샘플 코드는 PDF 파일 로드, 디지털 서명 생성, 모양 지정 및 서명된 PDF 파일 저장 방법을 보여줍니다. 디지털 서명은 다음을 사용하여 추가됩니다.`Certify` 의 방법`PdfFileSignature` 물체.

#### Q: 디지털 서명의 유효성을 어떻게 확인합니까?

A: 디지털 서명을 추가한 후 샘플 코드를 사용하여 서명의 유효성을 확인할 수 있습니다. 서명이 인증되었는지, 특정 접근 권한이 있는지 확인합니다.

####  Q: 무엇을 하는가?`PKCS7` object represent?

 답:`PKCS7` 개체는 디지털 서명에 대한 암호화 기능을 제공하는 데 사용됩니다. 제공된 샘플 코드에서 디지털 서명을 생성하는 데 사용됩니다.

#### Q: 디지털 서명의 모양을 사용자 정의할 수 있습니까?

 A: 예.`SignatureAppearance` 의 재산`PdfFileSignature` 물체.

#### Q: 서명이 유효하지 않으면 어떻게 되나요?

A: 서명이 유효하지 않으면 확인 프로세스가 실패하고 확인 코드 블록 내의 해당 작업이 실행되지 않습니다.

#### Q: 내 디지털 서명의 보안을 어떻게 보장할 수 있나요?

A: 디지털 서명은 설계상 안전하며 암호화 기술을 사용하여 진위성과 무결성을 보장합니다. 개인 키를 안전하게 유지하고 디지털 서명 처리에 대한 모범 사례를 따르십시오.

#### Q: PDF에 여러 개의 디지털 서명을 추가할 수 있나요?

 A: 예, 다음을 사용하여 PDF 파일에 여러 개의 디지털 서명을 추가할 수 있습니다.`PdfFileSignature` 사물`Sign` 또는`Certify` 행동 양식. 각 서명에는 고유한 모양과 구성이 있습니다.