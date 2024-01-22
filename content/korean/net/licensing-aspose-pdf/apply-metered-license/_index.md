---
title: PDF 파일에서 계량 라이센스 키 구성
linktitle: PDF 파일에서 계량 라이센스 키 구성
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 계량형 라이센스 키를 설정하고 고급 기능을 활용하는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/licensing-aspose-pdf/configure-metered-license/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일에 계량형 라이센스 키를 설정하는 방법을 단계별로 안내합니다. 계량 라이선스를 사용하면 실제 소비량을 기준으로 Aspose.PDF의 고급 기능을 사용할 수 있습니다.

### 1단계: 라이센스 키 구성

제공된 소스 코드에서 계량 라이선스의 공개 키와 개인 키를 지정해야 합니다. 교체 "*****" 값을 자신만의 키로 사용하세요. 이 키는 Aspose에서 측정 라이선스를 구매할 때 제공됩니다.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### 2단계: 문서 로드

 다음을 사용하여 디스크에서 PDF 문서를 로드합니다.`Document` Aspose.PDF의 클래스입니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### 3단계: 문서 페이지 수 가져오기

 사용`Count` 의 재산`Pages` 문서의 총 페이지 수를 가져오는 컬렉션입니다.

```csharp
Console.WriteLine(doc.Pages.Count);
```

### .NET용 Aspose.PDF를 사용하여 측정 라이센스 구성의 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 측정된 공개 및 개인 키 설정
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
//setMeteredKey 속성에 액세스하고 공개 키와 개인 키를 매개변수로 전달합니다.
metered.SetMeteredKey("*****", "*****");
// 디스크에서 문서를 로드합니다.
Document doc = new Document(dataDir + "input.pdf");
//문서의 페이지 수를 가져옵니다
Console.WriteLine(doc.Pages.Count);

```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 계량 라이센스를 설정하는 방법을 설명했습니다. 계량 라이선스를 사용하면 실제 사용량을 기반으로 Aspose.PDF의 고급 기능을 활용할 수 있습니다. Aspose.PDF의 모든 기능을 사용하려면 유효한 라이센스 키를 제공해야 합니다.

### PDF 파일의 계량 라이센스 키 구성에 대한 FAQ

#### Q: Aspose.PDF의 계량 라이선스란 무엇입니까?

A: Aspose.PDF의 계량형 라이선스는 고정된 라이선스 비용이 아닌 실제 기능 소비에 따라 비용을 지불할 수 있는 라이선스 모델입니다. 사용한 만큼만 비용을 지불하면서 Aspose.PDF의 고급 기능을 사용할 수 있습니다.

#### Q: Aspose.PDF에 계량 라이선스를 사용해야 하는 이유는 무엇입니까?

A: 계량형 라이선스를 사용하면 비용 절감과 유연성이 제공됩니다. 사용하는 기능에 대해서만 비용을 지불하므로 수요가 다양한 프로젝트에 적합합니다. 사전 라이센스 비용이 필요하지 않으며 고급 PDF 기능에 액세스할 수 있습니다.

#### Q: 계량형 라이센스 키를 얻으려면 어떻게 해야 합니까?

A: Aspose에서 계량 라이선스를 구매하면 한 쌍의 공개 키와 개인 키를 받게 됩니다. 이 키는 Aspose.PDF 애플리케이션에 대한 계량 라이선스를 인증하고 활성화하는 데 사용됩니다.

#### Q: .NET용 Aspose.PDF에서 계량 라이센스 키를 어떻게 구성합니까?

 A: 계량 라이센스 키를 구성하려면 다음을 사용하십시오.`SetMeteredKey` 의 방법`Aspose.Pdf.Metered` 수업. 바꾸다`"PUBLIC_KEY"` 그리고`"PRIVATE_KEY"` 실제 키로.

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서를 어떻게 로드합니까?

 A: 디스크에서 PDF 문서를 로드하려면`Document` Aspose.PDF 클래스를 선택하고 파일 경로를 제공하세요.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

#### Q: PDF 문서의 총 페이지 수를 어떻게 알 수 있나요?

 A: PDF 문서의 총 페이지 수를 얻으려면`Count` 의 재산`Pages` 수집.

```csharp
int pageCount = doc.Pages.Count;
Console.WriteLine("Total pages: " + pageCount);
```

#### Q: 다른 Aspose 제품에 계량 라이선스를 사용할 수 있나요?

A: 예, 다양한 Aspose 제품에 대해 계량형 라이선스를 사용할 수 있으므로 다양한 기능에 대한 사용량에 따라 비용을 지불할 수 있습니다.

#### Q: 측정 라이선스는 모든 유형의 프로젝트에 적합합니까?

A: 측정 라이선스는 다양한 기능을 사용하는 프로젝트에 적합합니다. 지속적으로 높은 기능을 사용하는 프로젝트에는 비용 효율적이지 않을 수 있습니다.

#### Q: Aspose.PDF 계량 라이선스에 대한 자세한 정보는 어디서 찾을 수 있나요?

 A: 측정 라이선스, 가격 및 혜택에 대한 자세한 내용을 보려면 다음을 방문하세요.[Aspose.PDF 계량 라이센스](https://purchase.aspose.com/pricing/pdf/net) 페이지.

#### Q: 계량 라이센스 키의 보안을 어떻게 보장합니까?

A: 계량형 라이센스 키는 인증에 사용되며 민감한 정보입니다. 기밀로 유지되고 공개적으로 공유되지 않도록 하세요.

#### Q: 기존 라이선스와 종량제 라이선스 간에 전환할 수 있나요?

A: 예, 프로젝트 요구 사항에 따라 Aspose.PDF에 대한 기존 라이선스와 계량 라이선스 간에 전환할 수 있습니다.

#### Q: 측정 라이센스를 구매하기 전에 평가판을 사용할 수 있습니까?

 A: 예, 다음을 시도해 볼 수 있습니다.[무료 평가판](https://products.aspose.com/pdf/net) 측정 라이센스를 구매하기 전에 Aspose.PDF의 특징과 기능을 평가해 보세요.

#### Q: 계량형 라이센스 키를 얼마나 자주 구성해야 합니까?

A: 측정 라이센스 키는 애플리케이션이 시작될 때 한 번만 구성하면 됩니다. 이는 애플리케이션 런타임 전반에 걸쳐 고급 기능에 대한 액세스를 제공합니다.

#### Q: 기존 애플리케이션에 종량제 라이선스를 적용할 수 있습니까?

A: 예, 기존 Aspose.PDF 애플리케이션에 계량 라이선스를 통합하여 이점을 누릴 수 있습니다.