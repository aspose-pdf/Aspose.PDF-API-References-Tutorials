---
title: SVG 크기 가져오기
linktitle: SVG 크기 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 SVG 크기를 얻는 방법에 대한 단계별 가이드입니다.
type: docs
weight: 40
url: /ko/net/document-conversion/get-svg-dimensions/
---
## 소개
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 SVG 파일의 크기를 얻는 과정을 안내합니다. SVG(Scalable Vector Graphics)는 벡터 그래픽을 표현하는 데 사용되는 XML 기반 이미지 형식입니다. 아래 단계를 사용하면 SVG 파일의 크기를 가져와 PDF로 저장할 수 있습니다.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: SVG 파일 로드
이 단계에서는 .NET용 Aspose.PDF를 사용하여 SVG 파일을 로드합니다. 아래 코드를 따르십시오.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` SVG 파일이 있는 실제 디렉토리를 사용합니다.

## 2단계: 페이지 크기 조정
이제 SVG 파일을 로드했으므로 SVG 콘텐츠에 맞게 페이지 크기를 조정할 수 있습니다. 다음 코드를 사용하세요.

```csharp
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
```

위의 코드는 페이지 여백을 0으로 설정하여 SVG 콘텐츠에 따라 페이지 크기를 조정할 수 있도록 합니다.

## 3단계: 결과 PDF 저장
페이지 크기를 조정한 후 이제 결과 PDF 문서를 저장할 수 있습니다. 마지막 단계는 다음과 같습니다.

```csharp
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 출력 PDF 파일을 저장하려는 원하는 디렉토리를 사용하십시오.
  
### .NET용 Aspose.PDF를 사용하여 SVG 치수 가져오기에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

var loadopt = new SvgLoadOptions();
loadopt.AdjustPageSize = true;
var svgDoc = new Document(dataDir + "GetSVGDimensions.svg", loadopt);
svgDoc.Pages[1].PageInfo.Margin.Top = 0;
svgDoc.Pages[1].PageInfo.Margin.Left = 0;
svgDoc.Pages[1].PageInfo.Margin.Bottom = 0;
svgDoc.Pages[1].PageInfo.Margin.Right = 0;
svgDoc.Save(dataDir + "GetSVGDimensions_out.pdf");
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 SVG 파일의 크기를 얻는 단계별 프로세스를 다루었습니다. 위에 설명된 지침을 따르면 이제 SVG 파일의 크기를 가져와 PDF 형식으로 저장할 수 있습니다. 이 기능은 벡터 그래픽의 크기를 측정해야 할 때 유용할 수 있습니다.

### FAQ

#### 질문: SVG란 무엇입니까?

A: SVG(Scalable Vector Graphics)는 벡터 그래픽을 표현하는 데 사용되는 XML 기반 이미지 형식입니다. 래스터 이미지와 달리 SVG 파일은 해상도에 독립적이며 품질 저하 없이 크기를 조정할 수 있습니다. SVG는 웹에서 그래픽을 표시하는 데 널리 사용되며 쉽게 편집하고 조작할 수 있습니다.

#### Q: SVG를 PDF로 변환하기 위해 .NET용 Aspose.PDF를 사용하는 이유는 무엇입니까?

A: .NET용 Aspose.PDF는 SVG 파일을 처리하고 PDF 형식으로 변환하는 안정적이고 효율적인 방법을 제공합니다. PDF에서 정확한 표현을 보장하기 위해 페이지 크기, 여백 및 기타 속성을 조정하는 등 변환 프로세스를 사용자 정의하는 다양한 옵션과 설정을 제공합니다.

#### Q: 복잡한 그래픽과 텍스트가 포함된 SVG 파일을 변환할 수 있나요?

A: 예, .NET용 Aspose.PDF는 복잡한 그래픽, 텍스트 및 벡터 요소가 포함된 SVG 파일을 처리할 수 있습니다. 변환 프로세스 중에 SVG 콘텐츠의 세부 사항과 품질을 정확하게 유지하여 고품질 PDF 문서를 생성합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 SVG 파일에서 텍스트를 추출할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하면 SVG 파일에서 텍스트를 추출할 수 있습니다. 라이브러리의 텍스트 추출 기능을 사용하여 SVG에서 텍스트 요소를 추출하고 추가 처리를 위해 별도로 저장할 수 있습니다.