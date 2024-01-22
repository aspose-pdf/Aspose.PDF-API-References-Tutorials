---
title: PDF 파일에서 이미지 크기 설정
linktitle: PDF 파일에서 이미지 크기 설정
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 이미지 크기를 설정하는 단계별 가이드입니다.
type: docs
weight: 270
url: /ko/net/programming-with-images/set-image-size/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 이미지 크기를 설정하는 방법을 안내합니다. 이 작업을 쉽게 수행하려면 다음 단계를 따르십시오.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Visual Studio 또는 기타 개발 환경이 설치 및 구성되었습니다.
- C# 프로그래밍 언어에 대한 기본 지식입니다.
- .NET용 Aspose.PDF 라이브러리가 설치되었습니다. Aspose 공식 홈페이지에서 다운로드 가능합니다.

## 1단계: PDF 문서 생성

시작하려면 다음 코드를 사용하여 새 PDF 문서를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Document 객체 인스턴스화
Document doc = new Document();

// PDF 파일의 페이지 모음에 페이지 추가
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 2단계: 사진 추가

다음으로 PDF 문서의 페이지에 이미지를 추가하겠습니다. 다음 코드를 사용하세요.

```csharp
// 이미지 인스턴스 만들기
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

// 이미지의 너비와 높이를 포인트 단위로 설정합니다.
img. FixWidth = 100;
img. FixHeight = 100;

// 이미지 유형을 알 수 없음(알 수 없음)으로 설정
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//이미지 소스 파일 경로
img.File = dataDir + "aspose-logo.jpg";

// 페이지의 단락 컬렉션에 이미지 추가
page.Paragraphs.Add(img);
```

이미지 소스 파일의 올바른 경로를 제공해야 합니다.

## 3단계: 페이지 속성 설정

마지막으로 너비와 높이를 포함한 페이지 속성을 설정합니다. 다음 코드를 사용하세요.

```csharp
// 페이지 속성 설정
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### .NET용 Aspose.PDF를 사용하여 이미지 크기 설정에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 객체 인스턴스화
Document doc = new Document();
// PDF 파일의 페이지 모음에 페이지 추가
Aspose.Pdf.Page page = doc.Pages.Add();
// 이미지 인스턴스 만들기
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
// 이미지 너비와 높이를 포인트 단위로 설정
img.FixWidth = 100;
img.FixHeight = 100;
// 이미지 유형을 SVG로 설정
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
// 소스 파일 경로
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//페이지 속성 설정
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
// 결과 PDF 파일 저장
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 PDF 문서의 이미지 크기를 성공적으로 설정했습니다. 이제 이 방법을 자신의 프로젝트에 적용하여 PDF 파일의 이미지 크기를 조정할 수 있습니다.

### PDF 파일의 이미지 크기 설정에 대한 FAQ

#### Q: Aspose.PDF for .NET을 사용하여 PDF 문서의 이미지 크기를 설정하는 목적은 무엇입니까?

답변: PDF 문서에서 이미지 크기를 설정하는 목적은 PDF에 추가될 때 이미지의 크기를 제어하는 것입니다. 이를 통해 PDF 파일 내 이미지의 모양과 레이아웃을 조정할 수 있습니다.

#### Q: PDF 문서에서 이미지 크기 설정 프로세스는 어떻게 진행됩니까?

 A: 프로세스에는`Aspose.Pdf.Image` 인스턴스를 사용하여 너비와 높이를 지정합니다.`FixWidth` 그리고`FixHeight` 속성을 선택한 다음 이미지를 PDF 문서에 추가합니다. 또한 이미지에 맞게 페이지 자체의 크기를 설정할 수도 있습니다.

#### Q: 이미지 크기를 페이지 크기의 특정 비율로 설정할 수 있습니까?

A: 제공된 코드는 이미지의 절대 너비와 높이를 포인트 단위로 설정합니다. 페이지 크기의 백분율을 기준으로 이미지 크기를 설정하려면 그에 따라 크기를 계산하고 이에 따라 코드를 조정해야 합니다.

####  Q. 의의는 무엇인가요?`FileType` property when adding an image to the PDF document?

 답:`FileType`속성은 PDF 문서에 추가되는 이미지 유형을 지정합니다. 제공된 코드에서 값은`Unknown` 는 이미지 유형을 알 수 없음을 나타내며 Aspose.PDF는 파일 확장자를 기반으로 이미지 유형을 결정하려고 시도합니다.

#### Q: 이 방법을 사용하여 단일 페이지에 여러 이미지를 추가할 수 있습니까?

 A: 예, 여러 개의 이미지를 생성하여 단일 페이지에 여러 개의 이미지를 추가할 수 있습니다.`Aspose.Pdf.Image` 인스턴스를 페이지의 단락 컬렉션에 추가합니다. 필요에 따라 이미지의 위치와 레이아웃을 조정하십시오.

#### Q: 페이지에 추가된 이미지의 배치와 정렬을 어떻게 제어할 수 있나요?

 A: 추가된 이미지의 배치와 정렬은 다음과 같은 속성을 사용하여 이미지의 좌표와 레이아웃을 조정하여 제어할 수 있습니다.`img.Left`, `img.Top`, 단락 서식 속성.

####  Q: 페이지 속성을 설정하는 목적은 무엇입니까?`page.PageInfo.Width` and `page.PageInfo.Height`?

A: 페이지 속성을 설정하면 페이지 자체의 크기를 정의할 수 있습니다. 이렇게 하면 페이지 크기가 추가된 이미지와 페이지에 있을 수 있는 기타 콘텐츠를 수용할 수 있게 됩니다.

#### Q: 동일한 PDF 문서 내에서 이미지마다 크기를 다르게 설정할 수 있습니까?

 A: 예, 별도의 이미지를 생성하여 다양한 이미지에 대해 서로 다른 크기를 설정할 수 있습니다.`Aspose.Pdf.Image` 인스턴스 및 조정`FixWidth`, `FixHeight`, 각 이미지의 배치 속성.

#### Q: 이 방법을 내 프로젝트에 통합하여 PDF 파일의 이미지 크기를 설정하려면 어떻게 해야 합니까?

A: 이 방법을 프로젝트에 통합하려면 설명된 단계를 따르고 필요에 따라 코드를 수정하십시오. 이 방법을 사용하면 응용 프로그램의 요구 사항에 따라 PDF 문서에 특정 크기의 이미지를 추가할 수 있습니다.