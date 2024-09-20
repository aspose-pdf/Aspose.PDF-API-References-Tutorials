---
title: PDF 파일에 음영 색상이 있는 텍스트 추가
linktitle: PDF 파일에 음영 색상이 있는 텍스트 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 튜토리얼을 통해 Aspose.PDF for .NET을 사용하여 PDF 파일에 텍스트 음영을 추가하는 방법을 알아보세요. 컬러 그라데이션으로 문서를 사용자 지정하세요.
type: docs
weight: 80
url: /ko/net/programming-with-text/add-text-with-shading-colors/
---
## 소개

PDF 문서에 약간의 색상을 더해 시각적으로 돋보이게 만들어야 할 때가 있었나요? PDF로 작업하면서 "눈에 띄려면 뭔가 특별한 게 필요해."라고 생각했을 수도 있습니다. 더 이상 찾지 마세요! Aspose.PDF for .NET을 사용하면 PDF 파일에 음영 색상이 있는 텍스트를 쉽게 추가할 수 있습니다. 프레젠테이션을 위해 문서를 준비하든 단순히 텍스트의 일부를 빛나게 하든, 텍스트에 음영을 입히면 문서의 디자인을 실제로 격상시킬 수 있습니다.

## 필수 조건

코드에 뛰어들기 전에 이 튜토리얼을 따르기 위해 설정해야 할 몇 가지 사항이 있습니다. 필요한 것은 다음과 같습니다.

