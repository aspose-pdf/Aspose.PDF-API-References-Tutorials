---
title: PDF에 자식 북마크 추가
linktitle: PDF에 자식 북마크 추가
second_title: Aspose.PDF Java PDF 처리 API
description: Aspose.PDF for Java를 사용하여 자식 북마크로 PDF 문서를 강화하는 방법을 알아보세요. 향상된 탐색 및 구성을 위한 코드 예제가 있는 단계별 가이드.
type: docs
weight: 11
url: /ko/java/pdf-bookmarks/add-child-bookmarks-pdfs/
---

## PDF에 자식 북마크 추가 소개

이 글에서는 Aspose.PDF for Java를 사용하여 PDF 문서에 자식 북마크를 추가하는 방법을 살펴보겠습니다. 자식 북마크는 PDF 문서의 내용을 정리하고 탐색하는 편리한 방법으로, 사용자가 문서 내에서 특정 섹션이나 주제를 더 쉽게 찾을 수 있도록 해줍니다.

## 필수 조건

구현에 들어가기 전에 다음과 같은 전제 조건이 충족되었는지 확인하세요.

- 시스템에 Java 개발 환경이 설치되어 있습니다.
-  Java 라이브러리용 Aspose.PDF. 여기에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/java/).

## 환경 설정하기

1. 제공된 링크에서 Java 라이브러리용 Aspose.PDF를 다운로드하세요.
2. Java 프로젝트에 라이브러리를 추가합니다.

이제 새 PDF 문서를 만들고 단계별로 자식 책갈피를 추가하는 것으로 시작해 보겠습니다.

## 새 PDF 문서 만들기

시작하려면 PDF 문서를 초기화하고 페이지를 추가해야 합니다. 시작하기 위한 코드 조각은 다음과 같습니다.

```java
// PDF 문서 초기화
Document pdfDocument = new Document();

// PDF에 페이지 추가
pdfDocument.getPages().add();
pdfDocument.getPages().add();
```

이 예제에서는 새 PDF 문서를 만들고 두 페이지를 추가했습니다.

## 부모 북마크 추가

부모 북마크는 PDF 문서의 주요 섹션 또는 카테고리 역할을 합니다. 부모 북마크를 만들어 보겠습니다.

```java
// 부모 북마크 만들기
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);
```

두 개의 부모 북마크, "부모 북마크 1"과 "부모 북마크 2"를 추가했습니다.

## 자식 북마크 추가

이제 이전에 만든 부모 북마크에 자식 북마크를 추가할 차례입니다. 자식 북마크는 각 부모 북마크 내의 특정 주제나 하위 섹션을 나타냅니다. 방법은 다음과 같습니다.

```java
// 부모 북마크 1에 자식 북마크 추가
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//부모 북마크 2에 자식 북마크 추가
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);
```

"부모 북마크 1"과 "부모 북마크 2"에 모두 자식 북마크를 추가했습니다.

## 북마크 모양 사용자 지정

북마크의 텍스트와 스타일을 변경하여 북마크의 모양을 사용자 지정할 수 있습니다. 또한 북마크에 아이콘을 추가하여 시각적으로 더 잘 표현할 수 있습니다. 다음은 이를 수행하는 방법의 예입니다.

```java
// 북마크 모양 사용자 정의
parentBookmark.setItalic(true);
childBookmark.setForegroundColor(Color.getGreen());
childBookmark.setIcon(OutlineItemCollection.getItalicIcon());
```

이 예제에서는 부모 책갈피를 기울임체로 만들고, 자식 책갈피의 텍스트 색상을 녹색으로 변경하고, 자식 책갈피에 기울임체 아이콘을 추가했습니다.

## 이벤트 처리

북마크에는 연관된 동작도 있을 수 있습니다. 예를 들어, 사용자가 북마크를 클릭하면 트리거되는 동작을 추가할 수 있습니다. 북마크 클릭 이벤트를 처리하는 방법은 다음과 같습니다.

```java
// 북마크에 작업 추가
GoToAction action = new GoToAction(pdfDocument.getPages().get_Item(1));
childBookmark.setAction(action);
```

이 코드에서는 사용자가 클릭하면 PDF의 두 번째 페이지로 이동하는 "이동" 동작을 자식 책갈피에 추가했습니다.

## PDF 저장하기

필요한 모든 북마크를 추가하고 모양과 동작을 사용자 지정한 후에는 수정된 PDF 문서를 저장할 수 있습니다.

```java
// PDF 문서 저장
pdfDocument.save("output.pdf");
```

이제 자식 책갈피가 포함된 PDF 문서가 준비되었습니다.

## 완전한 소스 코드

다음은 Java용 Aspose.PDF를 사용하여 PDF 문서에 자식 북마크를 추가하는 전체 소스 코드입니다.

```java
// PDF 문서 초기화
Document pdfDocument = new Document();

// PDF에 페이지 추가
pdfDocument.getPages().add();
pdfDocument.getPages().add();

// 부모 북마크 만들기
OutlineItemCollection outline = pdfDocument.getOutlines();
OutlineItemCollection parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 1");
outline.add(parentBookmark);

parentBookmark = new OutlineItemCollection(outline);
parentBookmark.setTitle("Parent Bookmark 2");
outline.add(parentBookmark);

// 부모 북마크 1에 자식 북마크 추가
OutlineItemCollection childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.1");
parentBookmark.add(childBookmark);

childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 1.2");
parentBookmark.add(childBookmark);

//부모 북마크 2에 자식 북마크 추가
childBookmark = new OutlineItemCollection(outline);
childBookmark.setTitle("Child Bookmark 2.1");
parentBookmark.add(childBookmark);

// 북마크 모양 사용자 정의
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

Aspose.PDF for Java를 사용하여 PDF에 자식 북마크를 추가하는 것은 문서의 탐색 및 구성을 강화하는 강력한 기능입니다. 이 문서에 설명된 단계를 따르면 부모 및 자식 북마크가 있는 잘 구성된 PDF를 만들고, 모양을 사용자 지정하고, 사용자 경험을 향상시키기 위한 동작을 추가할 수도 있습니다.

## 자주 묻는 질문

### Java용 Aspose.PDF를 어떻게 다운로드할 수 있나요?

 Java용 Aspose.PDF는 웹사이트에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/pdf/java/).

### 모든 PDF 뷰어에서 자식 책갈피가 지원됩니까?

네, 대부분의 최신 PDF 뷰어에서 자식 책갈피 기능이 지원되며 PDF 문서를 탐색할 때 향상된 사용자 경험을 제공합니다.

### 북마크의 모양을 추가로 사용자 지정할 수 있나요?

네, 문서 디자인에 맞게 텍스트 스타일, 색상, 아이콘을 조정하여 북마크의 모양을 사용자 지정할 수 있습니다.

### 북마크에 어떤 다른 작업을 추가할 수 있나요?

"이동" 동작 외에도 웹 링크를 여는 "URI" 동작이나 북마크를 클릭하면 사용자 정의 스크립트를 실행하는 "JavaScript" 동작과 같은 동작을 추가할 수 있습니다.

### Aspose.PDF for Java는 상업 프로젝트에 적합합니까?

네, Aspose.PDF for Java는 개인 및 상업 프로젝트 모두에 적합하며 PDF 조작 및 생성을 위한 광범위한 기능을 제공합니다.