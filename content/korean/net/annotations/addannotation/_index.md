---
title: PDF 주석 추가
linktitle: 주석 추가
second_title: .NET API 참조를 위한 Aspose.PDF
description: 이 단계별 가이드를 통해 Aspose.PDF for .NET을 사용하여 PDF에 사용자 정의 주석을 쉽게 추가하세요. 특정 세부 정보와 아이콘으로 주석을 사용자 정의하세요.
type: docs
weight: 10
url: /ko/net/annotations/addannotation/
---
## 소개

주석은 PDF 문서를 풍부하게 만들어 대화형이고 유익한 문서로 만드는 좋은 방법입니다. 공동작업자에게 메모를 남기든 독자에게 추가 정보를 추가하든 주석은 필수적일 수 있습니다. 이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 주석을 추가하는 프로세스를 자세히 살펴보겠습니다. 이 가이드를 마칠 때까지 PDF 파일에 주석을 포함하는 전문가가 될 수 있도록 각 단계를 세분화하겠습니다. 시작해 봅시다!

## 필수 조건

코드를 살펴보기 전에 먼저 필요한 모든 것이 있는지 확인해 보겠습니다.

-  .NET용 Aspose.PDF: Aspose.PDF 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[.NET용 Aspose.PDF 다운로드 페이지](https://releases.aspose.com/pdf/net/).
- 개발 환경: Visual Studio 또는 원하는 다른 C# IDE.
- C#에 대한 기본 지식: 이 가이드에서는 독자가 C# 프로그래밍에 익숙하다고 가정합니다.
- PDF 문서: 주석을 추가할 샘플 PDF 파일입니다.

 아직 Aspose.PDF 라이브러리가 없다면 위 링크에서 가져와서 시작할 수 있습니다.[무료 체험](https://releases.aspose.com/) 또는 구매[특허](https://purchase.aspose.com/buy). 

## 패키지 가져오기

코딩을 시작하기 전에 필요한 네임스페이스를 가져왔는지 확인하세요.

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Annotations;
```

이러한 네임스페이스는 PDF 조작 및 주석에 필요한 클래스와 메서드에 대한 액세스를 제공합니다.

## 1단계: PDF 문서 로드

먼저, 주석을 추가할 PDF 문서를 로드해야 합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DATA DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "AddAnnotation.pdf");
```

 다음은 진행 중인 작업입니다. PDF 파일이 저장된 디렉토리를 지정한 다음 다음을 사용하여 로드합니다.`Document` Aspose.PDF에서 제공하는 클래스입니다. 이 단계는 문서를 로드하지 않고는 변경할 수 없기 때문에 중요합니다.

## 2단계: 주석 만들기

### 주석 속성 정의
 이제 주석 자체를 만들어 보겠습니다. 우리는 다음을 사용할 것입니다.`TextAnnotation`PDF에 주석이나 메모를 추가하는 데 적합한 기능입니다.

```csharp
// 주석 만들기
TextAnnotation textAnnotation = new TextAnnotation(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(200, 400, 400, 600));
textAnnotation.Title = "Sample Annotation Title";
textAnnotation.Subject = "Sample Subject";
textAnnotation.Contents = "Sample contents for the annotation";
textAnnotation.Open = true;
textAnnotation.Icon = TextIcon.Key;
```

이 스니펫에서:
-  위치 및 크기:`Rectangle` 클래스는 주석이 페이지의 어느 위치에 표시될지와 크기를 정의합니다.
- 제목, 주제, 내용: 이러한 속성을 사용하면 주석의 내용과 포함할 내용을 지정할 수 있습니다.
-  아이콘 :`TextIcon.Key` 주석에 아이콘을 설정해서 시각적으로 더 매력적으로 보이도록 합니다.

## 3단계: 주석 모양 사용자 지정

다음으로, 테두리를 추가하고 모양을 조정하여 이 주석을 눈에 띄게 만들어 보겠습니다.

```csharp
Border border = new Border(textAnnotation);
border.Width = 5;
border.Dash = new Dash(1, 1);
textAnnotation.Border = border;
textAnnotation.Rect = new Aspose.Pdf.Rectangle(200, 400, 400, 600);
```

다음은 진행 중인 작업에 대한 세부 내용입니다.
-  테두리 : 우리는 테두리를 만듭니다`Border` 객체를 만들고 너비를 5로 설정하여 주석의 윤곽을 눈에 띄게 표현했습니다.
-  대시 패턴:`Dash` 속성을 사용하면 점선 테두리를 만들어 주석에 약간의 스타일을 추가할 수 있습니다.

## 4단계: PDF 페이지에 주석 추가

주석을 만들고 사용자 지정한 후에는 PDF 페이지에 추가할 차례입니다.

```csharp
// 페이지의 주석 컬렉션에 주석을 추가합니다.
pdfDocument.Pages[1].Annotations.Add(textAnnotation);
```

 이 코드는 PDF의 첫 페이지에 주석을 추가합니다.`Annotations` 컬렉션은 특정 페이지에 대한 모든 주석을 보관하며, 이 단계를 통해 새 주석이 해당 컬렉션에 포함되도록 할 수 있습니다.

## 5단계: 업데이트된 PDF 문서 저장

마지막으로, 주석이 영구적으로 추가되도록 문서를 저장해 보겠습니다.

```csharp
// 출력 파일 저장
dataDir = dataDir + "AddAnnotation_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nAnnotation added successfully.\nFile saved at " + dataDir);
```

새 이름으로 문서를 저장하여 (`AddAnnotation_out.pdf`), 원본 파일을 보존하고 주석이 추가된 새 파일을 생성합니다. 콘솔 메시지는 모든 것이 성공적이었음을 확인하고, 이제 지정된 디렉토리에서 주석이 달린 PDF를 찾을 수 있습니다.

## 결론

PDF에 주석을 추가하는 것은 강력한 기능일 뿐만 아니라 Aspose.PDF for .NET을 사용하면 매우 간단합니다. 검토를 위해 문서를 표시하든 나중에 참조할 수 있도록 메모를 추가하든 이 가이드에서는 알아야 할 모든 것을 다룹니다. 이러한 단계를 따르면 PDF를 풍부하게 하는 사용자 지정 주석을 만들어 더욱 유용하고 상호 작용적으로 만들 수 있습니다.

## 자주 묻는 질문

### Aspose.PDF for .NET을 사용하여 어떤 유형의 주석을 추가할 수 있습니까?
텍스트, 링크, 강조, 스탬프 주석 등 다양한 유형의 주석을 추가할 수 있습니다.

### 주석의 모양을 사용자 지정할 수 있나요?
물론입니다! 주석의 크기, 색상, 테두리, 심지어 아이콘까지 사용자 정의할 수 있습니다.

### 한 페이지에 여러 개의 주석을 추가할 수 있나요?
네, PDF의 어느 페이지에든 필요한 만큼 주석을 추가할 수 있습니다.

### 주석을 추가한 후에 제거할 수 있나요?
 예, 주석은 다음을 사용하여 제거할 수 있습니다.`Annotations.Delete` Aspose.PDF에서 제공하는 방법입니다.

### Aspose.PDF for .NET을 사용하려면 라이선스가 필요합니까?
 예, 모든 기능을 잠금 해제하고 제한을 피하려면 다음이 필요합니다.[특허](https://purchase.aspose.com/buy) . 또한 다음을 얻을 수 있습니다.[임시 면허](https://purchase.aspose.com/temporary-license/) 평가를 위해.