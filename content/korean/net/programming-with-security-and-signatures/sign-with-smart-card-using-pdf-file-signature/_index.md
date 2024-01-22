---
title: PDF 파일 서명을 사용하여 스마트 카드로 서명
linktitle: PDF 파일 서명을 사용하여 스마트 카드로 서명
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 스마트 카드로 PDF 파일에 안전하게 서명하세요.
type: docs
weight: 110
url: /ko/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
스마트 카드를 사용한 디지털 서명은 PDF 파일에 서명하는 안전한 방법입니다. .NET용 Aspose.PDF를 사용하면 다음 소스 코드에 따라 스마트 카드를 사용하여 PDF 파일에 쉽게 서명할 수 있습니다.

## 1단계: 필수 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 가져오기 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 서명하려는 PDF 파일이 포함된 폴더의 경로를 지정해야 합니다. 바꾸다`"YOUR DOCUMENTS DIRECTORY"`다음 코드에 문서 폴더의 실제 경로를 입력하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 3단계: PDF 문서 로드

이제 다음 코드를 사용하여 서명할 PDF 문서를 로드합니다.

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## 4단계: 스마트 카드로 서명 수행

 이 단계에서는 다음을 사용하여 스마트 카드로 서명을 수행합니다.`PdfFileSignature` 의 수업`Facades`도서관. Windows 인증서 저장소에서 스마트 카드 인증서를 선택하고 필요한 서명 정보를 지정합니다. 해당 코드는 다음과 같습니다.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     // 매장에서 인증서를 선택하세요.
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## 5단계: 서명 확인

 마지막으로 다음을 사용하여 서명된 PDF 파일의 서명을 확인합니다.`PdfFileSignature` 수업. 서명 이름을 받아 하나씩 확인합니다. 서명 확인에 실패하면 예외가 발생합니다. 해당 코드는 다음과 같습니다.

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

### .NET용 Aspose.PDF를 사용하여 PDF 파일 서명을 사용하여 스마트 카드로 서명하기 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	// Windows 인증서 저장소에서 인증서 선택으로 서명
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	// 저장소에서 인증서를 수동으로 선택했습니다.
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

축하합니다! 이제 Aspose.PDF for .NET을 사용하여 스마트 카드로 PDF 파일에 서명하는 단계별 가이드가 제공됩니다. 이 코드를 사용하여 PDF 문서에 보안 디지털 서명을 추가할 수 있습니다.

고급 디지털 서명 및 인증서 관리 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.

### FAQ

#### Q: 스마트 카드로 PDF 파일에 서명하는 것을 고려해야 하는 이유는 무엇입니까?

답변: 스마트 카드로 PDF 파일에 서명하면 문서의 신뢰성과 무결성이 보장되어 보안이 강화됩니다. 스마트 카드 기반 서명은 더 높은 수준의 신뢰와 규정 준수를 제공합니다.

#### Q: 스마트 카드 기반 디지털 서명은 어떻게 작동합니까?

답변: 스마트 카드 기반 디지털 서명에는 스마트 카드에 저장된 암호화 키를 사용하여 고유한 디지털 서명을 생성하는 작업이 포함됩니다. 이 서명은 PDF 파일에 첨부되어 수신자가 문서의 원본과 무결성을 확인할 수 있도록 합니다.

#### Q: 스마트 카드 기반 서명에서 Aspose.PDF for .NET의 역할은 무엇입니까?

A: .NET용 Aspose.PDF는 PDF 파일의 스마트 카드 기반 디지털 서명을 용이하게 하는 포괄적인 도구 및 라이브러리 세트를 제공합니다. 이는 프로세스를 단순화하고 안전한 문서 서명을 보장합니다.

#### Q: 서명을 위해 특정 스마트 카드 인증서를 선택할 수 있습니까?

A: 예, 서명을 위해 Windows 인증서 저장소에서 특정 스마트 카드 인증서를 선택할 수 있습니다. .NET용 Aspose.PDF를 사용하면 인증서 선택을 애플리케이션에 원활하게 통합할 수 있습니다.

#### Q: 제공된 소스 코드는 스마트 카드 기반 서명을 어떻게 처리합니까?

답변: 소스 코드는 PDF 문서 바인딩, 스마트 카드 인증서 선택, 서명 정보 지정 및 디지털 서명 생성 방법을 보여줍니다. 또한 서명의 유효성을 확인하는 방법도 보여줍니다.

#### Q: 단일 PDF 파일에 스마트 카드를 사용하여 여러 서명을 적용할 수 있습니까?

A: 물론, 단일 PDF 파일에 여러 스마트 카드 기반 서명을 적용할 수 있습니다. 각 서명은 고유하며 문서의 전반적인 보안에 기여합니다.

#### Q: 확인 단계에서 서명 확인에 실패하면 어떻게 되나요?

A: 서명 확인에 실패하면 서명이 유효하지 않음을 나타내는 예외가 발생합니다. 이렇게 하면 유효하고 신뢰할 수 있는 서명만 허용됩니다.

#### Q: 스마트 카드 기반 서명은 모든 유형의 PDF 문서와 호환됩니까?

A: 예, 스마트 카드 기반 서명은 모든 유형의 PDF 문서와 호환됩니다. 양식, 보고서 등을 포함한 다양한 유형의 PDF 파일에 디지털 서명을 적용할 수 있습니다.

#### Q: 고급 디지털 서명 및 인증서 관리에 대해 자세히 알아보려면 어떻게 해야 합니까?

A: 고급 디지털 서명 기능, 인증서 관리 및 문서 보안 보장을 위한 모범 사례에 대한 자세한 통찰력을 얻으려면 공식 Aspose.PDF 문서를 살펴보세요.

#### Q: 스마트 카드 기반 서명 구현에 대한 추가 지원은 어디에서 찾을 수 있습니까?

A: 추가 지침 및 지원이 필요하면 Aspose.PDF 커뮤니티 포럼에 문의하거나 스마트 카드 기반 서명에 대한 포괄적인 정보에 대한 설명서를 참조하세요.