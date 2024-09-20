---
title: PDF 파일에서 플로팅 박스 콘텐츠에 대한 텍스트 정렬
linktitle: PDF 파일에서 플로팅 박스 콘텐츠에 대한 텍스트 정렬
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 떠 있는 상자 내용을 정렬하는 방법을 알아보세요. 전문적인 레이아웃으로 멋진 문서를 만드세요.
type: docs
weight: 520
url: /ko/net/programming-with-text/text-alignment-for-floating-box-contents/
---
## 소개

시각적으로 매력적인 PDF를 만드는 것은 모든 사람이 주의를 끌기 위해 경쟁하는 오늘날의 디지털 세계에서 중요한 기술입니다. Aspose.PDF for .NET은 특히 문서 레이아웃을 사용자 정의할 때 이 작업을 매우 간단하고 유연하게 만듭니다. 이 튜토리얼에서는 PDF 파일 내에서 떠 있는 상자 내용을 정렬하는 방법을 살펴보겠습니다. 이 접근 방식은 문서에 군중 속에서 돋보이는 세련되고 전문적인 터치를 제공합니다.

## 필수 조건

튜토리얼을 시작하기 전에 꼭 알아두어야 할 몇 가지 필수 사항이 있습니다.

1. .NET Framework: 코드를 실행할 컴퓨터에 호환되는 .NET Framework가 설치되어 있는지 확인하세요.
2.  Aspose.PDF 라이브러리: Aspose.PDF 라이브러리가 필요합니다. 아직 다운로드하지 않았다면 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
3. IDE: Visual Studio와 같은 통합 개발 환경(IDE)은 코딩과 디버깅에 도움이 됩니다.
4. C#에 대한 기본 지식: C# 프로그래밍에 익숙하면 코드 조각을 따라가고 이해하는 것이 더 쉬워집니다.

## 패키지 가져오기

시작하려면 C# 프로젝트에서 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.

1. 프로젝트 열기: IDE를 실행하고, 떠 있는 상자 기능을 구현하려는 프로젝트를 엽니다.
2. .NET용 Aspose.PDF 설치: NuGet 패키지 관리자를 사용하여 Aspose.PDF 패키지를 설치합니다. 이렇게 하려면:
   - 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택합니다.
   - “Aspose.PDF”를 검색하고 “설치”를 클릭하세요.
   
```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

패키지를 설정한 후에는 PDF에서 떠 있는 상자를 만들고 정렬할 준비가 된 것입니다.

이제 PDF 문서에 떠 있는 상자를 추가하고 정렬하는 과정을 분석해 보겠습니다. 설명을 위해 여러 개의 떠 있는 상자를 만들고 그 내용을 다르게 정렬합니다.

## 1단계: 문서 설정

첫 번째 단계는 새 PDF 문서를 초기화하고 여기에 페이지를 추가하는 것입니다. 이것은 우리의 떠다니는 상자의 캔버스 역할을 합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document doc = new Document();
doc.Pages.Add();
```

 이 코드 조각에서 다음을 바꾸세요.`"YOUR DOCUMENT DIRECTORY"` PDF 파일을 저장하려는 실제 경로를 입력합니다.

## 2단계: 첫 번째 플로팅 박스 만들기

다음으로, 첫 번째 플로팅 박스를 만들고 정렬을 설정해 보겠습니다. 여기서 콘텐츠는 박스의 오른쪽 하단에 정렬됩니다.

```csharp
Aspose.Pdf.FloatingBox floatBox = new Aspose.Pdf.FloatingBox(100, 100);
floatBox.VerticalAlignment = VerticalAlignment.Bottom;
floatBox.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox.Paragraphs.Add(new TextFragment("FloatingBox_bottom"));
floatBox.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox);
```

- FloatingBox(100, 100): 이는 너비와 높이가 각각 100단위인 떠 있는 상자를 초기화합니다.
- 수직 및 수평 정렬: 텍스트가 아래쪽과 오른쪽에 정렬되도록 지정합니다.
- TextFragment: 이것은 떠 있는 상자 안에 표시하려는 텍스트를 나타냅니다.
- BorderInfo: 이 설정은 떠 있는 상자 주위에 테두리를 설정하여 시각적으로 구별되게 합니다.

## 3단계: 두 번째 플로팅 상자 추가

이제 콘텐츠를 중앙에 배치하는 두 번째 떠 있는 상자를 만들어 보겠습니다.

```csharp
Aspose.Pdf.FloatingBox floatBox1 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox1.VerticalAlignment = VerticalAlignment.Center;
floatBox1.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox1.Paragraphs.Add(new TextFragment("FloatingBox_center"));
floatBox1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox1);
```

첫 번째 상자와 마찬가지로 수직 정렬을 가운데로, 수평 정렬을 오른쪽으로 설정했습니다. 이 방법을 사용하면 동적 콘텐츠 조정과 더 나은 시각적 매력이 가능합니다.

## 4단계: 세 번째 플로팅 박스 만들기

이제 세 번째이자 마지막 플로팅 박스에서 콘텐츠를 오른쪽 상단에 정렬해 보겠습니다.

```csharp
Aspose.Pdf.FloatingBox floatBox2 = new Aspose.Pdf.FloatingBox(100, 100);
floatBox2.VerticalAlignment = VerticalAlignment.Top;
floatBox2.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Right;
floatBox2.Paragraphs.Add(new TextFragment("FloatingBox_top"));
floatBox2.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Blue);
doc.Pages[1].Paragraphs.Add(floatBox2);
```

이 상자는 오른쪽 상단의 콘텐츠를 정렬하여 Aspose.PDF 라이브러리를 사용하는 유연성을 보여줍니다. 각 떠다니는 상자는 시각적으로 정보를 전달하는 방법에 따라 고유한 목적을 제공할 수 있습니다.

## 5단계: 문서 저장

마지막으로 문서를 저장할 시간입니다. 이전에 지정한 위치에 저장합니다.

```csharp
doc.Save(dataDir + "FloatingBox_alignment_review_out.pdf");
```

 파일은 다음 이름으로 저장됩니다.`FloatingBox_alignment_review_out.pdf` 지정된 디렉토리에 있습니다. 생성된 PDF를 보려면 이 위치를 확인하세요.

## 결론

Aspose.PDF for .NET을 사용하여 PDF 레이아웃을 조작하면 전문적이고 시각적으로 매력적인 문서를 효율적으로 만들 수 있습니다. 떠 있는 상자 내용을 정렬하는 방법을 이해하면 PDF 파일의 사용자 경험을 크게 향상시킬 수 있습니다. 살펴본 것처럼 간단하지만 PDF를 돋보이게 할 만큼 강력합니다.

## 자주 묻는 질문

### Aspose.PDF의 플로팅 박스란 무엇인가요?  
떠 있는 상자를 사용하면 PDF 레이아웃 내에서 콘텐츠를 유연하게 배치할 수 있습니다.

### 떠 있는 상자 테두리의 색상을 변경할 수 있나요?  
네, 떠 있는 상자를 만들 때 테두리에 다른 색상을 지정할 수 있습니다.

### .NET용 Aspose.PDF는 무료로 사용할 수 있나요?  
Aspose.PDF는 무료 평가판을 제공하지만, 모든 기능을 사용하려면 유료 라이선스가 필요합니다.

### 떠 있는 상자에 이미지를 추가할 수 있나요?  
물론입니다! 이미지를 포함한 다양한 유형의 콘텐츠를 플로팅 박스에 추가할 수 있습니다.

### Aspose.PDF에 대한 자세한 정보는 어디에서 볼 수 있나요?  
 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/pdf/net/).