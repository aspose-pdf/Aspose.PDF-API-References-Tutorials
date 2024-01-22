---
title: PDF 파일에서 콜아웃 속성 설정
linktitle: PDF 파일에서 콜아웃 속성 설정
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 콜아웃 속성을 설정하는 방법을 알아보세요. 설명선, 텍스트 색상, 끝 스타일로 주석을 맞춤설정하세요.
type: docs
weight: 130
url: /ko/net/annotations/setcalloutproperty/
---
 .NET용 Aspose.PDF는 C#에서 PDF 문서를 생성, 조작 및 변환하기 위한 강력한 라이브러리입니다. 이 라이브러리에서 제공하는 기능 중 하나는 PDF 문서의 자유 텍스트 주석에 대한 설명선 속성을 설정하는 기능입니다. 이 작업은 다음을 사용하여 수행할 수 있습니다.`FreeTextAnnotation` 설명선이 포함된 주석을 만들 수 있는 클래스입니다.

이 튜토리얼에서는 C#에서 .NET용 Aspose.PDF를 사용하여 자유 텍스트 주석에 대한 설명선 속성을 설정하는 과정을 안내합니다. 시작하려면 아래 단계를 따르세요.

## .NET용 Aspose.PDF 설치

 아직 수행하지 않은 경우 다음을 수행해야 합니다.[다운로드](https://releases.aspose.com/pdf/net/) Aspose 릴리스 또는 NuGet 패키지 관리자를 통해 .NET용 Aspose.PDF를 설치합니다.

## 1단계: 새 PDF 문서 만들기

 다음을 사용하여 새 PDF 문서를 만듭니다.`Document`.NET용 Aspose.PDF에서 제공하는 클래스입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 2단계: 문서에 새 페이지 추가

 다음을 사용하여 문서에 새 페이지를 추가합니다.`Pages` 의 컬렉션`Document` 수업.

```csharp
Page page = doc.Pages.Add();
```

## 3단계: 기본 모양 설정

 새 주석을 생성하여 자유 텍스트 주석의 기본 모양을 설정합니다.`DefaultAppearance` 객체를 생성하고 다음과 같은 속성을 설정합니다.`TextColor` 그리고`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## 4단계: 설명선이 포함된 자유 텍스트 주석 생성

 다음을 사용하여 콜아웃이 포함된 새로운 자유 텍스트 주석을 생성합니다.`FreeTextAnnotation` 수업. 설정`Intent` 재산`FreeTextIntent.FreeTextCallout` 콜아웃 주석임을 지정합니다. 설정`EndingStyle` 재산`LineEnding.OpenArrow` 콜아웃 끝에 있는 화살표의 스타일을 지정합니다. 설정`Callout` 속성을 배열로`Point` 설명선을 그려야 하는 페이지의 지점을 나타내는 개체입니다.

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## 5단계: 페이지에 자유 텍스트 주석 추가

 다음을 사용하여 페이지에 자유 텍스트 주석을 추가합니다.`Annotations` 의 컬렉션`Page` 수업.

```csharp
page.Annotations.Add(fta);
```

## 6단계: 주석에 텍스트 추가

 다음을 설정하여 주석에 텍스트를 추가합니다.`RichText`속성을 형식화된 XML 문자열로 변환합니다. 이 튜토리얼에서는 텍스트 색상을 빨간색으로 설정하고 글꼴 크기를 9로 설정합니다.

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" 스타일=\"색상:#FF
```

## 7단계: 문서 저장

이제 다음 코드를 사용하여 문서를 저장합니다.

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### .NET용 Aspose.PDF를 사용하여 콜아웃 속성 설정에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">샘플입니다</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 자유 텍스트 주석에 대한 콜아웃 속성을 설정하는 방법을 살펴보았습니다. 설명선 주석은 문서의 특정 영역과 관련된 추가 정보나 설명을 제공하는 데 유용합니다. .NET용 Aspose.PDF는 콜아웃과 같은 주석 생성 및 사용자 정의를 포함하여 PDF 파일 작업을 위한 광범위한 기능을 제공합니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용함으로써 개발자는 PDF 문서에 설명선 주석을 쉽게 구현하여 문서의 유용성과 명확성을 향상시킬 수 있습니다. Aspose.PDF for .NET은 .NET 애플리케이션의 PDF 작업을 위한 다재다능하고 안정적인 라이브러리로, 다양한 PDF 관련 작업을 효율적으로 처리할 수 있는 강력한 도구를 제공합니다.

### PDF 파일의 콜아웃 속성 설정에 대한 FAQ

#### Q: PDF 문서의 설명선 주석이란 무엇입니까?

A: PDF 문서의 설명선 주석은 문서의 특정 영역을 가리키는 지시선이 있는 텍스트 상자를 만들 수 있는 주석 유형입니다. 일반적으로 문서의 특정 섹션이나 요소와 관련된 추가 정보나 설명을 제공하는 데 사용됩니다.

#### Q: .NET용 Aspose.PDF를 사용하여 콜아웃 주석의 모양을 사용자 정의할 수 있습니까?

A: 예, 색상, 글꼴 크기, 텍스트 정렬, 선 스타일, 화살표 스타일 등과 같은 설명선 주석의 다양한 속성을 사용자 정의할 수 있습니다.

#### Q: 콜아웃 주석에 텍스트를 어떻게 추가합니까?

 A: 콜아웃 주석에 텍스트를 추가하려면`RichText` 의 재산`FreeTextAnnotation` 물체. 그만큼`RichText` 속성은 콜아웃 주석에 표시될 텍스트를 나타내는 형식화된 XML 문자열을 사용합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에 여러 설명선 주석을 추가할 수 있습니까?

 A: 예, 여러 인스턴스를 생성하여 PDF 문서에 여러 설명선 주석을 생성할 수 있습니다.`FreeTextAnnotation`개체를 문서의 다른 페이지나 위치에 추가합니다.