---
title: XImage 컬렉션에 이미지 저장
linktitle: XImage 컬렉션에 이미지 저장
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 XImage 컬렉션에 이미지를 저장하는 단계별 가이드입니다.
type: docs
weight: 290
url: /ko/net/programming-with-images/store-image-in-ximage-collection/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 XImage 컬렉션에 이미지를 저장하는 방법을 안내합니다. 이 작업을 쉽게 수행하려면 다음 단계를 따르십시오.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Visual Studio 또는 기타 개발 환경이 설치 및 구성되었습니다.
- C# 프로그래밍 언어에 대한 기본 지식입니다.
- .NET용 Aspose.PDF 라이브러리가 설치되었습니다. Aspose 공식 홈페이지에서 다운로드 가능합니다.

## 1단계: PDF 문서 초기화

시작하려면 다음 코드를 사용하여 새 PDF 문서를 초기화하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//문서 초기화
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
```

## 2단계: XImage 컬렉션에 이미지 추가

다음으로 PDF 문서의 XImage 컬렉션에 이미지를 추가하겠습니다. 다음 코드를 사용하세요.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
```

이미지 소스 파일의 올바른 경로를 제공해야 합니다.

## 3단계: 페이지에 이미지 배치

이제 PDF 문서의 페이지에 이미지를 배치해 보겠습니다. 다음 코드를 사용하세요.

```csharp
page. Contents. Add(new GSave());

// 좌표 설정
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});

// ConcatenateMatrix 연산자 사용: 이미지 배치 방법 정의
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page. Contents. Add(new GRestore());
```

그러면 페이지의 지정된 좌표에 이미지가 배치됩니다.

## 4단계: PDF 문서 저장

마지막으로 업데이트된 PDF 문서를 저장하겠습니다. 다음 코드를 사용하세요.

```csharp
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

최종 PDF 문서에 대해 원하는 경로와 파일 이름을 제공하십시오.

### .NET용 Aspose.PDF를 사용하여 XImage 컬렉션에 이미지 저장을 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 초기화
Aspose.Pdf.Document document = new Document();
document.Pages.Add();
Page page = document.Pages[1];
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
page.Resources.Images.Add(imageStream, ImageFilterType.Flate);
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new GSave());
// 좌표 설정
int lowerLeftX = 0;
int lowerLeftY = 0;
int upperRightX = 600;
int upperRightY = 600;
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] {rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY});
// ConcatenateMatrix(연결 행렬) 연산자 사용: 이미지를 배치하는 방법을 정의합니다.
page.Contents.Add(new ConcatenateMatrix(matrix));
page.Contents.Add(new Do(ximage.Name));
page.Contents.Add(new GRestore());
document.Save(dataDir + "FlateDecodeCompression.pdf");
```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 XImage 컬렉션에 이미지를 성공적으로 저장했습니다. 이제 이 방법을 자신의 프로젝트에 적용하여 PDF 파일의 이미지를 조작하고 개인화할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 XImage 컬렉션에 이미지를 저장하는 목적은 무엇입니까?

A: XImage 컬렉션에 이미지를 저장하면 PDF 문서 내의 이미지를 효율적으로 관리하고 사용할 수 있습니다. 이 접근 방식을 사용하면 이미지를 특정 페이지에 배치하기 전에 이미지를 조작, 사용자 정의 및 개인화할 수 있습니다.

#### Q: XImage 컬렉션에 이미지를 저장하는 것과 PDF 페이지에 이미지를 직접 배치하는 것은 어떻게 다릅니까?

A: XImage 컬렉션에 이미지를 저장하면 이미지를 관리하는 보다 체계적이고 재사용 가능한 방법이 제공됩니다. 페이지에 이미지를 직접 배치하는 대신 컬렉션에 저장한 다음 필요할 때 이름으로 참조할 수 있으므로 관리 및 수정이 더 쉽습니다.

#### Q: 단일 PDF 문서 내의 XImage 컬렉션에 여러 이미지를 추가할 수 있습니까?

A: 예, 동일한 PDF 문서 내의 XImage 컬렉션에 여러 이미지를 추가할 수 있습니다. 각 이미지에는 컬렉션의 고유한 이름이 할당되며, 이 이름은 이미지를 참조하고 다른 페이지에 배치하는 데 사용할 수 있습니다.

#### Q: XImage 컬렉션의 PDF 페이지에 이미지를 배치할 때 이미지의 위치와 크기를 어떻게 지정합니까?

A: 이미지의 위치와 크기를 지정하려면 직사각형과 행렬 변환을 정의해야 합니다. 직사각형은 이미지의 경계를 정의하고, 행렬 변환은 해당 직사각형 내에 이미지를 배치하는 방법을 지정합니다.

####  Q: 이 프로그램의 목적은 무엇입니까?`GSave()` and `GRestore()` operators in the code for placing the image?

 답:`GSave()` 그리고`GRestore()` 연산자는 PDF 페이지의 그래픽 상태를 저장하고 복원하는 데 사용됩니다. 이렇게 하면 이미지 배치와 같이 페이지에서 수행되는 작업이 이미지 배치 후 페이지 상태에 영향을 주지 않습니다.

#### Q: XImage 컬렉션에 저장된 이미지에 추가 수정이나 변형을 적용할 수 있습니까?

A: 예, XImage 컬렉션에 저장된 이미지에 다양한 수정 및 변환을 적용할 수 있습니다. Aspose.PDF for .NET에서 제공하는 적절한 작업과 기술을 사용하여 회전, 크기 조정, 자르기 및 기타 변환을 수행할 수 있습니다.

#### Q: 이 방법을 내 프로젝트에 통합하여 PDF 문서의 XImage 컬렉션에 이미지를 저장하고 배치하려면 어떻게 해야 합니까?

A: 이 방법을 통합하려면 설명된 단계를 따르고 프로젝트 요구 사항에 맞게 코드를 수정하십시오. XImage 컬렉션을 사용하여 이미지를 저장 및 관리한 다음 지정된 좌표 및 변환을 사용하여 특정 페이지에 이미지를 배치할 수 있습니다.

#### Q: .NET용 Aspose.PDF에서 XImage 컬렉션으로 작업할 때 고려 사항이나 제한 사항이 있습니까?

A: XImage 컬렉션은 이미지를 관리하고 조작하는 강력한 방법을 제공하지만 메모리 사용량 및 이미지에 수행되는 작업의 복잡성과 같은 요소를 고려하는 것이 중요합니다. 자원의 수집을 주의 깊게 관리하고 자원을 효율적으로 활용하는 것이 좋습니다.

#### Q: 여러 PDF 문서에서 XImage 컬렉션에 저장된 이미지를 재사용할 수 있습니까?

A: XImage 컬렉션은 각 PDF 문서에만 적용되며 문서 간 재사용을 위해 설계되지 않았습니다. 여러 문서에서 이미지를 재사용해야 하는 경우 각 문서마다 별도로 저장하고 관리해야 합니다.