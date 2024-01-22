---
title: SVG를 PDF로
linktitle: SVG를 PDF로
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 SVG를 PDF로 쉽고 빠르게 변환합니다.
type: docs
weight: 280
url: /ko/net/document-conversion/svg-to-pdf/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 SVG 파일을 PDF 파일로 변환하는 단계를 안내합니다. Aspose.PDF는 콘텐츠 품질과 레이아웃을 유지하면서 SVG 파일을 PDF로 변환하기 위한 간단하고 효과적인 솔루션을 제공합니다. 이 변환을 수행하려면 아래 단계를 따르십시오.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: SVG 파일 로드
첫 번째 단계는 SVG 파일을`Document` SVG 로드 옵션을 사용하는 객체(`SvgLoadOptions`). 다음 코드를 사용하세요.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// SVG 로드 옵션을 사용하여 LoadOption 객체 인스턴스화
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// 문서 객체 생성
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` SVG 파일이 있는 실제 디렉토리를 사용합니다.

## 2단계: PDF로 변환
 두 번째 단계는 다음을 사용하여 SVG 문서를 PDF 문서로 변환하는 것입니다.`Save` 의 방법`Document` 물체. 다음 코드를 사용하세요.

```csharp
// 결과 PDF 문서를 저장
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

결과 PDF 파일에 대해 원하는 경로와 파일 이름을 지정하십시오.

### .NET용 Aspose.PDF를 사용하여 SVG를 PDF로 변환하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// SVG 로드 옵션을 사용하여 LoadOption 객체 인스턴스화
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

// 문서 객체 생성
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

// 결과 PDF 문서 저장
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 SVG 파일을 PDF 파일로 변환하는 방법을 배웠습니다. 위에 제공된 단계를 따르면 이 변환을 쉽게 수행할 수 있습니다. 이 방법을 사용하여 SVG 파일을 PDF로 변환하고 Aspose.PDF의 유연성과 품질을 즐기세요.

### FAQ

#### Q: .NET용 Aspose.PDF이 무엇인가요?

A: .NET용 Aspose.PDF는 개발자가 C# 애플리케이션에서 PDF 문서 작업을 할 수 있게 해주는 강력한 라이브러리입니다. SVG 파일을 PDF로 변환하는 등 다양한 기능을 제공합니다.

#### Q: SVG 파일을 PDF로 변환하려는 이유는 무엇입니까?

A: SVG(Scalable Vector Graphics) 파일은 일반적으로 웹의 벡터 그래픽에 사용됩니다. SVG 파일을 PDF 형식으로 변환하면 그래픽 콘텐츠를 더 쉽게 공유, 인쇄 및 포함할 수 있습니다.

#### Q: .NET용 Aspose.PDF를 사용하여 SVG 파일을 로드하고 PDF로 변환하려면 어떻게 해야 합니까?

 A: SVG 파일을 로드하려면 다음을 사용할 수 있습니다.`SvgLoadOptions` SVG 로드 옵션을 지정하는 클래스입니다. 그런 다음`Document` 개체를 선택하고 SVG 파일을 해당 개체에 로드합니다. 마지막으로`Save` 의 방법`Document` SVG를 PDF로 변환하고 저장하는 개체입니다.

#### Q: 변환 중에 출력 PDF를 사용자 정의할 수 있습니까?

A: 예, 변환 프로세스 중에 출력 PDF를 사용자 정의할 수 있습니다. .NET용 Aspose.PDF는 PDF 문서의 모양과 레이아웃을 제어하는 다양한 옵션과 속성을 제공합니다.

#### Q: 결과 PDF에서 SVG의 콘텐츠 품질이 유지됩니까?

A: 예, .NET용 Aspose.PDF는 SVG에서 PDF로 변환하는 동안 콘텐츠 품질과 레이아웃을 보존하여 형식 간 원활한 전환을 보장합니다.