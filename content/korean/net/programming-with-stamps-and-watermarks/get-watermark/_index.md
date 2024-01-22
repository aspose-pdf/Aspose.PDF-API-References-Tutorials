---
title: PDF 파일에서 워터마크 가져오기
linktitle: PDF 파일에서 워터마크 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 워터마크를 추출하는 방법을 알아보세요.
type: docs
weight: 100
url: /ko/net/programming-with-stamps-and-watermarks/get-watermark/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 워터마크를 얻는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 사용하여 특정 페이지의 아티팩트를 반복하고 워터마크 유형, 텍스트 및 위치를 가져오는 방법을 보여 드리겠습니다.

## 1단계: 환경 설정

시작하기 전에 다음 사항이 있는지 확인하세요.

- 설치된 .NET 개발 환경.
- .NET용 Aspose.PDF 라이브러리가 다운로드되어 프로젝트에서 참조됩니다.

## 2단계: PDF 문서 로드

첫 번째 단계는 기존 PDF 문서를 프로젝트에 로드하는 것입니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//PDF 문서 열기
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

"YOUR DOCUMENTS DIRECTORY"를 PDF 문서가 있는 디렉토리의 실제 경로로 바꾸십시오.

## 3단계: 워터마크 가져오기

이제 PDF 문서를 로드했으므로 특정 페이지 아티팩트를 반복하여 워터마크 정보를 얻을 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 아티팩트를 찾아보고 워터마크 하위 유형, 텍스트 및 위치를 가져옵니다.
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

위 코드는 PDF 문서의 첫 번째 페이지에 있는 모든 아티팩트를 반복하여 발견된 각 워터마크의 하위 유형, 텍스트 및 직사각형(위치)을 표시합니다.

### .NET용 Aspose.PDF를 사용하여 워터마크 가져오기의 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// 반복하여 욕조 유형, 텍스트 및 아티팩트 위치를 얻습니다.
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 PDF 문서에서 워터마크 정보를 얻는 방법을 배웠습니다. 이제 이 지식을 활용하여 PDF 문서의 워터마크를 분석하고 처리할 수 있습니다.

### PDF 파일에서 워터마크 가져오기에 대한 FAQ

#### Q: PDF 문서의 워터마크는 무엇이며, 해당 정보를 추출해야 하는 이유는 무엇입니까?

답변: PDF 문서의 워터마크는 문서 내용에 겹쳐지는 인식 가능한 이미지나 텍스트로, 종종 문서의 상태, 소유권 또는 기밀성을 나타냅니다. 워터마크 정보 추출은 문서 진위 분석, 문서 소스 식별 또는 워터마크 존재 여부에 따른 문서 처리에 유용할 수 있습니다.

#### Q: 제공된 C# 소스 코드는 PDF 파일에서 워터마크 정보를 추출하는 데 어떻게 도움이 됩니까?

 답변: 제공된 코드는 기존 PDF 문서를 로드하고, 특정 페이지의 아티팩트를 반복하고, 워터마크에 대한 정보를 추출하는 방법을 보여줍니다. 이 작업은`Subtype`, `Text` , 그리고`Rectangle` 각 아티팩트의 속성.

####  Q: 무엇을 하는가?`Subtype` property of an artifact represent?

 답:`Subtype` 아티팩트의 속성은 아티팩트의 유형을 나타냅니다. 워터마크의 경우 아티팩트가 워터마크임을 나타냅니다.

#### Q: 코드는 페이지에서 워터마크의 위치(사각형)를 어떻게 결정합니까?

 A: 코드는 다음을 사용합니다.`Rectangle` 워터마크의 위치를 결정하기 위한 아티팩트의 속성입니다. 그만큼`Rectangle` 속성은 페이지에 있는 아티팩트의 경계 사각형을 나타냅니다.

#### Q: 모양이나 색상 등 워터마크에 대한 추가 정보를 추출하기 위해 코드를 수정할 수 있습니까?

A: 예. 해당 정보가 사용 가능하고 사용 사례와 관련이 있는 경우 코드를 수정하여 모양이나 색상과 같은 아티팩트의 다른 속성에 액세스할 수 있습니다.

#### Q: 이 코드를 사용하여 PDF 문서의 여러 페이지에서 워터마크 정보를 추출할 수 있습니까?

A: 예, 루프의 페이지 인덱스를 변경하여 여러 페이지의 아티팩트에 액세스함으로써 여러 페이지의 아티팩트를 반복하도록 코드를 수정할 수 있습니다.

#### Q: 지정된 페이지에 워터마크가 없으면 어떻게 되나요?

A: 지정된 페이지에 워터마크가 없으면 루프가 실행되지 않고 워터마크 정보가 표시되지 않습니다.

#### Q: 추출된 워터마크 정보를 추가 처리에 어떻게 사용할 수 있나요?

A: 추출된 워터마크 정보는 워터마크 유무나 속성에 따른 특정 작업의 로깅, 분석, 보고, 자동화 등 다양한 목적으로 사용될 수 있습니다.

#### Q: PDF 문서에서 다른 유형의 아티팩트에 대한 정보를 추출하기 위해 이 코드를 수정할 수 있습니까?

A: 예, 유사한 접근 방식을 사용하여 해당 속성에 액세스함으로써 다른 유형의 아티팩트에 대한 정보를 추출하도록 코드를 수정할 수 있습니다.

#### Q: 가공물은 아니지만 PDF 콘텐츠의 일부인 워터마크에 어떻게 액세스할 수 있습니까?

A: 인공물이 아닌 워터마크는 이미지나 텍스트와 같은 PDF 콘텐츠 자체의 일부일 수 있습니다. 이러한 유형의 워터마크에 대한 정보를 추출하려면 PDF 콘텐츠를 분석하고 워터마크를 나타내는 특정 요소를 식별해야 할 수 있습니다.