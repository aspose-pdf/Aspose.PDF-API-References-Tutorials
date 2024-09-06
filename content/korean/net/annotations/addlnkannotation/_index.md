---
title: lnk 주석 추가
linktitle: lnk 주석 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 흥미로운 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 PDF 파일에 잉크 주석을 추가하는 방법을 알아보세요.
type: docs
weight: 20
url: /ko/net/annotations/addlnkannotation/
---
## 소개

Aspose.PDF for .NET으로 PDF 조작의 세계에 오신 것을 환영합니다! 전문적인 용도, 개인 프로젝트 또는 그 사이의 무엇이든 PDF 문서를 향상시키고자 한다면, 당신은 올바른 곳에 있습니다. 오늘은 Aspose.PDF의 구체적이면서도 실용적인 기능인 PDF 파일에 잉크 주석을 추가하는 것에 대해 알아보겠습니다. 이 기능은 문서에 손으로 쓴 것과 같은 메모나 서명을 추가하여 더욱 상호 작용적이고 매력적으로 만들고 싶을 때 매우 유용할 수 있습니다.

## 필수 조건

코딩 마법에 들어가기 전에 시작하는 데 필요한 모든 것이 있는지 확인해 보겠습니다.

1. .NET Framework: 컴퓨터에 .NET이 설치되어 있는지 확인하세요. 이 라이브러리는 .NET Core를 포함한 다양한 버전의 .NET과 원활하게 작동합니다.
2.  Aspose.PDF 라이브러리: .NET용 Aspose.PDF 라이브러리를 다운로드하여 프로젝트에서 참조해야 합니다. 아직 이 작업을 수행하지 않았다면 다음에서 최신 버전을 가져올 수 있습니다.[다운로드 링크](https://releases.aspose.com/pdf/net/).
3. 코드 편집기: 원하는 코드 편집기를 사용할 수 있지만 .NET 애플리케이션에서 사용하기 편리하므로 Visual Studio를 사용하는 것이 좋습니다.
4. C#에 대한 기본적인 이해: C#에 대한 실무 지식이 있으면 코딩 예제를 원활하게 탐색하는 데 도움이 됩니다.
5. 개발 환경 설정: IDE가 .NET 프로젝트를 처리하도록 설정되어 있는지 확인하고 프로젝트에서 Aspose.PDF 라이브러리를 올바르게 참조했는지 확인하세요. 

이러한 전제 조건을 충족하면 이제 PDF에 잉크 주석을 추가할 준비가 되었습니다!

## 패키지 가져오기

코딩에 들어가기 전에 필요한 패키지를 임포트해 보겠습니다. C# 파일의 맨 위에 다음 using 문을 추가합니다.

```csharp
using System.IO;
using Aspose.Pdf.Annotations;
using Aspose.Pdf;
using System;
using System.Collections;
using System.Collections.Generic;
```

이렇게 하면 PDF 주석 작업에 필요한 모든 클래스와 메서드에 액세스할 수 있습니다.

이제 무대를 마련했으니, 소매를 걷어붙이고 핵심을 파헤쳐야 할 때입니다! 각 단계를 자세히 설명하여 PDF 문서에 잉크 주석을 만들고 추가하는 방법을 정확히 이해하도록 하겠습니다.

## 1단계: 문서 및 디렉토리 설정

가장 먼저 해야 할 일은 문서와 출력 파일을 저장할 경로를 설정하는 것입니다. 

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
```
 우리는 변수를 정의합니다`dataDir` , 결과 PDF가 저장될 디렉토리를 가리킵니다.`Document` 그런 다음 객체가 인스턴스화되어 편집할 수 있는 새 PDF 문서가 생성됩니다.

## 2단계: 문서에 페이지 추가

다음으로, 새로 만든 문서에 페이지를 추가하고 싶을 겁니다.

```csharp
Page pdfPage = doc.Pages.Add();
```
여기서 우리는 문서에 새 페이지를 추가합니다. 모든 PDF에는 최소한 한 페이지가 필요하므로 이 단계는 필수적입니다.

## 3단계: 도면 사각형 정의

그림을 그리기 전에 먼저 페이지의 어느 부분에 잉크 주석을 넣을지 정의해야 합니다.

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
```
 여기서 우리는 다음을 생성합니다.`Rectangle` 페이지에 잉크 주석을 추가할 영역을 지정하는 객체입니다. 전체 페이지에 맞게 크기를 설정합니다(0,0).

## 4단계: 잉크 포인트 준비

이제 재밌는 부분, 잉크 주석을 구성하는 포인트를 정의하는 단계입니다. 

```csharp
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
```
이 코드 블록은 Point 배열 목록을 생성하는데, 각 배열은 잉크 스트로크에 대한 점 집합을 나타냅니다. 여기서는 삼각형을 형성하는 세 점을 정의합니다. 디자인에 맞게 좌표를 조정할 수 있습니다.

## 5단계: 잉크 주석 만들기

포인트를 정의했으면 이제 실제 잉크 주석을 만들 차례입니다.

```csharp
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList)
{
    Title = "XXX",
    Color = Aspose.Pdf.Color.LightBlue,
    CapStyle = CapStyle.Rounded
};
```
 우리는 인스턴스화합니다`InkAnnotation`객체, 페이지, 사각형 및 잉크 포인트를 전달합니다. 또한 다음과 같은 일부 속성을 설정합니다.`Title`, `Color` , 그리고`CapStyle`. 귀하의 필요에 맞게 사용자 정의하세요!

## 6단계: 테두리 및 불투명도 설정

주석을 돋보이게 하고 싶으신가요? 스타일을 더해 봅시다.

```csharp
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
```
여기서는 주석에 특정 너비의 테두리를 추가하고 불투명도를 설정하여 반투명하게 만듭니다.

## 7단계: 페이지에 주석 추가

이제 주석이 준비되었으니, PDF 페이지에 추가할 차례입니다.

```csharp
pdfPage.Annotations.Add(ia);
```
이 줄은 앞서 만든 잉크 주석을 페이지의 주석 컬렉션에 추가합니다. 

## 8단계: 문서 저장

마지막으로 수정된 문서를 저장해 보겠습니다.

```csharp
dataDir = dataDir + "AddInkAnnotation_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nInk annotation added successfully.\nFile saved at " + dataDir);
```
 우리는 우리의 수정`dataDir` 출력 파일 이름을 포함하고 문서를 저장합니다. 모든 것이 순조롭게 진행되었음을 알려주는 확인 메시지가 콘솔에 인쇄됩니다.

## 결론

이제 다 되었습니다! Aspose.PDF for .NET을 사용하여 PDF 문서에 잉크 주석을 성공적으로 추가했습니다. 이 간단하면서도 효과적인 기능은 문서를 향상시키고 대화형으로 만들 수 있습니다. 서명, 메모 또는 낙서를 추가하든 잉크 주석은 콘텐츠를 풍부하게 하는 고유한 방법을 제공합니다.

## 자주 묻는 질문

### Aspose.PDF란 무엇인가요?
Aspose.PDF는 .NET 애플리케이션에서 PDF 문서를 만들고, 조작하고, 변환하기 위한 라이브러리입니다.

### Aspose.PDF를 무료로 사용할 수 있나요?
 네! Aspose는 자사 제품을 평가하기 위한 무료 체험판을 제공합니다. 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### 여러 개의 잉크 주석을 추가할 수 있나요?
 물론입니다! 여러 개를 만들 수 있습니다.`InkAnnotation` 개체를 선택하여 문서 페이지에 추가합니다.

### 더 많은 예를 어디서 볼 수 있나요?
 당신은 확인할 수 있습니다[선적 서류 비치](https://reference.aspose.com/pdf/net/) 자세한 튜토리얼과 샘플을 확인하세요.

### 지원이 필요하면 어떻게 해야 하나요?
 문제가 발생하면 다음에서 도움을 요청할 수 있습니다.[지원 포럼](https://forum.aspose.com/c/pdf/10).