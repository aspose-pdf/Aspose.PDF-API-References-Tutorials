---
title: 그림 구조 요소
linktitle: 그림 구조 요소
second_title: .NET API 참조를 위한 Aspose.PDF
description: 단계별 튜토리얼을 따라 .NET용 Aspose.PDF에서 일러스트레이션 요소가 포함된 구조화된 PDF를 만들어 보세요.
type: docs
weight: 100
url: /ko/net/programming-with-tagged-pdf/illustration-structure-elements/
---
## 소개

.NET 애플리케이션에서 멋지고 구조화된 PDF를 만들 준비가 되셨나요? 태그가 필요한 콘텐츠를 필요로 하는 프로젝트를 진행 중이든, 단순히 PDF를 한 단계 업그레이드하고 싶든, Aspose.PDF for .NET에는 일러스트레이션 구조 요소로 작업하는 데 필요한 모든 도구가 있습니다. 이 튜토리얼에서는 가장 복잡한 부분도 매우 명확하게 보이도록 단계별로 프로세스를 안내해 드리겠습니다.

## 필수 조건

자세한 내용을 살펴보기에 앞서, 순조롭게 따라갈 수 있도록 필요한 모든 것이 있는지 확인해 보겠습니다.

1.  .NET용 Aspose.PDF – Aspose.PDF 라이브러리가 설치되어 있어야 합니다. 아직 없으신가요?[여기서 다운로드하세요](https://releases.aspose.com/pdf/net/) . 먼저 테스트하고 싶다면 다음을 잡을 수 있습니다.[무료 체험](https://releases.aspose.com/).
2. Visual Studio – C#으로 코딩할 것이므로 Visual Studio나 호환되는 IDE가 설치되어 있는지 확인하세요.
3. .NET Framework – Aspose.PDF for .NET과 호환되는 버전이 있는지 확인하세요.
4.  임시 라이센스 – Aspose.PDF는 평가판 모드에서는 몇 가지 제한 사항이 있으므로 다음을 받으십시오.[임시 면허](https://purchase.aspose.com/temporary-license/) 모든 기능을 사용하려면.

그게 전부입니다! 이제 필요한 네임스페이스를 가져와서 코딩을 진행해 보겠습니다.

## 네임스페이스 가져오기

```csharp
using Aspose.Pdf.LogicalStructure;
using Aspose.Pdf.Tagged;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이것이 기초입니다. 이러한 네임스페이스를 가져오지 않으면 Aspose.PDF 기능과 상호 작용하거나 태그가 지정된 PDF 콘텐츠를 처리할 수 없습니다. 이제 단계를 자세히 분석해 보겠습니다.

## 1단계: 문서 디렉토리 설정

PDF를 만들기 전에 파일이 저장될 문서 디렉토리 경로를 지정해야 합니다. 이는 이미지나 다른 자산이 저장되는 시스템의 폴더입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 이 단계는 간단하지만 필수적입니다. 작업할 파일을 어디에서 찾고 저장할지 프로그램에 알려주는 것입니다. PDF에 대한 홈 베이스를 갖는 것과 같습니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 컴퓨터의 실제 경로와 일치합니다.

## 2단계: 새 PDF 문서 만들기

이제 PDF 문서를 만들 시간입니다. 이 단계에서는 빈 PDF 문서를 시작하고, 이후 단계에서 수정하고 개선합니다.
 문서 만들기

```csharp
Document document = new Document();
```

이 줄은 모든 마법을 부립니다. 완전히 비어 있는 새 PDF 파일을 만들어서 사용자가 콘텐츠를 추가할 때까지 기다립니다. 새 캔버스를 여는 것으로 생각하세요.

## 3단계: 태그가 지정된 PDF 콘텐츠 액세스

일러스트레이션 구조 요소로 작업하려면 문서의 태그가 지정된 콘텐츠를 활용해야 합니다. 이를 통해 특정 태그를 정의하여 PDF를 보다 구조화하고 접근하기 쉽게 만들 수 있습니다.

```csharp
ITaggedContent taggedContent = document.TaggedContent;
```

 마법이 일어나는 곳은 바로 여기입니다!`TaggedContent` object는 PDF의 요소가 어떻게 해석되는지 정의할 수 있게 해줍니다. 접근성이나 구조로 작업하는 경우 이 단계는 매우 중요합니다.

## 4단계: 문서 제목 및 언어 설정

구조화된 PDF를 만들고 있으므로 제목과 언어를 정의하는 것이 필수적입니다. 이는 접근성을 높이는 데 도움이 될 뿐만 아니라 문서를 보다 전문적이고 검색하기 쉽게 만듭니다.

```csharp
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
```

제목과 언어를 지정하면 본질적으로 PDF에 개성을 부여하는 것입니다. 제목은 문서 속성에 표시되고 언어를 설정하면 화면 판독기 및 기타 접근성 도구와의 호환성이 보장됩니다.

## 5단계: 일러스트레이션(그림) 요소 만들기

이제 흥미로운 부분이 왔습니다. 일러스트레이션을 추가하는 것입니다! 이 경우 이미지, 대체 텍스트 설명 및 제목을 포함하는 그림 요소를 만듭니다.

```csharp
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
```

이 코드는 새로운 figure 요소를 생성하여 문서의 루트 요소에 추가합니다. 이것을 문서에 이미지 플레이스홀더를 추가하는 것으로 생각하세요.

## 6단계: 대체 텍스트, 제목 및 이미지 추가

PDF에 액세스할 수 있도록 하려면 대체 텍스트와 일러스트레이션 제목을 포함해야 합니다. 이미지도 첨부합니다.

```csharp
figure1.AlternativeText = "Figure One";
figure1.Title = "Image 1";
figure1.SetTag("Fig1");
figure1.SetImage(dataDir + "image.jpg");
```

 이것은 마지막 터치입니다. 우리는 이미지에 설명적인 대체 텍스트(화면 판독기에 유용함), 제목을 제공하고 실제 이미지 파일을 설정합니다.`SetTag`메서드는 그림에 태그를 붙여서 나중에 참조하기 쉽게 해줍니다.

 중요 참고 사항: 이미지 경로가 다음과 같은지 확인하십시오.`SetImage` 컴퓨터에 있는 유효한 이미지 파일을 가리킵니다.

## 7단계: 태그가 지정된 PDF 문서 저장

모든 콘텐츠가 추가되고 구조화되면 PDF를 저장할 시간입니다. 이 단계에서는 모든 것을 마무리하고 실제 파일을 생성합니다.

```csharp
document.Save(dataDir + "IllustrationStructureElements.pdf");
```

간단하죠? 이 명령은 여러분이 한 모든 작업을 가져와서 이전에 지정한 디렉토리에 새 PDF 파일을 만듭니다. 이제 폴더를 확인하면 짜잔! 일러스트레이션 요소가 있는 구조화된 PDF가 완성되었습니다!

## 결론

축하합니다! 방금 Aspose.PDF for .NET을 사용하여 일러스트레이션 구조 요소가 있는 태그가 지정된 PDF를 만드는 방법을 배웠습니다. 이 접근 방식은 PDF가 시각적으로 매력적일 뿐만 아니라 구조화되고 접근하기 쉬운지 확인합니다. 콘텐츠에 태그를 지정하고 대체 텍스트를 추가하면 보조 기술을 사용하는 사람을 포함한 모든 사람이 문서를 즐길 수 있습니다.

## 자주 묻는 질문

### 태그가 지정된 PDF 콘텐츠란 무엇입니까?
태그가 있는 PDF는 제목, 문단, 그림과 같은 다양한 요소를 식별하기 위한 태그나 라벨이 포함된 PDF로, 문서의 접근성을 높입니다.

### 대체 텍스트를 설정하면 어떻게 도움이 되나요?
대체 텍스트는 화면 판독기로 읽을 수 있는 이미지에 대한 설명을 제공하므로 시각 장애인 사용자의 접근성을 향상합니다.

### 태그가 지정된 PDF에 여러 개의 이미지를 추가할 수 있나요?
 네! 여러 개를 만들 수 있습니다.`FigureElement` 객체를 만들고 각각을 문서에 추가합니다. 이는 단일 이미지에서 한 것과 마찬가지입니다.

### Aspose.PDF for .NET을 사용하려면 라이선스가 필요합니까?
 예, Aspose.PDF는 유료 라이브러리이지만 다음을 얻을 수 있습니다.[임시 면허](https://purchase.aspose.com/temporary-license/) 또는 ~로 시작하세요[무료 체험](https://releases.aspose.com/).

### PDF를 만든 후에 그림 요소를 수정할 수 있나요?
PDF를 저장한 후에는 직접 수정할 수 없지만, Aspose.PDF를 사용하여 문서를 다시 열어 변경한 후 다시 저장할 수 있습니다.