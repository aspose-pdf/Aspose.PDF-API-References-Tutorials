---
title: 페이지에서 모든 주석 가져오기
linktitle: 페이지에서 모든 주석 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: 이 단계별 가이드를 통해 .NET용 Aspose.PDF를 사용하여 PDF 페이지에서 모든 주석을 검색하는 방법을 알아보세요.
type: docs
weight: 70
url: /ko/net/annotations/getallannotationsfrompage/
---
이 문서에서는 Aspose.PDF for .NET을 사용하여 PDF 페이지에서 모든 주석을 추출하는 과정을 안내합니다. Aspose.PDF for .NET은 개발자가 PDF 문서를 생성, 편집 및 변환할 수 있는 라이브러리입니다. 이 가이드의 도움으로 제공된 C# 소스 코드를 사용하여 특정 PDF 페이지에서 모든 주석을 얻을 수 있습니다.

.NET용 Aspose.PDF를 사용하여 PDF 페이지의 모든 주석을 얻는 방법은 아래 단계를 따르십시오.

## 1단계: 문서 디렉토리 경로

.NET용 Aspose.PDF를 사용하여 PDF 페이지에서 모든 주석을 가져오는 첫 번째 단계는 PDF 파일이 저장된 문서 디렉터리의 경로를 설정하는 것입니다. 다음 코드 줄을 수정하여 이 작업을 수행할 수 있습니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```
## 2단계: PDF 파일이 저장됩니다.

"YOUR DOCUMENT DIRECTORY"를 PDF 파일이 저장된 폴더의 경로로 바꾸십시오. 예를 들어:

```csharp
string dataDir = @"C:\Users\JohnDoe\Documents\PDFs\";
```

## 3단계: 문서 열기

다음 단계는 추출하려는 주석이 포함된 PDF 문서를 여는 것입니다. 다음 코드를 추가하면 됩니다.

```csharp
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");
```

이 코드 줄은 Document 클래스의 새 인스턴스를 초기화하고 PDF 문서 "GetAllAnnotationsFromPage.pdf"를 로드합니다. 이 파일 이름을 PDF 파일 이름으로 바꾸십시오.

## 4단계: 모든 주석을 반복합니다.

PDF 문서를 열면 특정 페이지의 모든 주석을 반복해서 살펴볼 수 있습니다. 예를 들어 PDF 문서의 첫 번째 페이지에 있는 모든 주석을 반복하려면 다음 코드를 추가하세요.

```csharp
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
    // 코드는 여기에 표시됩니다.
}
```

이 코드는 PDF 문서의 첫 번째 페이지에 있는 모든 주석을 반복하고 각 주석을 "annotation" 변수에 할당합니다.

## 5단계: 주석 속성 가져오기

각 주석의 속성을 추출하려면 foreach 루프 내에 다음 코드를 추가하면 됩니다.

```csharp
Console.WriteLine("Title : {0} ", annotation.Title);
Console.WriteLine("Subject : {0} ", annotation.Subject);
Console.WriteLine("Contents : {0} ", annotation.Contents);
```

이 코드는 각 주석의 제목, 주제 및 내용을 콘솔에 기록합니다.

### .NET용 Aspose.PDF를 사용하여 페이지에서 모든 주석 가져오기에 대한 예제 소스 코드

다음은 .NET용 Aspose.PDF를 사용하여 PDF 페이지에서 모든 주석을 가져오는 전체 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서 열기
Document pdfDocument = new Document(dataDir + "GetAllAnnotationsFromPage.pdf");

// 모든 주석을 반복합니다.
foreach (MarkupAnnotation annotation in pdfDocument.Pages[1].Annotations)
{
	// 주석 속성 가져오기
	Console.WriteLine("Title : {0} ", annotation.Title);
	Console.WriteLine("Subject : {0} ", annotation.Subject);
	Console.WriteLine("Contents : {0} ", annotation.Contents);                
}
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서의 특정 페이지에서 모든 주석을 얻는 방법을 살펴보았습니다. 단계별 가이드를 따르고 제공된 C# 소스 코드를 사용하여 개발자는 PDF 문서에서 주석을 쉽게 추출하고 관리할 수 있습니다.

### FAQ

#### Q: PDF 문서의 주석이란 무엇입니까?

답변: PDF 문서의 주석은 문서의 특정 부분에 대한 추가 정보, 설명 또는 메모를 제공하는 대화형 요소입니다. 주석에는 텍스트 메모, 설명, 강조 표시 및 기타 대화형 요소가 포함될 수 있습니다.

#### Q: 특정 페이지에서만 주석을 받을 수 있나요?

A: 예, .NET용 Aspose.PDF를 사용하면 요구 사항에 따라 특정 페이지 또는 전체 문서에서 주석을 얻을 수 있습니다.

#### Q: .NET용 Aspose.PDF는 비밀번호로 보호된 PDF 파일에서 주석 추출을 지원합니까?

 A: 예, .NET용 Aspose.PDF는 비밀번호로 보호된 PDF 파일에서 주석 추출을 지원합니다. PDF 문서를 로드할 때 올바른 비밀번호를 제공해야 합니다.`Document` 수업.

#### Q: 콘텐츠나 작성자 등 속성을 기준으로 주석을 필터링할 수 있습니까?

A: 예, .NET용 Aspose.PDF는 콘텐츠, 작성자 또는 생성 날짜와 같은 속성을 기반으로 주석에 액세스하고 필터링하는 방법을 제공합니다. 모든 주석을 반복하여 필터링하려는 특정 속성을 확인할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 다양한 유형의 PDF 문서에서 주석 추출을 지원합니까?

A: 예, .NET용 Aspose.PDF는 텍스트 마크업 주석, 자유 텍스트 주석 등을 포함하여 다양한 유형의 PDF 문서에서 주석을 추출하는 다양한 방법을 제공합니다.