---
title: PDF 파일에서 텍스트 조각을 사용하여 텍스트 회전
linktitle: PDF 파일에서 텍스트 조각을 사용하여 텍스트 회전
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 텍스트를 회전하는 방법을 단계별 가이드와 함께 알아보세요. 위치 지정에서 회전까지 텍스트 조작 기술을 알아보세요.
type: docs
weight: 390
url: /ko/net/programming-with-text/rotate-text-using-text-fragment/
---
## 소개

PDF를 만드는 것은 한 가지 일이지만, 특정 요구 사항에 맞게 조작하는 것은? 그게 진짜 마법이 일어나는 곳입니다! PDF에서 텍스트를 회전하는 방법을 궁금해하신 적이 있나요? 보고서를 생성하든 사용자 지정 디자인으로 문서를 만들든, 텍스트 조각을 회전하면 PDF가 시각적으로 더 매력적으로 보일 수 있습니다. 이 튜토리얼에서는 PDF 문서를 원활하게 조작할 수 있는 강력한 라이브러리인 Aspose.PDF for .NET을 사용하여 텍스트를 회전하는 방법을 살펴보겠습니다.

## 필수 조건

코드로 넘어가기 전에 필요한 도구와 설정을 간단히 살펴보겠습니다. 쉽게 따라할 수 있도록 모든 것을 준비해야 합니다.

