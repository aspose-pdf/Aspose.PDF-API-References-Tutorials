---
title: PDF 파일에 숨겨진 텍스트 추가 및 검색
linktitle: PDF 파일에 숨겨진 텍스트 추가 및 검색
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에서 숨겨진 텍스트를 추가하고 검색하는 방법을 알아보세요. 코드 예제가 포함된 단계별 가이드.
type: docs
weight: 20
url: /ko/net/programming-with-text/add-and-search-hidden-text/
---
## 소개

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 숨겨진 텍스트를 추가하고 검색하는 방법에 대한 단계별 가이드를 안내합니다. 숙련된 개발자이든 프로그래밍 기술을 향상시키고자 하는 초보자이든 이 문서는 숨겨진 텍스트 기능을 애플리케이션에 통합하는 데 필요한 통찰력을 제공합니다.

## 필수 조건

코딩 부분에 들어가기 전에 꼭 염두에 두어야 할 몇 가지 전제 조건이 있습니다.

### 요구사항 체크리스트
- Visual Studio: Visual Studio가 설치되어 있는지 확인하세요. 이 튜토리얼에서는 .NET Framework를 사용한다고 가정합니다.
-  .NET용 Aspose.PDF: .NET용 Aspose.PDF 라이브러리가 필요합니다. 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
- C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 코드 조각을 더 잘 이해하는 데 도움이 됩니다.

## 패키지 가져오기

코드를 시작하기 전에 필요한 Aspose.PDF 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

### 프로젝트 설정
1. Visual Studio를 열고 새 C# 프로젝트를 만들거나 기존 프로젝트를 사용합니다.
2.  NuGet 패키지를 추가하여 Aspose.PDF를 설치합니다. NuGet 패키지 관리자로 이동하여 다음을 검색하여 이를 수행할 수 있습니다.`Aspose.PDF`. 
3.  또는 라이브러리를 다음에서 직접 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/) 프로젝트에 참조로 추가하세요.

### 필요한 네임스페이스 가져오기
C# 파일의 맨 위에 다음 네임스페이스를 가져옵니다.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이 단계는 이러한 네임스페이스에 PDF 문서를 조작하는 데 필요한 클래스와 메서드가 포함되어 있으므로 매우 중요합니다.

## 숨겨진 텍스트가 있는 PDF 문서 만들기

이제 설정이 끝났으니, 보이는 텍스트와 보이지 않는 텍스트가 모두 포함된 PDF 문서를 만드는 단계를 살펴보겠습니다.

### 1단계: 문서 디렉토리 정의
먼저 PDF가 저장될 경로를 설정해야 합니다. 여기서 마법이 시작됩니다!

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // 이것을 귀하의 디렉토리로 변경하세요
```

 이 줄은 생성된 PDF가 저장될 위치를 정의합니다. 다음을 바꾸는 것을 잊지 마세요.`YOUR DOCUMENT DIRECTORY` 실제 경로와 일치합니다.

### 2단계: PDF 문서 만들기
다음으로, 새 PDF 문서를 만들고 페이지를 추가해 보겠습니다.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
```

여기서는 새 문서를 초기화하고 텍스트 조각을 넣을 페이지를 추가합니다.

### 3단계: 표시 및 숨겨진 텍스트 추가
이제 PDF에 보이는 텍스트와 보이지 않는 텍스트를 모두 추가해 보겠습니다.

```csharp
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
```

 이 스니펫에서는`frag1` 보일 것입니다, 반면에`frag2` 다음에는 보이지 않게 설정됩니다.

### 4단계: 텍스트를 보이지 않게 설정
 텍스트를 만들려면`frag2` 보이지 않는 것, 간단히 수정하면 됩니다.`TextState`.

```csharp
frag2.TextState.Invisible = true;
```

 이 속성을 설정하면 연관된 모든 텍스트가`frag2` PDF를 볼 때 렌더링되지 않습니다.

### 5단계: 페이지에 텍스트 조각 추가
마지막으로, 이러한 텍스트 조각을 페이지에 추가하고 PDF를 저장합니다.

```csharp
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

이 코드의 이 부분은 페이지에 텍스트 조각을 추가합니다. 그 후, 문서를 적절히 저장하고 폐기합니다.

## PDF에서 숨겨진 텍스트 검색

이제 보이는 텍스트와 숨겨진 텍스트가 모두 있는 PDF를 만들었으니, 어떻게 숨겨진 텍스트를 검색할까요? 분석해 보겠습니다.

### 1단계: PDF 문서 로드
PDF 내에서 텍스트를 검색하려면 먼저 방금 만든 문서를 로드해야 합니다.

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
```

### 2단계: 텍스트 조각 흡수기 만들기
 우리는 사용할 것이다`TextFragmentAbsorber` PDF의 모든 텍스트 조각을 캡처합니다.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
```

여기서는 첫 번째 페이지의 모든 텍스트 조각을 흡수하도록 지정합니다.

### 3단계: 조각을 반복합니다.
이제 수집된 텍스트 조각을 반복해서 살펴보아 어떤 텍스트 조각이 보이고 어떤 텍스트 조각이 숨겨져 있는지 알아낼 수 있습니다.

```csharp
foreach (TextFragment fragment in absorber.TextFragments)
{
    Console.WriteLine("Text '{0}' on pos {1} invisibility: {2}",
        fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
```

 이 루프는 각 텍스트 조각을 확인하고 위치와 가시성 상태와 함께 내용을 인쇄합니다.`fragment.TextState.Invisible` true로 설정하면 텍스트가 숨겨집니다!

### 4단계: 문서 폐기
마지막으로 작업이 끝나면 문서를 다시 폐기하는 것을 잊지 마세요.

```csharp
doc.Dispose();
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 숨겨진 텍스트를 추가하고 검색하는 흥미로운 과정을 살펴보았습니다. 보이는 텍스트와 숨겨진 텍스트가 모두 있는 PDF 문서를 만드는 방법과 숨겨진 텍스트를 프로그래밍 방식으로 검색하는 방법을 배웠습니다. 이 기능은 기밀 정보를 저장하거나 문서 내에서 고유한 사용자 경험을 제공해야 하는지 여부에 관계없이 다양한 애플리케이션에서 매우 유용할 수 있습니다.

ASPose.PDF에 익숙해질수록 가능성은 무한해집니다. 계속 실험하고 PDF 문서로 달성할 수 있는 것의 경계를 넓혀보세요!

## 자주 묻는 질문

### Aspose.PDF는 암호화된 PDF 파일을 처리할 수 있나요?  
네, Aspose.PDF는 PDF 문서의 암호화 및 복호화를 지원합니다. 암호로 PDF를 쉽게 보호할 수 있습니다.

### Aspose.PDF의 평가판이 있나요?  
 물론입니다! 무료 체험판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Aspose.PDF는 어떤 프로그래밍 언어를 지원하나요?  
Aspose.PDF는 C#, Java, Python을 포함한 여러 언어를 지원합니다.

### Aspose.PDF에 대한 문서는 어디에서 찾을 수 있나요?  
 문서에 접근할 수 있습니다[여기](https://reference.aspose.com/pdf/net/).

### 문제가 발생하면 어떻게 지원을 받을 수 있나요?  
 지원이 필요하면 Aspose 포럼을 방문하세요.[여기](https://forum.aspose.com/c/pdf/10).