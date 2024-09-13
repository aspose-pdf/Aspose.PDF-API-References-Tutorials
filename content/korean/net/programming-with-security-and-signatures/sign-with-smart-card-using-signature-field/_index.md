---
title: 서명 필드를 사용하여 스마트 카드로 서명
linktitle: 서명 필드를 사용하여 스마트 카드로 서명
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 스마트 카드를 사용하여 PDF에 안전하게 서명하는 방법을 알아보세요. 쉬운 구현을 위한 단계별 가이드를 따르세요.
type: docs
weight: 120
url: /ko/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## 소개

오늘날의 디지털 세계에서 문서 보안은 그 어느 때보다 중요합니다. 개발자, 사업주 또는 민감한 정보를 다루는 사람이든 PDF에 전자적으로 서명하는 방법을 알면 시간을 절약하고 문서가 인증되었는지 확인할 수 있습니다. 이 가이드에서는 Aspose.PDF for .NET을 사용하여 스마트 카드와 서명 필드를 사용하여 PDF에 서명하는 과정을 안내합니다. 

## 필수 조건

서명 과정의 핵심을 파헤치기 전에, 시작하는 데 필요한 모든 것이 있는지 확인해 보겠습니다. 필수 조건 체크리스트는 다음과 같습니다.

1. .NET용 Aspose.PDF: .NET 환경에 Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[대지](https://releases.aspose.com/pdf/net/).

2. Visual Studio: .NET 코드를 작성하고 실행하려면 IDE가 필요합니다. Visual Studio Community Edition은 훌륭한 무료 옵션입니다.

3. 스마트 카드: PDF에 서명하는 데 필수적입니다. 스마트 카드 리더와 필요한 인증서가 컴퓨터에 설치되어 있는지 확인하세요.

4. 기본 C# 지식: C# 프로그래밍에 대한 지식은 우리가 사용할 코드 조각을 이해하는 데 도움이 될 것입니다.

5. 샘플 PDF 문서: 테스트를 위해 샘플 PDF 문서를 준비하세요. 빈 PDF를 만들거나 기존 PDF를 사용할 수 있습니다.

## 패키지 가져오기

코딩을 시작하기 전에 필요한 패키지를 임포트해 보겠습니다. C# 파일에 다음 네임스페이스를 포함해야 합니다.

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

이러한 네임스페이스를 사용하면 PDF 작업과 디지털 서명 처리에 필요한 클래스와 메서드에 액세스할 수 있습니다.

## 스마트 카드로 PDF에 서명하는 단계별 가이드

이제 전제 조건을 정리했으니 서명 프로세스를 관리 가능한 단계로 나누어 보겠습니다. 각 단계를 자세히 살펴보고, 후드 아래에서 무슨 일이 일어나고 있는지 이해하도록 하겠습니다.

### 1단계: 문서 디렉토리 설정

해결 방법: 문서 디렉토리의 경로를 정의하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 설명: 바꾸기`"YOUR DOCUMENTS DIRECTORY"` PDF 파일이 있는 실제 경로와 함께. 여기서 빈 PDF를 읽고 서명된 문서를 저장합니다.

### 2단계: 빈 PDF 복사

해결 방법: 작업할 빈 PDF 사본을 만드세요.

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

 설명: 이 줄은 다음을 복사합니다.`blank.pdf`파일을 새 파일로 이름 지정`externalSignature1.pdf` . 그`true` 매개변수는 파일이 이미 존재하는 경우 덮어쓰기를 허용합니다.

### 3단계: PDF 문서 열기

수행 방법: 복사한 PDF를 열어 읽고 쓰세요.

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        // 추가 단계는 여기에 있습니다.
    }
}
```

 설명: 우리는 ~를 사용합니다`FileStream` PDF 파일을 열려면.`Document` Aspose.PDF의 클래스를 사용하면 PDF 콘텐츠를 조작할 수 있습니다.

### 4단계: 서명 필드 만들기

해결 방법: 서명이 배치될 PDF에 서명 필드를 정의합니다.

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

 설명: 여기서 우리는 다음을 생성합니다.`SignatureField` PDF의 두 번째 페이지(페이지 인덱스는 1부터 시작)에 있습니다.`Rectangle` 서명 필드의 위치와 크기를 정의합니다.

### 5단계: 스마트 카드 인증서 저장소에 액세스

해결 방법: 인증서 저장소를 열어 스마트 카드 인증서를 선택하세요.

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

설명: 현재 사용자의 인증서 저장소에 액세스합니다. 여기에 스마트 카드 인증서가 저장됩니다.

### 6단계: 인증서 선택

해결 방법: 사용자에게 저장소에서 인증서를 선택하라는 메시지를 표시합니다.

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

설명: 이 줄은 인증서를 선택할 수 있는 대화 상자를 엽니다. 스마트 카드와 관련된 인증서를 선택할 수 있습니다.

### 7단계: 외부 서명 만들기

 수행 방법: 인스턴스를 만듭니다.`ExternalSignature` 선택된 인증서를 사용합니다.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

 설명: 우리는 초기화합니다`ExternalSignature` 선택한 인증서로. 또한 권한, 서명 이유, 연락처 정보를 설정할 수 있습니다.

### 8단계: 문서에 서명 필드 추가

해결 방법: 문서에 서명 필드를 추가합니다.

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

설명: 서명 필드에 이름을 지정하고 문서의 첫 페이지에 추가합니다. 이렇게 하면 PDF가 서명을 위해 준비됩니다.

### 9단계: 문서 서명

해결 방법: 외부 서명을 사용하여 PDF에 서명하세요.

```csharp
field1.Sign(externalSignature);
doc.Save();
```

설명: 이 줄은 외부 서명을 사용하여 문서에 서명하고 PDF에 변경 사항을 저장합니다. 이제 문서가 서명되었습니다!

### 10단계: 서명 확인

해결 방법: 서명이 유효한지 확인하세요.

```csharp
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

설명: 우리는 인스턴스를 생성합니다`PdfFileSignature` 문서의 서명을 검증합니다. 서명이 유효하지 않으면 예외가 발생합니다.

## 결론

축하합니다! 방금 Aspose.PDF for .NET을 사용하여 스마트 카드와 서명 필드를 사용하여 PDF 문서에 서명하는 방법을 배웠습니다. 이 프로세스는 문서를 보호할 뿐만 아니라 진위성을 보장하여 오늘날의 디지털 환경에서 필수적인 기술입니다. 계약서, 송장 또는 기타 중요한 문서에 서명하든 디지털 서명을 구현하는 방법을 알면 시간을 절약하고 마음의 평화를 얻을 수 있습니다.

## 자주 묻는 질문

### .NET용 Aspose.PDF란 무엇인가요?
.NET용 Aspose.PDF는 개발자가 .NET 애플리케이션에서 PDF 문서를 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다.

### PDF에 서명하려면 스마트 카드가 필요한가요?
네, 디지털 인증서로 PDF에 안전하게 서명하려면 스마트 카드가 필요합니다.

### Aspose.PDF를 무료로 사용할 수 있나요?
 Aspose.PDF는 무료 평가판을 제공하며 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### 서명된 PDF를 어떻게 검증할 수 있나요?
 당신은 사용할 수 있습니다`PdfFileSignature` Aspose.PDF의 클래스를 사용하여 PDF 문서의 서명을 확인합니다.

### Aspose.PDF에 대한 더 많은 문서는 어디에서 찾을 수 있나요?
 확인할 수 있습니다[Aspose.PDF 문서](https://reference.aspose.com/pdf/net/) 자세한 내용과 예를 확인하세요.