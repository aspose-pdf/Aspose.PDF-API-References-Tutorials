---
title: HTML에서 변환 후 하이퍼링크 제거
linktitle: HTML에서 변환 후 하이퍼링크 제거
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드에서는 Aspose.PDF for .NET을 사용하여 PDF로 변환한 후 HTML 문서에서 하이퍼링크를 제거하는 방법을 알아봅니다.
type: docs
weight: 250
url: /ko/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## 소개

디지털 시대에 HTML 문서를 PDF로 변환하는 것은 흔한 작업입니다. 그러나 때로는 가독성을 향상시키거나 원치 않는 탐색을 방지하는 등 다양한 이유로 변환된 PDF에서 하이퍼링크를 제거하고 싶을 수 있습니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 이를 달성하는 방법을 살펴보겠습니다. 

## 필수 조건

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Visual Studio: 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요. 이것이 개발 환경이 됩니다.
2.  .NET용 Aspose.PDF: Aspose.PDF 라이브러리가 필요합니다. 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
3. C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 코드를 더 잘 이해하는 데 도움이 됩니다.

## 패키지 가져오기

시작하려면 C# 프로젝트에서 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.

1. Visual Studio 프로젝트를 엽니다.
2. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택합니다.
3.  검색`Aspose.PDF` 설치하세요.

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

이제 모든 것이 설정되었으니, HTML 파일을 PDF로 변환한 후 하이퍼링크를 제거하는 과정을 살펴보겠습니다.

## 1단계: 문서 디렉토리 설정

먼저, 문서 디렉토리 경로를 지정해야 합니다. 여기가 HTML 파일이 있는 위치이며 출력 PDF가 저장되는 위치입니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` HTML 파일이 저장된 실제 경로를 사용합니다.

## 2단계: HTML 문서 로드

 다음으로, 다음을 사용하여 HTML 문서를 로드합니다.`Document` Aspose.PDF의 클래스입니다. 이 클래스를 사용하면 PDF 문서를 쉽게 작업할 수 있습니다.

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

 여기서 우리는 HTML 파일을 로드하고 있습니다`SampleHtmlFile.html`. 이 파일이 지정된 디렉토리에 있는지 확인하세요.

## 3단계: 문서를 메모리 스트림에 저장

주석 처리를 시작하기 전에 문서를 메모리 스트림에 저장해야 합니다. 이 단계는 문서를 추가 조작할 수 있도록 준비하기 때문에 중요합니다.

```csharp
doc.Save(new MemoryStream());
```

이 줄은 문서를 메모리에 저장하여 디스크에 쓰지 않고도 작업할 수 있게 해줍니다.

## 4단계: 주석 반복

이제 문서의 주석을 반복합니다. 주석은 링크, 댓글, 하이라이트와 같은 요소입니다. 우리는 특히 링크 주석에 관심이 있습니다.

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        // 링크 주석 처리
    }
}
```

이 루프에서 우리는 주석 유형이 링크인지 확인합니다. 그렇다면 다음 단계로 진행합니다.

## 5단계: 하이퍼링크 작업 제거

각 링크 주석에 대해 하이퍼링크 동작이 있는지 확인해야 합니다. 하이퍼링크 동작이 있으면 URI를 빈 문자열로 설정하여 하이퍼링크를 제거합니다.

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

이 코드 조각은 하이퍼링크 동작이 효과적으로 제거되도록 보장합니다.

## 6단계: 텍스트 조각 흡수

다음으로, 링크 주석과 관련된 텍스트 조각을 흡수합니다. 이를 통해 텍스트 모양을 조작할 수 있습니다.

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

 여기서 우리는 다음을 생성합니다.`TextFragmentAbsorber` 그리고 검색 옵션을 주석의 사각형으로 설정합니다. 이렇게 하면 링크된 텍스트를 찾는 데 도움이 됩니다.

## 7단계: 텍스트 모양 수정

텍스트 조각을 얻으면 모양을 수정할 수 있습니다. 이 경우 밑줄을 제거하고 텍스트 색상을 검은색으로 변경합니다.

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

이 단계에서는 하이퍼링크 스타일을 제거하여 텍스트의 가독성을 향상합니다.

## 8단계: 주석 삭제

텍스트를 수정한 후에는 문서에서 링크 주석을 안전하게 삭제할 수 있습니다.

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

이 줄은 PDF에서 하이퍼링크를 제거하여 최종 출력물에 더 이상 존재하지 않도록 합니다.

## 9단계: 수정된 문서 저장

마지막으로, 수정된 문서를 새 PDF 파일에 저장해야 합니다. 이것은 프로세스의 마지막 단계입니다.

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

 이 줄은 하이퍼링크를 제거하여 문서를 저장하고 이름이 ''인 새 PDF 파일''을 만듭니다.`RemoveHyperlinksFromText_out.pdf`.

## 결론

이제 아시죠! Aspose.PDF for .NET을 사용하여 HTML 문서를 PDF로 변환한 후 하이퍼링크를 성공적으로 제거했습니다. 이 프로세스는 PDF의 가독성을 향상시킬 뿐만 아니라 제시하는 콘텐츠를 제어할 수 있게 해줍니다. 

## 자주 묻는 질문

### 모든 PDF 문서에서 하이퍼링크를 제거할 수 있나요?
네, Aspose.PDF for .NET을 사용하면 모든 PDF 문서에서 하이퍼링크를 제거할 수 있습니다.

### Aspose.PDF는 무료로 사용할 수 있나요?
 Aspose.PDF는 무료 평가판을 제공하지만 모든 기능을 사용하려면 라이선스를 구매해야 합니다.[구매 페이지](https://purchase.aspose.com/buy).

### Aspose.PDF를 사용하는 동안 문제가 발생하면 어떻게 해야 하나요?
 당신은에 대한 도움을 구할 수 있습니다[지원 포럼](https://forum.aspose.com/c/pdf/10).

### Aspose를 사용하여 다른 파일 형식을 PDF로 변환할 수 있나요?
네, Aspose는 다양한 파일 형식을 PDF로 변환하는 것을 지원합니다.

### .NET용 Aspose.PDF를 어디에서 다운로드할 수 있나요?
 여기에서 다운로드할 수 있습니다[다운로드 링크](https://releases.aspose.com/pdf/net/).