1.  .NET용 Aspose.PDF: 최신 버전의 Aspose.PDF를 다운로드하여 설치했는지 확인하세요.[여기서 다운로드하세요](https://releases.aspose.com/pdf/net/).
2. IDE(통합 개발 환경): .NET과 호환되는 모든 IDE를 사용할 수 있지만 Visual Studio를 적극 권장합니다.
3. C#에 대한 기본 지식: C# 구문과 .NET 환경에 익숙해야 합니다.
4. 샘플 PDF 파일: 작업할 샘플 PDF 파일이 필요합니다. 파일이 없으면 간단한 텍스트 PDF를 만들거나 데모에 기존 파일을 사용할 수 있습니다.
5.  Aspose.PDF 라이센스: Aspose.PDF를 다음과 함께 사용할 수 있습니다.[임시 면허](https://purchase.aspose.com/temporary-license/)무료 체험판을 통해 기능을 탐색해 볼 수도 있습니다.

## 패키지 가져오기

코드로 넘어가기 전에 필요한 네임스페이스를 가져와야 합니다. 이를 통해 Aspose.PDF 객체로 작업하고 PDF 문서에서 텍스트와 색상 설정을 조작할 수 있습니다.

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Aspose.PDF for .NET을 사용하여 PDF 파일의 텍스트에 음영을 추가하는 과정을 관리 가능한 단계로 나누어 보겠습니다. 걱정하지 마세요. 생각보다 간단합니다!

## 1단계: 문서 디렉토리 설정

가장 먼저 해야 할 일은 문서의 위치를 정의하는 것입니다. 모든 PDF 파일이 저장되고 새로 편집한 파일을 저장할 폴더라고 생각하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 파일에 대한 실제 경로와 함께. 이렇게 하면 코드가 어디를 보고 편집된 문서를 어디에 저장할지 알 수 있습니다.

## 2단계: 기존 PDF 문서 로드

문서 디렉토리를 설정했으면 이제 편집하려는 PDF 파일을 로드할 차례입니다. 이 예에서는 다음 이름의 파일을 사용합니다.`"text_sample4.pdf"`.

```csharp
using (Document pdfDocument = new Document(dataDir + "text_sample4.pdf"))
{
    // 다음 단계로 넘어가세요.
}
```

 그만큼`Document` Aspose.PDF의 객체를 사용하면 PDF를 열고 작업할 수 있습니다.

## 3단계: TextFragmentAbsorber를 사용하여 특정 텍스트 검색

텍스트의 특정 부분에 음영을 적용하려면 PDF에서 해당 텍스트를 찾아야 합니다. 여기서 TextFragmentAbsorber가 등장합니다. 수정하려는 텍스트를 흡수하는 스캐너와 같습니다.

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Lorem ipsum");
pdfDocument.Pages.Accept(absorber);
```

 이 예에서 우리는 PDF에서 "Lorem ipsum"이라는 문구를 찾고 있습니다.`Accept` 이 방법은 페이지를 처리하고 흡수체가 텍스트 조각을 식별할 수 있도록 합니다.

## 4단계: 수정하려는 텍스트 조각에 액세스

이제 텍스트가 흡수되었으므로 특정 TextFragment에 액세스할 수 있습니다. 우리는 "Lorem ipsum"이라는 텍스트의 첫 번째 발생을 수정하고자 한다고 가정합니다.

```csharp
TextFragment textFragment = absorber.TextFragments[1];
```

이 줄은 TextFragments 컬렉션에서 문구 "Lorem ipsum"의 첫 번째 인스턴스를 검색합니다. 다른 인스턴스를 수정하려면 인덱스를 변경할 수 있습니다.

## 5단계: 텍스트에 음영 적용

이제 재밌는 부분이 왔습니다! 텍스트에 음영 색상을 추가해 보겠습니다. GradientAxialShading을 사용하여 그라데이션 효과가 있는 새 색상을 만들 수 있습니다. 이 예에서는 Red에서 Blue로 전환되는 음영을 적용합니다.

```csharp
textFragment.TextState.ForegroundColor = new Aspose.Pdf.Color()
{
    PatternColorSpace = new Aspose.Pdf.Drawing.GradientAxialShading(Color.Red, Color.Blue)
};
```

 이렇게 하면 선택한 텍스트에서 빨간색에서 파란색으로 부드러운 그라데이션이 생성됩니다.`PatternColorSpace` 이 특별한 색상 효과를 정의하는 데 사용됩니다.

## 6단계: 텍스트에 밑줄 긋기(선택 사항)

 추가 강조를 위해 텍스트에 밑줄을 추가하려면 다음을 설정하세요.`Underline` 재산에`true`.

```csharp
textFragment.TextState.Underline = true;
```

밑줄을 추가하면 음영이 있는 텍스트가 더욱 눈에 띄게 됩니다.

## 7단계: 업데이트된 PDF 문서 저장

마지막으로 음영 처리와 다른 원하는 수정 사항을 적용한 후 PDF를 디렉토리에 저장합니다.

```csharp
pdfDocument.Save(dataDir + "text_out.pdf");
```

 수정된 PDF는 다음 이름으로 저장됩니다.`"text_out.pdf"`이전에 지정한 디렉토리에 있습니다. 이제 파일을 열고 아름답게 음영 처리된 텍스트를 볼 수 있습니다!

## 결론

이제 다 됐습니다! 몇 가지 간단한 단계만 거치면 Aspose.PDF for .NET을 사용하여 PDF의 텍스트에 음영을 성공적으로 적용할 수 있습니다. 이 기능은 특정 텍스트를 강조하는 데 도움이 될 뿐만 아니라 문서에 세련되고 전문적인 터치를 더해줍니다. 시각적으로 매력적인 보고서를 만들든 단순히 텍스트의 특정 부분을 돋보이게 해야 하든 이 기술은 게임 체인저입니다.


## 자주 묻는 질문

### 한 번에 여러 텍스트 조각에 음영을 적용할 수 있나요?
네! TextFragments 컬렉션을 반복하면서 각 조각에 개별적으로 음영을 적용할 수 있습니다.

### 그라데이션 색상을 사용자 정의할 수 있나요?
물론입니다! GradientAxialShading을 사용하여 그래디언트에 원하는 색상을 정의할 수 있습니다.

### 이 기능을 사용하려면 유료 라이선스가 필요합니까?
 이 기능을 사용하여 시도할 수 있습니다[무료 체험](https://releases.aspose.com/) 또는[임시 면허](https://purchase.aspose.com/temporary-license/)하지만 모든 기능을 사용하려면 유료 라이선스를 구입하는 것이 좋습니다.

### 텍스트의 글꼴 스타일을 어떻게 변경할 수 있나요?
 TextState 객체를 통해 글꼴 크기, 스타일, 두께와 같은 속성을 설정할 수 있습니다.`FontSize` 그리고`FontStyle`.

### 새로 추가한 텍스트에 음영을 추가할 수 있나요?
네, 이 가이드에서 다룬 것과 동일한 방법을 사용하여 PDF에 새 텍스트를 추가하고 음영을 적용할 수 있습니다.