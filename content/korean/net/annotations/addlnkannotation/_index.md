---
title: LNK 주석 추가
linktitle: LNK 주석 추가
second_title: .NET API 참조용 Aspose.PDF
description: 단계별 가이드 및 전체 소스 코드와 함께 .NET용 Aspose.PDF를 사용하여 C#에서 PDF 문서에 잉크 주석 기능을 추가하는 방법을 알아보세요.
type: docs
weight: 20
url: /ko/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET은 개발자가 다양한 PDF 작업을 수행할 수 있는 강력한 라이브러리입니다. 그러한 작업 중 하나는 PDF 문서에 잉크 주석을 추가하는 것입니다. 이 기사에서는 .NET용 Aspose.PDF를 사용하여 잉크 주석을 추가하기 위한 C# 소스 코드를 설명하는 단계별 가이드를 제공합니다. 시작하자!

## .NET용 Aspose.PDF의 잉크 주석 기능 이해

C# 소스 코드를 살펴보기 전에 먼저 잉크 주석이 무엇인지, 그리고 그 용도를 이해해 보겠습니다.

잉크 주석은 PDF 문서에 자유형 잉크 주석을 그리는 방법입니다. 스타일러스나 마우스를 사용하여 주석을 작성할 수 있습니다. 이 기능은 다이어그램, 스케치 또는 기타 유형의 주석을 그려야 하는 상황에서 유용합니다.

## 1단계: 새 문서 만들기

PDF 문서에 잉크 주석을 추가하는 첫 번째 단계는 Document 클래스의 새 인스턴스를 만드는 것입니다. 이는 다음 코드 조각을 사용하여 달성됩니다.

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

여기서는 Document 클래스의 새 인스턴스를 만들고 여기에 새 페이지를 추가합니다.

## 2단계: 잉크 주석 만들기

다음 단계는 InkAnnotation 클래스의 인스턴스를 만드는 것입니다. 이는 다음 코드 조각을 사용하여 수행됩니다.

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(스트로크.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

여기서는 먼저 System.드로잉.Rectangle 클래스를 사용하여 직사각형을 만들고 FromRect 메서드를 사용하여 이를 Aspose.Pdf.Rectangle로 변환합니다. 그런 다음 사각형, 지점 목록 및 주석이 추가된 페이지를 사용하여 InkAnnotation 클래스의 인스턴스를 만듭니다.

그런 다음 제목, 색상, 캡 스타일, 테두리, 불투명도 등 InkAnnotation의 다양한 속성을 설정합니다. 마지막으로 Annotations.Add 메서드를 사용하여 페이지에 주석을 추가합니다.

## 3단계: 문서 저장

마지막 단계는 잉크 주석이 추가된 PDF 문서를 저장하는 것입니다. 이는 다음 코드 조각을 사용하여 달성됩니다.

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

여기서는 출력 파일 이름을 데이터 디렉터리에 연결하고 Save 메서드를 사용하여 문서를 저장합니다.

### .NET용 Aspose.PDF를 사용하여 잉크 주석을 추가하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(스트로크.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
// 출력 파일 저장
doc.Save(dataDir);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에 잉크 주석을 추가하는 방법을 살펴보았습니다. 제공된 단계별 가이드와 C# 소스 코드를 따르면 개발자는 PDF 처리 애플리케이션에서 잉크 주석 기능을 쉽게 구현할 수 있습니다.

### FAQ

#### Q: PDF 문서의 잉크 주석이란 무엇입니까?

A: PDF 문서의 잉크 주석을 사용하면 사용자가 스타일러스나 마우스를 사용하여 자유형 잉크 주석을 그릴 수 있습니다. 손으로 그린 스케치, 다이어그램 또는 기타 자유형 주석을 PDF에 추가하는 데 일반적으로 사용됩니다.

#### Q: 잉크 주석의 모양을 사용자 정의할 수 있습니까?

A: 예, .NET용 Aspose.PDF는 색상, 불투명도, 캡 스타일, 테두리 너비 등과 같은 잉크 주석의 모양을 사용자 정의하는 다양한 속성을 제공합니다. 개발자는 특정 요구 사항에 맞게 이러한 속성을 조정할 수 있습니다.

#### Q: 단일 PDF 페이지에 여러 잉크 주석을 추가할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하여 단일 PDF 페이지에 여러 잉크 주석을 추가할 수 있습니다. 각 잉크 주석에는 고유한 점 집합과 사용자 정의된 모양이 있을 수 있습니다.

#### Q: 기존 PDF 문서에 잉크 주석을 추가할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하면 새로 생성된 PDF 문서와 기존 PDF 파일 모두에 잉크 주석을 추가할 수 있습니다. 기존 PDF를 열고, 잉크 주석을 추가하고, 업데이트된 문서를 저장할 수 있습니다.

#### Q: PDF 문서의 잉크 주석에 대한 일반적인 사용 사례는 무엇입니까?

답변: 잉크 주석은 PDF 양식에 서명이나 손으로 쓴 메모 추가, 건축 청사진이나 엔지니어링 도면에 주석 달기, 공동 검토를 위한 문서 마크업 등 다양한 응용 프로그램에 유용합니다.