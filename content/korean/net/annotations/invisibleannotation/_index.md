---
title: PDF 파일의 보이지 않는 주석
linktitle: PDF 파일의 보이지 않는 주석
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF와 함께 C# 소스 코드를 사용하여 PDF 파일에서 주석을 보이지 않게 하는 방법을 알아보세요. 단계별 가이드.
type: docs
weight: 100
url: /ko/net/annotations/invisibleannotation/
---
PDF 파일의 주석은 실제 내용을 변경하지 않고도 문서에 추가 정보나 메모를 추가할 수 있는 강력한 기능입니다. 텍스트를 강조 표시하거나, 문서의 특정 영역에 주의를 끌거나, 설명이나 피드백을 추가하는 데 사용할 수 있습니다.

PDF 문서에서 사용할 수 있는 다양한 유형의 주석은 다음과 같습니다.

- 텍스트 주석
- 링크 주석
- 스탬프 주석
- 사운드 주석
- 파일 첨부 주석
- 그리고 더 많은

## 1단계: .NET용 Aspose.PDF를 사용하여 PDF 문서에 보이지 않는 주석 만들기

 .NET용 Aspose.PDF를 사용하여 PDF 문서에 보이지 않는 주석을 만들려면 먼저`FreeTextAnnotation` 개체를 선택하고 주석의 위치와 크기를 지정합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
```

 위의 코드에서 우리는`FreeTextAnnotation`개체를 선택하고 PDF 문서의 2페이지에 주석 위치를 지정합니다. 또한 주석에 표시될 텍스트의 글꼴 유형, 크기 및 색상을 지정합니다.

## 2단계: 보이지 않는 주석에 특성 추가

다음으로 테두리 색상, 배경 색상 또는 불투명도와 같은 몇 가지 특성을 주석에 추가할 수 있습니다.

```csharp
annotation.Characteristics.Border = System.Drawing.Color.Red;
```

위 코드에서는 주석의 테두리 색상을 빨간색으로 설정했습니다.

## 3단계: 주석 플래그 설정

주석을 생성하고 해당 특성을 설정한 후에는 주석 플래그를 지정할 수 있습니다. 이 튜토리얼에서는 주석을 인쇄할 수는 있지만 볼 수는 없도록 하려고 합니다.

```csharp
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);
```

## 4단계: 수정된 PDF 문서 저장

마지막으로 새로운 보이지 않는 주석을 사용하여 수정된 PDF 문서를 저장할 수 있습니다.

```csharp
dataDir = dataDir + "InvisibleAnnotation_out.pdf";
doc.Save(dataDir);
```

## .NET용 Aspose.PDF를 사용하여 보이지 않는 주석을 작성하는 방법에 대한 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document doc = new Document(dataDir + "input.pdf");

FreeTextAnnotation annotation = new FreeTextAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(50, 600, 250, 650), new DefaultAppearance("Helvetica", 16, System.Drawing.Color.Red));
annotation.Contents = "ABCDEFG";
annotation.Characteristics.Border = System.Drawing.Color.Red;
annotation.Flags = AnnotationFlags.Print | AnnotationFlags.NoView;
doc.Pages[1].Annotations.Add(annotation);

dataDir = dataDir + "InvisibleAnnotation_out.pdf";
// 출력 파일 저장
doc.Save(dataDir);
// ExEnd:보이지 않는주석
Console.WriteLine("\nAnnotation nvisible successfully.\nFile saved at " + dataDir);
```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에 보이지 않는 주석을 만드는 방법을 배웠습니다. 보이지 않는 주석은 독자에게 표시하지 않고 문서에 추가 정보나 메모를 추가하려는 경우 유용한 기능입니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용하여 개발자는 PDF 문서에서 보이지 않는 주석을 쉽게 만들고 사용자 지정할 수 있습니다. .NET용 Aspose.PDF는 주석 작업을 위한 포괄적인 도구 세트를 제공하여 PDF 파일의 상호 작용성과 유용성을 향상시킬 수 있습니다.

### FAQ

#### Q: PDF 문서에서 보이지 않는 주석이란 무엇입니까?

A: PDF 문서의 보이지 않는 주석은 페이지에는 보이지 않지만 추가 정보나 메모가 포함되어 있는 주석입니다. 독자에게 표시하지 않고 댓글이나 피드백을 추가할 수 있습니다.

#### Q: 보이지 않는 주석에는 어떤 유형의 특성을 추가할 수 있습니까?

A: 표시될 텍스트의 테두리 색상, 배경 색상, 불투명도, 글꼴 유형, 크기 및 색상과 같은 다양한 특성을 보이지 않는 주석에 추가할 수 있습니다.

#### Q: 보이지 않는 주석에 대해 다른 주석 플래그를 설정할 수 있습니까?

A: 예, 요구 사항에 따라 보이지 않는 주석에 대해 다른 주석 플래그를 설정할 수 있습니다. 예를 들어 주석을 인쇄할 수는 있지만 볼 수는 없도록 설정할 수 있습니다.

#### Q: PDF 문서의 특정 페이지에 보이지 않는 주석을 추가하려면 어떻게 해야 합니까?

 답변: PDF 문서의 특정 페이지에 보이지 않는 주석을 추가하려면`FreeTextAnnotation` 개체를 선택하고 해당 페이지에 주석의 위치와 크기를 지정합니다.

#### Q: PDF 파일에서 기존 보이지 않는 주석의 특성을 수정할 수 있습니까?

A: 예, Aspose.PDF for .NET을 사용하여 PDF 파일에 있는 기존 보이지 않는 주석의 특성을 수정할 수 있습니다. 주석의 글꼴 유형, 크기, 색상, 테두리 색상, 배경색, 불투명도 및 기타 속성을 변경할 수 있습니다.