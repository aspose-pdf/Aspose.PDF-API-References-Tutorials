---
title: PDF에 하위 책갈피 추가
linktitle: PDF에 하위 책갈피 추가
second_title: Aspose.PDF 자바 PDF 처리 API
description: Aspose.PDF for Java를 사용하여 하위 북마크로 PDF 문서를 향상시키는 방법을 알아보세요. 향상된 탐색 및 구성을 위한 코드 예제가 포함된 단계별 가이드입니다.
type: docs
weight: 11
url: /ko/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## PDF에 하위 책갈피 추가 소개

이 기사에서는 Aspose.PDF for Java를 사용하여 PDF 문서에 하위 북마크를 추가하는 방법을 살펴보겠습니다. 하위 책갈피는 PDF 문서의 내용을 구성하고 탐색하는 편리한 방법으로, 사용자가 문서 내의 특정 섹션이나 주제를 더 쉽게 찾을 수 있도록 해줍니다.

## 전제조건

구현을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 Java 개발 환경이 설치되어 있습니다.
-  Java 라이브러리용 Aspose.PDF. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/java/).

## 환경 설정

1. 제공된 링크에서 Java 라이브러리용 Aspose.PDF를 다운로드하세요.
2. Java 프로젝트에 라이브러리를 추가합니다.

이제 새 PDF 문서를 만들고 단계별로 하위 책갈피를 추가하는 것부터 시작해 보겠습니다.

## 새 PDF 문서 만들기

시작하려면 PDF 문서를 초기화하고 페이지를 추가해야 합니다. 시작하기 위한 코드 조각은 다음과 같습니다.

```java
// PDF 문서 초기화
Document pdfDocument = new Document();

// PDF에 페이지 추가
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

이 예에서는 새 PDF 문서를 만들고 여기에 두 페이지를 추가했습니다.

## 상위 북마크 추가

상위 책갈피는 PDF 문서의 주요 섹션 또는 카테고리 역할을 합니다. 몇 가지 상위 북마크를 만들어 보겠습니다.

```java
// 상위 북마크 만들기
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

"상위 북마크 1"과 "상위 북마크 2"라는 두 개의 상위 북마크를 추가했습니다.

## 하위 북마크 추가

이제 앞서 만든 상위 북마크에 하위 북마크를 추가할 차례입니다. 하위 북마크는 각 상위 북마크 내의 특정 주제나 하위 섹션을 나타냅니다. 방법은 다음과 같습니다.

```java
// 상위 북마크 1에 하위 북마크 추가
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//상위 북마크 2에 하위 북마크 추가
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

"상위 북마크 1"과 "상위 북마크 2" 모두에 하위 북마크를 추가했습니다.

## 북마크 모양 사용자 정의

텍스트와 스타일을 변경하여 북마크 모양을 사용자 정의할 수 있습니다. 또한 더 나은 시각적 표현을 위해 책갈피에 아이콘을 추가할 수 있습니다. 이를 수행하는 방법의 예는 다음과 같습니다.

```java
// 북마크 모양 맞춤설정
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

이 예에서는 상위 북마크를 기울임꼴로 만들고, 하위 북마크의 텍스트 색상을 녹색으로 변경하고, 하위 북마크에 기울임꼴 아이콘을 추가했습니다.

## 이벤트 처리

북마크에는 이와 관련된 작업이 있을 수도 있습니다. 예를 들어, 사용자가 북마크를 클릭할 때 트리거되는 작업을 추가할 수 있습니다. 북마크 클릭 이벤트를 처리하는 방법은 다음과 같습니다.

```java
// 북마크에 작업 추가
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

이 코드에서는 사용자가 클릭하면 PDF의 두 번째 페이지로 이동하는 "GoTo" 작업을 하위 책갈피에 추가했습니다.

## PDF 저장

필요한 북마크를 모두 추가하고 북마크의 모양과 작업을 사용자 정의한 후에는 수정된 PDF 문서를 저장할 수 있습니다.

```java
// PDF 문서 저장
pdfDocument.save("output.pdf");
```

이제 하위 북마크가 포함된 PDF 문서가 준비되었습니다.

## 완전한 소스 코드

다음은 Aspose.PDF for Java를 사용하여 PDF 문서에 하위 북마크를 추가하는 전체 소스 코드입니다.

```java
// PDF 문서 초기화
Document pdfDocument = new Document();

// PDF에 페이지 추가
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// 상위 북마크 만들기
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// 상위 북마크 1에 하위 북마크 추가
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//상위 북마크 2에 하위 북마크 추가
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// 북마크 모양 맞춤설정
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());

// 북마크에 작업 추가
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);

// PDF 문서 저장
pdfDocument.save("output.pdf");
```

## 결론

Aspose.PDF for Java를 사용하여 PDF에 하위 책갈피를 추가하는 것은 문서의 탐색 및 구성을 향상시키는 강력한 기능입니다. 이 문서에 설명된 단계를 따르면 상위 및 하위 책갈피가 포함된 잘 구성된 PDF를 만들고, 모양을 사용자 정의하고, 작업을 추가하여 사용자 경험을 향상시킬 수도 있습니다.

## FAQ

### Java용 Aspose.PDF를 어떻게 다운로드할 수 있나요?

 웹사이트에서 Java용 Aspose.PDF를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/java/).

### 모든 PDF 뷰어에서 하위 북마크가 지원됩니까?

예, 하위 북마크는 대부분의 최신 PDF 뷰어에서 지원되며 PDF 문서 탐색을 위한 향상된 사용자 경험을 제공합니다.

### 북마크 모양을 추가로 맞춤설정할 수 있나요?

예, 문서 디자인에 맞게 텍스트 스타일, 색상, 아이콘을 조정하여 책갈피 모양을 사용자 정의할 수 있습니다.

### 북마크에 추가할 수 있는 다른 작업은 무엇입니까?

"GoTo" 작업 외에도 웹 링크를 여는 "URI" 작업이나 책갈피를 클릭할 때 사용자 정의 스크립트를 실행하는 "JavaScript" 작업과 같은 작업을 추가할 수 있습니다.

### Aspose.PDF for Java는 상업용 프로젝트에 적합합니까?

예, Aspose.PDF for Java는 개인 및 상업용 프로젝트 모두에 적합하며 PDF 조작 및 생성을 위한 광범위한 기능을 제공합니다.