### .NET 라이브러리용 Aspose.PDF
우선, 프로젝트에 Aspose.PDF for .NET이 설치되어 있어야 합니다. 이 라이브러리에는 PDF 파일을 프로그래밍 방식으로 만들고, 수정하고, 관리하는 데 도움이 되는 기능이 가득 들어 있습니다. 아직 다운로드하지 않았다면 다음 위치에서 다운로드할 수 있습니다.
- [.NET용 Aspose.PDF 다운로드](https://releases.aspose.com/pdf/net/)

이 튜토리얼에서는 최신 버전의 라이브러리를 사용하고 있는지 확인하세요.

### 개발 환경
Visual Studio와 같은 .NET 개발 환경도 필요합니다. C# 개발을 위한 필수 IDE이며, 코딩 경험을 매끄럽고 효율적으로 만들어 줄 것입니다.

### 임시 또는 전체 라이센스
Aspose.PDF의 무료 평가판으로 시작할 수 있지만, 제한을 피하고 싶다면 임시 또는 전체 라이선스를 사용하는 것이 좋습니다. 다음은 라이선스를 얻는 방법입니다.
- [무료 체험](https://releases.aspose.com/)
- [임시 라이센스](https://purchase.aspose.com/temporary-license/)
- [전체 라이센스 구매](https://purchase.aspose.com/buy)

이러한 필수 사항을 모두 준비했다면 다음으로 넘어가볼까요!

## 패키지 가져오기

코딩을 시작하기 전에 Aspose.PDF와 함께 제공되는 필수 네임스페이스를 가져와야 합니다. 이는 문서, 페이지, 텍스트 조각 등을 다루는 데 필수적입니다. C# 파일의 시작 부분에 다음 코드를 추가합니다.

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.Facades;
```

이제 예제 코드를 단계별로 나누어서 전문가처럼 텍스트를 회전해 보세요!

## 1단계: 문서 개체 초기화

모든 PDF 조작은 PDF 문서를 만들거나 로드하는 것으로 시작합니다. 여기서는 Aspose.PDF를 사용하여 새 PDF 문서를 처음부터 초기화합니다.

 우리는 새로운 것을 만들고 있습니다`Document` PDF 파일을 나타내는 객체입니다. 처음에는 이 문서가 비어 있습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 객체 초기화
Document pdfDocument = new Document();
```

설명:  
- `dataDir`: 최종 PDF가 저장되는 디렉토리입니다.
- `Document pdfDocument = new Document();`: 새 빈 PDF 문서를 초기화합니다. 

## 2단계: 문서에 페이지 추가

다음으로, 문서에 페이지를 추가해야 합니다. PDF는 기본적으로 페이지 모음이며, 콘텐츠를 추가하려면 최소한 한 페이지가 필요합니다.

```csharp
// 특정 페이지 가져오기
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

페이지를 추가하지 않으면 그림을 그리거나 텍스트를 넣을 캔버스가 없습니다!

## 3단계: 첫 번째 텍스트 조각 만들기

이제 흥미로운 부분이 왔습니다! PDF에 텍스트 조각을 추가해 보겠습니다. 텍스트 조각은 글꼴, 크기, 위치와 같은 특정 속성을 가진 텍스트 조각입니다.

```csharp
// 텍스트 조각 만들기
TextFragment textFragment1 = new TextFragment("main text");
textFragment1.Position = new Position(100, 600);
textFragment1.TextState.FontSize = 12;
textFragment1.TextState.Font = FontRepository.FindFont("TimesNewRoman");
```

- TextFragment("main text"): 이것은 "main text"라는 내용으로 새로운 텍스트 조각을 생성합니다.
- Position(100, 600): 페이지에서 텍스트의 위치를 정의합니다. 첫 번째 숫자는 x 좌표이고 두 번째 숫자는 y 좌표입니다.
- TextState.FontSize: 텍스트의 글꼴 크기를 설정합니다.
- FontRepository.FindFont: 텍스트에 적용할 지정된 글꼴을 찾습니다.

## 4단계: 회전된 텍스트 조각 만들기

더 많은 텍스트 조각을 추가해 보죠. 이번에는 다른 각도로 회전해 볼까요!

### 텍스트 조각을 45도 회전

```csharp
// 회전된 텍스트 조각 만들기
TextFragment textFragment2 = new TextFragment("rotated text");
textFragment2.Position = new Position(200, 600);
textFragment2.TextState.FontSize = 12;
textFragment2.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment2.TextState.Rotation = 45;
```

여기서 주요 변화는 다음과 같습니다.
- TextState.Rotation: 이 속성은 텍스트 조각의 회전 각도를 설정하며, 이 경우 45도입니다.

### 텍스트 조각을 90도 회전

```csharp
// 회전된 텍스트 조각 만들기
TextFragment textFragment3 = new TextFragment("rotated text");
textFragment3.Position = new Position(300, 600);
textFragment3.TextState.FontSize = 12;
textFragment3.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment3.TextState.Rotation = 90;
```

이 경우 회전은 90도입니다.

## 5단계: PDF 페이지에 텍스트 조각 추가

이제 모든 텍스트 조각이 준비되었으므로 TextBuilder 클래스를 사용하여 PDF 페이지에 추가할 차례입니다.

```csharp
// TextBuilder 객체 생성
TextBuilder textBuilder = new TextBuilder(pdfPage);
// PDF 페이지에 텍스트 조각 추가
textBuilder.AppendText(textFragment1);
textBuilder.AppendText(textFragment2);
textBuilder.AppendText(textFragment3);
```

TextBuilder 클래스는 단일 페이지에 여러 텍스트 조각을 추가하는 데 도움이 되며, 이를 개별적으로 조작할 수 있는 유연성을 제공합니다.

## 6단계: PDF 문서 저장

마지막으로, 지정된 디렉토리에 문서를 저장합니다. 이 단계가 없다면, 당신의 모든 노고가 허공으로 사라질 것입니다!

```csharp
// 문서 저장
pdfDocument.Save(dataDir + "TextFragmentTests_Rotated1_out.pdf");
```

Aspose.PDF for .NET을 사용하여 PDF 파일의 텍스트를 성공적으로 회전했습니다. 이제 PDF를 열어 회전된 텍스트 조각을 볼 수 있습니다!

## 결론

PDF에서 텍스트를 회전하면 문서에 전문적인 터치를 더해 시각적으로 매력적이고 독특하게 만들 수 있습니다. Aspose.PDF for .NET을 사용하면 텍스트 조각을 조작하기가 매우 쉬워 콘텐츠가 표시되는 방식을 완벽하게 제어할 수 있습니다. 이제 텍스트를 회전하는 방법을 배웠으므로 프로젝트의 필요에 맞게 다양한 각도와 레이아웃을 실험해 볼 수 있습니다.

## 자주 묻는 질문

### 텍스트 조각을 어떤 각도로든 회전할 수 있나요?
 네! 설정할 수 있습니다.`TextState.Rotation` 텍스트를 필요에 따라 회전하려면 속성을 원하는 각도(음의 각도도 가능)로 변경하세요.

### 각 텍스트 조각에 다른 글꼴을 사용할 수 있나요?
 물론입니다. 각 텍스트 조각의 글꼴을 다음을 사용하여 사용자 정의할 수 있습니다.`FontRepository.FindFont` 적용하려는 글꼴을 전달하세요.

### Aspose.PDF는 여러 페이지로 된 PDF를 지원합니까?
네, PDF 문서에 여러 페이지를 추가하고 각 페이지를 개별적으로 조작할 수 있습니다.

### 추가할 수 있는 텍스트 조각의 수에 제한이 있나요?
아니요, 필요한 만큼 많은 텍스트 조각을 추가할 수 있습니다. 페이지에 제대로 배치되었는지 확인하기만 하면 됩니다.

### 텍스트 조각을 추가한 후에 수정할 수 있나요?
네, 텍스트 조각을 추가한 후에도 해당 속성을 업데이트하거나 페이지에서 제거할 수 있습니다.