---
title: 서명 필드를 사용하여 스마트 카드로 서명
linktitle: 서명 필드를 사용하여 스마트 카드로 서명
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 스마트 카드로 PDF 파일을 안전하게 서명하세요.
type: docs
weight: 120
url: /ko/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
스마트 카드를 사용한 디지털 서명은 PDF 파일에 서명하는 안전한 방법입니다. Aspose.PDF for .NET을 사용하면 다음 소스 코드를 따라 서명 필드와 스마트 카드를 사용하여 PDF 파일에 쉽게 서명할 수 있습니다.

## 1단계: 필요한 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 가져오기 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 서명하려는 PDF 파일이 들어 있는 폴더의 경로를 지정해야 합니다. 바꾸기`"YOUR DOCUMENTS DIRECTORY"` 다음 코드에서는 문서 폴더의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3단계: PDF 문서 복사 및 열기

이제 다음 코드를 사용하여 서명할 PDF 문서를 복사하여 열어 보겠습니다.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);

using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
     using (Document doc = new Document(fs))
     {
         // 서명 필드 만들기
         SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));

         // 매장에서 인증서를 선택하세요
         X509Store store = new X509Store(StoreLocation.CurrentUser);
         store.Open(OpenFlags.ReadOnly);
         X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
        
         // 필요한 정보로 외부 서명을 만드세요
         ExternalSignature externalSignature = new ExternalSignature(sel[0])
         {
             Authority = "Me",
             Reason = "Reason",
             ContactInfo = "Contact"
         };

         field1.PartialName = "sig1";
         doc.Form.Add(field1, 1);
         field1.Sign(externalSignature);
         doc.Save();
     }
}
```

## 4단계: 서명 확인

 마지막으로, 우리는 다음을 사용하여 서명된 PDF 파일의 서명을 확인합니다.`PdfFileSignature` 클래스. 우리는 서명 이름을 얻고 하나씩 확인합니다. 서명이 검증에 실패하면 예외가 발생합니다. 여기에 해당 코드가 있습니다.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### .NET용 Aspose.PDF를 사용하여 스마트 카드로 서명 필드에 서명하기 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
	using (Document doc = new Document(fs))
	{
		SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
		// Windows 인증서 저장소에서 인증서 선택으로 서명
		System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
		store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
		// 매장에서 수동으로 인증서를 선택했습니다.
		System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
		Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
		{
			Authority = "Me",
			Reason = "Reason",
			ContactInfo = "Contact"
		};
		field1.PartialName = "sig1";
		doc.Form.Add(field1, 1);
		field1.Sign(externalSignature);
		doc.Save();
	}
}
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
	IList<string> sigNames = pdfSign.GetSignNames();
	for (int index = 0; index <= sigNames.Count - 1; index++)
	{
		if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
		{
			throw new ApplicationException("Not verified");
		}
	}
}
```

## 결론

축하합니다! 이제 Aspose.PDF for .NET의 서명 필드를 사용하여 스마트 카드로 PDF 파일에 서명하는 단계별 가이드가 있습니다. 이 코드를 사용하여 PDF 문서에 보안 디지털 서명을 추가할 수 있습니다.

고급 디지털 서명 및 인증서 관리 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.

### 자주 묻는 질문

#### 질문: 스마트카드를 사용하여 디지털 서명을 할 때 서명 필드를 사용하면 어떤 이점이 있나요?

A: 스마트 카드로 디지털 서명을 위해 서명 필드를 사용하면 PDF 내에 서명이 적용되는 지정된 영역이 제공됩니다. 이렇게 하면 문서의 명확성이 향상되고 서명의 진위성이 보장됩니다.

#### 질문: .NET용 Aspose.PDF 라이브러리는 서명 필드를 사용하여 스마트 카드 기반 디지털 서명을 어떻게 구현합니까?

답변: .NET용 Aspose.PDF를 사용하면 서명 필드를 만들고, 스마트 카드 인증서를 선택하고, PDF 문서 내의 특정 영역에 디지털 서명을 적용하는 과정이 간소화됩니다.

#### 질문: 스마트카드 기반 서명에 특정 인증서를 선택하는 것이 중요한 이유는 무엇입니까?

A: 특정 인증서를 선택하면 서명자를 고유하게 식별하고 서명의 무결성을 보장할 수 있습니다. 이를 통해 디지털 서명 표준에 대한 신뢰와 준수를 확립하는 데 도움이 됩니다.

#### 질문: 제공된 소스 코드는 서명 필드를 사용한 스마트 카드 기반 서명 프로세스를 어떻게 처리합니까?

A: 소스 코드는 서명 필드를 만들고, 스마트 카드 인증서를 선택하고, 특정 서명 정보가 있는 디지털 서명을 적용하는 방법을 보여줍니다. 또한 서명의 유효성을 확인하는 방법도 보여줍니다.

#### 질문: 서명 필드의 모양을 사용자 지정할 수 있나요?

대답: 네, 문서 레이아웃에 맞게 서명 필드의 크기, 위치, 시각적 표현 등을 사용자 지정할 수 있습니다.

#### 질문: 검증 단계에서 서명 검증에 실패하면 어떻게 되나요?

A: 서명이 검증에 실패하면 예외가 발생하여 서명이 유효하지 않음을 나타냅니다. 이를 통해 유효하고 신뢰할 수 있는 서명만 허용됩니다.

#### 질문: 하나의 PDF 문서에 여러 개의 서명 필드와 스마트 카드 기반 서명을 적용할 수 있나요?

물론입니다. 동일한 PDF 문서의 여러 영역에 여러 개의 서명 필드와 스마트 카드 기반 서명을 적용하여 다층 보안을 제공할 수 있습니다.

#### 질문: 서명 필드를 사용하면 전체 문서 서명 프로세스가 어떻게 향상되나요?

대답: 서명 필드를 사용하면 서명자가 지정된 영역에 서명하기만 하면 되므로 문서 서명 과정이 간소화되고, 서명 과정이 보다 체계적이고 사용자 친화적으로 진행됩니다.

#### 질문: 스마트 카드 기반 서명에서 서명 필드를 사용하는 데 제한이 있나요?

A: 스마트 카드 기반 서명에서 서명 필드를 사용하는 데에는 본질적인 제한이 없습니다. 그러나 선택한 서명 필드 위치가 중요한 문서 내용을 가리지 않도록 하는 것이 중요합니다.

#### 질문: 서명 필드를 사용한 스마트 카드 기반 서명을 구현하기 위한 추가 지원이나 도움말은 어디에서 찾을 수 있나요?

답변: 추가적인 지침과 지원이 필요한 경우 공식 Aspose.PDF 문서와 커뮤니티 포럼을 참조할 수 있습니다. 이러한 포럼에서는 안전한 디지털 서명을 구현하기 위한 귀중한 통찰력과 솔루션을 제공합니다.