---
title: PDF 파일에서 콜아웃 속성 설정
linktitle: PDF 파일에서 콜아웃 속성 설정
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 자세하고 단계별 튜토리얼을 통해 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 콜아웃 속성을 설정하는 방법을 알아보세요.
type: docs
weight: 130
url: /ko/net/annotations/setcalloutproperty/
---
## 소개

전문적이고 시각적으로 매력적인 PDF 문서를 만들려면 종종 특정 콘텐츠에 주의를 끌기 위한 주석을 추가해야 합니다. 그러한 주석 중 하나는 콜아웃으로, 만화에서 볼 수 있는 말풍선과 같습니다. 콜아웃은 PDF 내의 텍스트를 명확히 하거나 강조하는 데 도움이 됩니다. Aspose.PDF for .NET을 사용하면 문서에 이러한 주석을 매우 쉽게 추가할 수 있으며, 이 튜토리얼에서는 이 강력한 라이브러리를 사용하여 PDF 파일에서 콜아웃 속성을 설정하는 방법을 살펴보겠습니다. 노련한 개발자이든 방금 시작한 개발자이든 이 가이드를 마치면 PDF 파일에서 콜아웃을 사용하는 방법을 명확하게 이해하게 될 것입니다.

## 필수 조건

코드를 살펴보기 전에, 시작하는 데 필요한 필수 사항을 살펴보겠습니다.

