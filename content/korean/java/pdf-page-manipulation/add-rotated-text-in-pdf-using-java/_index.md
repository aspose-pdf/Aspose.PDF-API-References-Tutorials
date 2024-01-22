---
title: Java를 사용하여 PDF에 회전된 텍스트 추가
linktitle: Java를 사용하여 PDF에 회전된 텍스트 추가
second_title: Aspose.PDF 자바 PDF 처리 API
description: Java를 사용하여 PDF 문서에 회전된 텍스트를 삽입하는 방법을 알아보세요. 회전된 텍스트로 PDF를 향상하려면 코드 예제가 포함된 자세한 단계별 가이드를 따르세요.
type: docs
weight: 14
url: /ko/java/pdf-page-manipulation/add-rotated-text-in-pdf-using-java/
---

## 소개

이 포괄적인 튜토리얼에서는 Java를 사용하여 PDF 문서에 회전된 텍스트를 추가하는 과정을 자세히 살펴보겠습니다. 다이어그램에 라벨을 붙이거나, 워터마크를 생성하거나, PDF에 특수 효과를 추가해야 하는 경우 이 가이드가 단계별로 안내해 드립니다. PDF 조작을 위한 강력한 라이브러리인 Aspose.PDF for Java를 사용하여 프로세스를 보여드리겠습니다.

## 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Java 개발 환경: 시스템에 Java가 설치되어 있는지 확인하십시오.

2.  Java용 Aspose.PDF: Aspose.PDF 라이브러리를 다운로드하여 Java 프로젝트에 포함하세요. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/pdf/java/).

## 1단계: 새 PDF 문서 만들기

Aspose.PDF를 사용하여 새 PDF 문서를 만드는 것부터 시작해 보겠습니다. 이 문서는 회전된 텍스트의 캔버스 역할을 합니다.

```java
// PDF 문서 초기화
com.aspose.pdf.Document pdfDocument = new com.aspose.pdf.Document();
```

## 2단계: 페이지 추가

다음으로, 회전된 텍스트를 삽입하려는 PDF 문서에 페이지를 추가합니다.

```java
//문서에 새 페이지 추가
com.aspose.pdf.Page page = pdfDocument.getPages().add();
```

## 3단계: 회전된 텍스트 정의

이제 삽입하고 회전할 텍스트를 정의해 보겠습니다. 요구 사항에 따라 텍스트, 글꼴 및 회전 각도를 사용자 정의할 수 있습니다.

```java
// 텍스트 내용 정의
String text = "Rotated Text Example";

// TextFragment 객체 생성
com.aspose.pdf.TextFragment textFragment = new com.aspose.pdf.TextFragment(text);

// 글꼴 크기 및 스타일 설정
textFragment.getTextState().setFontSize(12);
textFragment.getTextState().setFont(com.aspose.pdf.FontRepository.findFont("Arial"));

// 회전 각도 정의(도 단위)
textFragment.setTextRotation(45);
```

이 예에서는 텍스트를 "회전된 텍스트 예"로 설정하고 Arial 글꼴을 선택하고 글꼴 크기를 12로 설정하고 텍스트를 45도 회전했습니다. 특정 요구 사항에 맞게 이러한 매개 변수를 조정하십시오.

## 4단계: 회전된 텍스트 배치

회전된 텍스트를 배치할 페이지의 위치를 지정합니다.

```java
// 텍스트의 위치를 설정하세요
textFragment.setPosition(new com.aspose.pdf.Position(100, 200));
```

여기서는 페이지의 좌표 (100, 200)에 텍스트를 배치했습니다. 필요한 위치에 정확하게 텍스트를 배치하려면 이러한 좌표를 수정하세요.

## 5단계: 페이지에 회전된 텍스트 추가

이제 페이지에 회전된 텍스트를 추가합니다.

```java
// 페이지에 회전된 텍스트 추가
page.getParagraphs().add(textFragment);
```

## 6단계: PDF 저장

마지막으로 텍스트가 회전된 PDF 문서를 저장합니다.

```java
// PDF 문서 저장
pdfDocument.save("output.pdf");
```

## 결론

이 튜토리얼에서는 Java 및 Java용 Aspose.PDF를 사용하여 PDF 문서에 회전된 텍스트를 추가하는 프로세스를 살펴보았습니다. 새 PDF를 만들고, 사용자 정의 스타일로 회전된 텍스트를 정의하고, 페이지에 배치하고, 수정된 PDF를 저장하는 방법을 배웠습니다.

회전된 텍스트는 다이어그램 레이블 지정, 워터마킹, 문서에 창의적인 요소 추가 등 다양한 목적으로 PDF에 유용한 추가 기능이 될 수 있습니다.

Java용 Aspose.PDF의 기능 덕분에 회전된 텍스트를 쉽게 통합하여 PDF 문서를 향상할 수 있습니다.

---

## FAQ(자주 묻는 질문)

### 1. 동일한 PDF에서 텍스트를 다른 각도로 회전할 수 있나요?
   예, 동일한 PDF 문서에 각도가 다른 회전된 텍스트의 여러 인스턴스를 추가할 수 있습니다. 회전된 텍스트의 각 부분에 대해 이 튜토리얼에 설명된 프로세스를 반복하기만 하면 됩니다.

### 2. 회전된 텍스트의 색상을 어떻게 변경할 수 있나요?
    텍스트 색상을 변경하려면`textFragment.getTextState().setForegroundColor` 방법을 사용하고 RGB 형식으로 색상을 지정합니다. 예를 들어 텍스트 색상을 빨간색으로 설정하려면 다음을 사용하세요.`textFragment.getTextState().setForegroundColor(com.aspose.pdf.Color.getRed());`.

### 3. Aspose.PDF for Java는 무료 라이브러리인가요?
   Aspose.PDF for Java는 강력한 상용 라이브러리이지만 테스트 및 평가를 위한 무료 평가판을 제공합니다. 프로젝트 요구 사항에 따라 적절한 라이선스 옵션을 선택할 수 있습니다.

### 4. 텍스트를 90도 회전하여 세로 텍스트를 만들 수 있나요?
   예, 텍스트를 90도 회전하여 세로 텍스트를 만들 수 있습니다. 회전 각도를 90도로 설정하면 텍스트가 페이지에 수직으로 나타납니다.

### 5. Java에서 PDF 작업을 위한 다른 라이브러리가 있습니까?
   예, iText 및 PDFBox와 같은 여러 라이브러리를 Java에서 PDF 조작에 사용할 수 있습니다. 각 라이브러리에는 고유한 기능이 있으므로 프로젝트 요구 사항에 가장 적합한 라이브러리를 선택하세요.