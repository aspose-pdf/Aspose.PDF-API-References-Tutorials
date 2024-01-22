---
title: PDF 주석 추가
linktitle: 주석 추가
second_title: .NET API 참조용 Aspose.PDF
description: 이 C# 소스 코드를 사용하여 .NET용 Aspose.PDF로 텍스트 PDF 주석을 추가하는 방법을 알아보세요. 특정 세부정보와 아이콘으로 주석을 맞춤설정하세요.
type: docs
weight: 10
url: /ko/net/annotations/addannotation/
---
PDF 문서에 주석을 추가하는 것은 공동 작업 및 검토 프로세스를 향상시킬 수 있는 강력한 기능입니다. .NET용 Aspose.PDF를 사용하면 C#을 사용하여 프로그래밍 방식으로 PDF 문서에 주석을 쉽게 추가할 수 있습니다. 이 가이드에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에 주석을 추가하는 방법을 단계별로 설명합니다.

## 1단계: 새 프로젝트 생성 및 .NET용 Aspose.PDF 설치

주석 추가를 위한 코드 작성을 시작하기 전에 새 프로젝트를 만들고 .NET용 Aspose.PDF를 설치해야 합니다. .NET용 Aspose.PDF를 설치하려면 다음 단계를 따르세요.

1. Visual Studio를 열고 새 C# 프로젝트를 만듭니다.
2. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 "NuGet 패키지 관리"를 선택합니다.
3. "Aspose.PDF"를 검색하고 "설치"를 선택하세요.

설치가 완료되면 코드 작성을 시작할 수 있습니다.

## 2단계: PDF 문서 열기

주석을 추가하는 첫 번째 단계는 PDF 문서를 여는 것입니다. 다음 코드를 사용하여 문서를 열 수 있습니다.

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

이 코드에서는 열려는 PDF 문서의 경로를 지정합니다. "YOUR DATA DIRECTORY"를 데이터 디렉터리의 실제 경로로 바꾸십시오.

## 3단계: 주석 생성

 주석을 추가하려면`TextAnnotation` 수업. 다음 코드를 사용하여 새 텍스트 주석을 만들 수 있습니다.

```csharp
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

이 코드에서는 PDF 문서의 두 번째 페이지에 새 텍스트 주석을 만듭니다. 또한 주석의 제목, 제목, 상태, 내용, 열기 및 아이콘 속성을 설정합니다.

## 4단계: 주석 사용자 정의

 다음을 사용하여 주석의 모양을 사용자 정의할 수 있습니다.`Border` 수업. 다음 코드를 사용하여 주석 테두리를 맞춤설정할 수 있습니다.

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

 이 코드에서는 새로운`Border`개체를 선택하고 너비와 대시 속성을 설정합니다. 그런 다음`Border` 새 주석에 대한 주석 속성`Border` 물체. 마지막으로 우리는`Rect` 위치와 크기를 지정하는 주석의 속성입니다.

## 5단계: PDF 문서에 주석 추가

주석을 생성하고 사용자 정의한 후에는 이를 PDF 문서에 추가해야 합니다. 다음 코드를 사용하여 PDF 문서에 주석을 추가할 수 있습니다.

```csharp
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

이 코드에서는 PDF 문서의 두 번째 페이지에 있는 주석 컬렉션에 주석을 추가합니다.

## 6단계: 출력 파일 저장

마지막으로 주석이 추가된 PDF 문서를 저장해야 합니다. 다음 코드를 사용하여 출력 파일을 저장할 수 있습니다.

```csharp
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
```
### .NET용 Aspose.PDF를 사용하여 주석을 추가하는 예제 소스 코드


```csharp   
 // 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DATA DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");

// 주석 만들기
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.State = AnnotationState.Accepted;
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;

Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);

// 페이지의 주석 컬렉션에 주석 추가
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
dataDir = dataDir + "AddAnnotation_out.pdf";
// 출력 파일 저장
pdfDocument.Save(dataDir);
```
이 코드는 .NET용 Aspose.PDF를 사용하여 PDF 페이지에 특정 제목, 주제, 상태, 내용 및 아이콘이 포함된 텍스트 주석을 추가하는 방법을 보여줍니다. PDF 문서에 주석을 추가하기 위한 요구 사항에 따라 이 코드를 수정할 수 있습니다. 귀하의 데이터 디렉토리를 PDF 파일이 있고 출력 파일을 저장하려는 실제 디렉토리 경로로 바꾸십시오.

## 결론

.NET용 Aspose.PDF를 사용하여 PDF 문서에 주석을 추가하면 문서 공동 작업 및 검토 프로세스를 향상시키는 귀중한 도구를 제공합니다. 이 문서에 제공된 단계별 가이드를 따르면 개발자는 주석 기능을 C# 애플리케이션에 원활하게 통합할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 어떤 유형의 주석을 추가할 수 있습니까?

A: .NET용 Aspose.PDF는 텍스트 주석, 스탬프, 링크, 모양 등을 포함한 다양한 유형의 주석을 지원합니다. 개발자는 특정 요구 사항에 맞게 이러한 주석의 모양과 속성을 사용자 정의할 수 있습니다.

#### 질문: 여러 페이지로 구성된 PDF 문서의 특정 페이지에 주석을 추가할 수 있습니까?

A: 예, .NET용 Aspose.PDF를 사용하면 주석을 추가하려는 페이지를 지정할 수 있습니다. 필요에 따라 특정 페이지를 선택하거나 여러 페이지에 주석을 추가할 수 있습니다.

#### Q: 주석의 모양을 어떻게 사용자 정의합니까?

A: 테두리 너비, 색상, 대시 스타일, 텍스트 스타일 등과 같은 속성을 사용하여 주석을 사용자 정의할 수 있습니다. .NET용 Aspose.PDF는 주석 모양을 맞춤화할 수 있는 다양한 옵션 세트를 제공합니다.

#### Q: .NET용 Aspose.PDF를 사용하여 하이퍼링크를 주석으로 추가할 수 있습니까?

A: 예, Aspose.PDF for .NET을 사용하여 PDF 문서에 하이퍼링크를 주석으로 추가할 수 있습니다. 하이퍼링크 주석을 사용하여 외부 URL이나 동일한 문서 내의 특정 위치에 연결할 수 있습니다.

#### Q: 원본 내용을 변경하지 않고 기존 PDF 문서에 주석을 추가할 수 있습니까?

A: 예, .NET용 Aspose.PDF는 PDF 문서의 원본 내용을 변경하지 않고 추가 요소로 주석을 추가합니다. 원본 PDF 내용은 그대로 유지됩니다.