1.  .NET용 Aspose.PDF: .NET용 Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요. 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/net/).
2. IDE: Visual Studio와 같은 개발 환경.
3. .NET Framework: 컴퓨터에 .NET이 설치되어 있는지 확인하세요.
4. 임시 라이센스: 제한 없이 Aspose.PDF의 모든 기능을 사용해보고 싶다면[임시 면허](https://purchase.aspose.com/temporary-license/).

## 패키지 가져오기

코드 작성을 시작하기 전에 PDF 파일과 주석을 다루는 데 필요한 패키지를 가져와야 합니다.

```csharp
using Aspose.Pdf.Annotations;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

이러한 가져오기는 PDF 문서를 조작하고 콜아웃과 같은 주석을 만드는 데 필요한 모든 클래스와 메서드를 제공합니다.

## 1단계: PDF 문서 초기화

여정의 첫 번째 단계는 콜아웃 주석을 추가할 새 PDF 문서를 초기화하는 것입니다. 요소를 추가할 수 있는 빈 캔버스를 설정하는 것으로 생각하세요.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 새 PDF 문서 초기화
Document doc = new Document();
```
 여기서 우리는 새로운 것을 만들고 있습니다`Document` PDF 파일로 사용될 객체입니다.`dataDir` 변수는 작업이 끝난 후 PDF 파일을 저장할 디렉토리로 설정됩니다.

## 2단계: 문서에 새 페이지 추가

PDF 문서는 여러 페이지를 가질 수 있으며, 이 단계에서는 문서에 새 페이지를 추가합니다. 이 페이지는 콜아웃 주석이 배치될 곳입니다.

```csharp
//문서에 새 페이지 추가
Page page = doc.Pages.Add();
```
 그만큼`Pages.Add()`이 방법은 새 페이지를 추가하는 데 사용됩니다.`doc` 객체. 새 페이지는 다음 위치에 저장됩니다.`page` 변수는 나중에 주석을 추가할 때 사용할 것입니다.

## 3단계: 기본 모양 정의

주석은 콜아웃과 마찬가지로 사용자 정의할 수 있는 시각적 모양이 있습니다. 이 단계에서는 콜아웃 내의 텍스트가 어떻게 보여야 하는지 정의합니다.

```csharp
// 주석의 기본 모양을 정의합니다.
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```
 우리는 만듭니다`DefaultAppearance` 텍스트 색상과 글꼴 크기를 정의하는 객체입니다. 여기서 텍스트는 빨간색이고 글꼴 크기는 10으로 설정됩니다. 이 모양은 콜아웃 주석에 적용됩니다.

## 4단계: 자유 텍스트 주석 만들기

이제 실제 주석을 만들 시간입니다. 자유 텍스트 주석은 특정 텍스트와 스타일로 콜아웃을 추가할 수 있게 해줍니다.

```csharp
// 콜아웃이 있는 FreeTextAnnotation 만들기
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
```
 우리는 만듭니다`FreeTextAnnotation` 특정 좌표를 가진 객체로 페이지에서 위치를 정의합니다.`Intent` 로 설정되었습니다`FreeTextCallout` , 이것이 콜아웃 주석임을 나타냅니다.`EndingStyle` 로 설정되었습니다`OpenArrow`즉, 설명선은 열린 화살표로 끝납니다.

## 5단계: 콜아웃 라인 포인트 정의

콜아웃 주석에는 관심 영역을 가리키는 선이 있습니다. 여기서는 이 선을 구성하는 점을 정의합니다.

```csharp
// 콜아웃 라인에 대한 포인트를 정의합니다
fta.Callout = new Point[]
{
    new Point(428.25, 651.75), 
    new Point(462.75, 681.375), 
    new Point(474, 681.375)
};
```
 그만큼`Callout` 속성은 배열입니다`Point` 객체, 각각 페이지의 좌표를 나타냅니다. 이러한 점은 콜아웃 라인의 경로를 정의하여 고전적인 말풍선 모양을 제공합니다.

## 6단계: 페이지에 주석 추가

주석을 만들고 구성한 후 다음 단계는 이를 페이지에 추가하는 것입니다.

```csharp
// 페이지에 주석을 추가하세요
page.Annotations.Add(fta);
```
 그만큼`Annotations.Add()` 방법은 우리가 이전에 만든 페이지에 주석을 배치하는 데 사용됩니다. 이 단계는 PDF 페이지에 콜아웃을 효과적으로 "그립니다".

## 7단계: 서식 있는 텍스트 콘텐츠 설정

콜아웃 주석에는 서식 있는 텍스트를 포함할 수 있으므로 버블 내에 서식 있는 콘텐츠를 허용합니다. 샘플 텍스트를 추가해 보겠습니다.

```csharp
// 주석에 대한 서식 있는 텍스트를 설정합니다.
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"><span style=\"font-size:9.0pt;font-family:Helvetica\">이것은 샘플입니다.</span></p></body>";
```
 그만큼`RichText` 속성은 HTML 콘텐츠로 설정됩니다. 이를 통해 글꼴 크기, 색상 및 스타일 지정과 같은 콜아웃 내에서 자세한 서식을 지정할 수 있습니다.

## 8단계: PDF 문서 저장

마지막으로 모든 것을 설정한 후에는 문서를 저장해야 합니다. 이 단계는 콜아웃 주석이 있는 PDF 생성을 마무리합니다.

```csharp
// 문서를 저장하세요
doc.Save(dataDir + "SetCalloutProperty.pdf");
```
 그만큼`Save()` 이 방법은 지정된 디렉토리에 "SetCalloutProperty.pdf"라는 파일 이름으로 문서를 저장합니다. 이 단계는 PDF 생성 프로세스를 마무리합니다.

## 결론

이제 다 되었습니다! Aspose.PDF for .NET을 사용하여 콜아웃 주석이 있는 PDF 문서를 만들었습니다. 이 주석은 문서의 특정 부분을 강조하거나 설명하는 데 매우 유용할 수 있습니다. Aspose.PDF는 PDF 조작을 간단하고 유연하게 만드는 강력한 API를 제공합니다. 주석을 추가하든, 문서를 변환하든, 복잡한 PDF 작업을 처리하든 Aspose.PDF가 해결해 드립니다.

## 자주 묻는 질문

### 콜아웃의 모양을 더욱 세부적으로 사용자 지정할 수 있나요?

물론입니다! 선 색상, 두께, 텍스트의 글꼴 패밀리 및 스타일과 같은 다양한 측면을 사용자 정의할 수 있습니다.

### 한 페이지에 여러 개의 콜아웃을 추가할 수 있나요?

네, 각 주석에 대해 단계를 반복하여 필요한 만큼 많은 콜아웃을 추가할 수 있습니다.

### 콜아웃의 위치를 어떻게 바꾸나요?

 좌표를 수정하기만 하면 됩니다.`Rectangle` 그리고`Callout` 주석의 위치를 변경하기 위한 속성입니다.

### Aspose.PDF를 사용하여 다른 유형의 주석을 추가할 수 있나요?

네, Aspose.PDF는 강조 표시, 스탬프, 파일 첨부 등 다양한 주석 유형을 지원합니다.

### 서식 있는 텍스트 콘텐츠는 HTML로 제한됩니까?

 그만큼`RichText` 이 속성은 HTML 하위 집합을 지원하므로 스타일이 지정된 텍스트와 기본 서식을 포함할 수 있습니다.