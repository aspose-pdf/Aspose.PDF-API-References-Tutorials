---
title: PDF 파일의 페이지 배경으로 이미지 설정
linktitle: PDF 파일의 페이지 배경으로 이미지 설정
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 이미지를 PDF 파일의 페이지 배경으로 설정하는 단계별 가이드입니다.
type: docs
weight: 110
url: /ko/net/programming-with-pdf-pages/image-as-background/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 이미지를 페이지 배경으로 설정하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 자신의 프로젝트에서 이 기능을 이해하고 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼이 끝나면 Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지 배경으로 이미지를 추가하는 방법을 알게 됩니다.

## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 개발 환경에 설치된 .NET용 Aspose.PDF

## 1단계: 문서 디렉터리 정의
먼저 문서 디렉터리의 경로를 설정해야 합니다. 편집한 PDF 문서를 저장하려는 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸십시오.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 새 문서 만들기
 그런 다음 다음을 사용하여 새 Document 개체를 만들 수 있습니다.`Document` 수업.

```csharp
Document doc = new Document();
```

## 3단계: 문서에 새 페이지 추가
 이제 다음을 사용하여 Document 개체에 새 페이지를 추가할 수 있습니다.`Add()` 의 방법`Pages` 수업.

```csharp
Page page = doc.Pages.Add();
```

## 4단계: 배경 아티팩트 객체 생성
그런 다음 새 BackgroundArtifact 객체를 생성하여 배경 이미지를 설정할 수 있습니다.

```csharp
BackgroundArtifact background = new BackgroundArtifact();
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
```

## 5단계: 페이지에 배경 추가
그런 다음 다음을 사용하여 BackgroundArtifact 개체를 페이지의 아티팩트 컬렉션에 추가할 수 있습니다.`Artifacts` 의 재산`Page` 수업.

```csharp
page. Artifacts. Add(background);
```

## 6단계: PDF 문서 저장
 마지막으로 다음을 사용하여 PDF 문서를 파일로 저장할 수 있습니다.`Save()` 의 방법`Document`수업. 올바른 경로와 파일 이름을 지정하십시오.

```csharp
doc.Save(dataDir + "ImageAsBackground_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 배경으로 이미지를 위한 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 새 문서 개체 만들기
Document doc = new Document();
// 문서 개체에 새 페이지 추가
Page page = doc.Pages.Add();
// 배경 아티팩트 객체 생성
BackgroundArtifact background = new BackgroundArtifact();
// backgroundartifact 개체의 이미지를 지정합니다.
background.BackgroundImage = File.OpenRead(dataDir + "aspose-total-for-net.jpg");
// 페이지의 아티팩트 컬렉션에 배경 아티팩트 추가
page.Artifacts.Add(background);
dataDir = dataDir + "ImageAsBackground_out.pdf";
// 문서 저장
doc.Save(dataDir);
System.Console.WriteLine("\nImage as page background added successfully.\nFile saved at " + dataDir);

```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 이미지를 페이지 배경으로 설정하는 방법을 배웠습니다. 이 단계별 가이드를 따르면 PDF 문서에 배경 이미지를 쉽게 추가할 수 있습니다. Aspose.PDF는 페이지 배경 사용자 정의를 포함하여 PDF 파일 작업을 위한 강력하고 유연한 API를 제공합니다. 이제 자신의 프로젝트에 이 기능을 적용하여 사용자 정의 배경 이미지가 포함된 PDF 문서를 만들 수 있습니다.

### PDF 파일의 페이지 배경으로 이미지 설정에 대한 FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 이미지를 페이지 배경으로 설정하려면 어떻게 해야 합니까?

A: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 이미지를 페이지 배경으로 설정하려면 다음 단계를 따르세요.

1. 편집한 PDF 문서를 저장할 경로를 지정하여 문서 디렉터리를 설정하세요.
2.  다음을 사용하여 새 Document 개체를 만듭니다.`Document` 수업.
3.  다음을 사용하여 Document 개체에 새 페이지를 추가합니다.`Add()` 의 방법`Pages` 수업.
4.  배경 이미지를 설정하려면 새 BackgroundArtifact 개체를 만듭니다. 다음을 사용하여 이미지 파일을 지정할 수 있습니다.`File.OpenRead()` 방법.
5.  다음을 사용하여 페이지의 아티팩트 컬렉션에 BackgroundArtifact 개체를 추가합니다.`Artifacts` 의 재산`Page` 수업.
6.  다음을 사용하여 PDF 문서를 파일로 저장합니다.`Save()` 의 방법`Document` 클래스를 선택하고 출력에 대한 올바른 경로와 파일 이름을 지정합니다.

#### 질문: PDF 문서의 서로 다른 페이지에 여러 배경 이미지를 추가할 수 있습니까?

A: 예, 각 페이지에 대해 튜토리얼에 설명된 프로세스를 반복하여 PDF 문서의 다른 페이지에 여러 배경 이미지를 추가할 수 있습니다. 각 페이지에 대해 원하는 이미지가 포함된 새 BackgroundArtifact 객체를 생성하고 이를 해당 페이지의 아티팩트 컬렉션에 추가하기만 하면 됩니다.

#### Q: 페이지의 배경 이미지에 이미지 크기 조정이나 위치 지정을 적용할 수 있나요?

 A: 예, 페이지의 배경 이미지에 이미지 크기 조정이나 위치 지정을 적용할 수 있습니다.`background.BackgroundImage` BackgroundArtifact 개체의 속성입니다. BackgroundArtifact를 페이지에 추가하기 전에 너비, 높이, 위치 등의 이미지 속성을 수정하여 이미지가 배경으로 표시되는 방식을 사용자 지정할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 콘텐츠가 포함된 기존 PDF 문서에 배경 이미지 추가를 지원합니까?

A: 예, .NET용 Aspose.PDF를 사용하면 콘텐츠가 포함된 기존 PDF 문서에 배경 이미지를 추가할 수 있습니다. 기존 PDF 문서를 로드하고 원하는 페이지에 배경 이미지를 추가한 다음 업데이트된 문서를 새 파일에 저장하거나 원본 파일을 덮어쓸 수 있습니다.

#### Q: PNG나 BMP 등 다양한 형식의 이미지를 페이지 배경으로 사용할 수 있나요?

A: 예, 튜토리얼에서 사용되는 JPEG 형식 외에도 PNG 또는 BMP와 같은 다양한 형식의 이미지를 페이지 배경으로 사용할 수 있습니다. .NET용 Aspose.PDF는 광범위한 이미지 형식을 지원하며 지원되는 모든 이미지 형식을 PDF 페이지의 배경으로 사용할 수 있습니다.