---
title: PDF 파일에 이미지 추가
linktitle: PDF 파일에 이미지 추가
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에 이미지를 쉽게 추가할 수 있습니다.
type: docs
weight: 10
url: /ko/net/programming-with-images/add-image/
---
이 가이드는 .NET용 Aspose.PDF를 사용하여 PDF 파일에 이미지를 추가하는 방법을 단계별로 안내합니다. 이미 환경을 설정했는지 확인하고 아래 단계를 따르세요.

## 1단계: 문서 디렉터리 정의

 시작하기 전에 문서에 대한 올바른 디렉토리를 설정했는지 확인하십시오. 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 문서가 있는 디렉토리의 경로가 포함된 코드에

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 문서 열기

이 단계에서는 다음을 사용하여 PDF 문서를 엽니다.`Document` Aspose.PDF의 클래스입니다. 사용`Document` 생성자를 선택하고 PDF 문서의 경로를 전달합니다.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## 3단계: 이미지 좌표 설정

 추가하려는 이미지의 좌표를 설정합니다. 변수`lowerLeftX`, `lowerLeftY`, `upperRightX` 그리고`upperRightY` 각각 이미지의 왼쪽 하단 모서리와 오른쪽 상단 모서리의 좌표를 나타냅니다.

```csharp
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
```

## 4단계: 이미지를 추가해야 하는 페이지 가져오기

PDF 문서의 특정 페이지에 이미지를 추가하려면 먼저 해당 페이지를 검색해야 합니다. 이 예에서는 문서의 두 번째 페이지(색인 1)에 이미지를 추가합니다.

```csharp
Page page = pdfDocument.Pages[1];
```

## 5단계: 스트림에서 이미지 로드

 이제 PDF 문서에 추가하려는 이미지를 로드하겠습니다. 이 예에서는 다음과 같은 이미지 파일이 있다고 가정합니다.`aspose-logo.jpg` 문서와 동일한 디렉토리에 있습니다. 필요한 경우 파일 이름을 바꾸십시오.

```csharp
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
```

## 6단계: 페이지 자산에 이미지 추가

PDF 문서의 이미지를 사용하려면 해당 이미지를 페이지의 리소스 이미지 컬렉션에 추가해야 합니다.

```csharp
page.Resources.Images.Add(imageStream);
```

## 7단계: 현재 그래픽 상태 저장

 이미지를 그리기 전에 다음을 사용하여 현재 그래픽 상태를 저장해야 합니다.`GSave` 운영자. 이렇게 하면 그래픽 상태에 대한 변경 사항을 나중에 롤백할 수 있습니다.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
```

## 8단계: Rectangle 및 Matrix 개체 만들기

 이제 우리는`Rectangle` 객체와`Matrix`물체. 직사각형은 이미지의 위치와 크기를 나타내고, 매트릭스는 이미지 배치 방법을 정의합니다.

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lower

LeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
```

## 9단계: 이미지 배치를 위한 행렬 연결

 직사각형에 이미지를 배치하는 방법을 지정하려면 다음을 사용합니다.`ConcatenateMatrix` 운영자. 이 연산자는 이미지의 좌표 공간을 페이지의 좌표 공간에 매핑하는 변환 행렬을 정의합니다.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
```

## 10단계: 이미지 그리기

 이 단계에서는 다음을 사용하여 페이지에 이미지를 그릴 것입니다.`Do` 운영자. 그만큼`Do` 연산자는 리소스에서 이미지 이름을 가져와 페이지에 그립니다.

```csharp
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
```

## 11단계: 그래픽 상태 복원

 이미지를 그린 후에는 다음을 사용하여 이전 그래픽 상태를 복원해야 합니다.`GRestore` 운영자.

```csharp
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
```

## 12단계: 업데이트된 문서 저장

 마지막으로 업데이트된 문서를 새 파일에 저장하겠습니다. 업데이트`dataDir` 원하는 출력 디렉터리와 파일 이름으로 변수를 지정합니다.

```csharp
dataDir = dataDir + "AddImage_out.pdf";
pdfDocument.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용하여 이미지 추가에 대한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir+ "AddImage.pdf");
// 좌표 설정
int lowerLeftX = 100;
int lowerLeftY = 100;
int upperRightX = 200;
int upperRightY = 200;
//이미지를 추가해야 하는 페이지 가져오기
Page page = pdfDocument.Pages[1];
// 스트림에 이미지 로드
FileStream imageStream = new FileStream(dataDir + "aspose-logo.jpg", FileMode.Open);
// 페이지 리소스의 이미지 컬렉션에 이미지 추가
page.Resources.Images.Add(imageStream);
// GSave 연산자 사용: 이 연산자는 현재 그래픽 상태를 저장합니다.
page.Contents.Add(new Aspose.Pdf.Operators.GSave());
// Rectangle 및 Matrix 개체 만들기
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(lowerLeftX, lowerLeftY, upperRightX, upperRightY);
Matrix matrix = new Matrix(new double[] { rectangle.URX - rectangle.LLX, 0, 0, rectangle.URY - rectangle.LLY, rectangle.LLX, rectangle.LLY });
// ConcatenateMatrix(연결 행렬) 연산자 사용: 이미지를 배치하는 방법을 정의합니다.
page.Contents.Add(new Aspose.Pdf.Operators.ConcatenateMatrix(matrix));
XImage ximage = page.Resources.Images[page.Resources.Images.Count];
// Do 연산자 사용: 이 연산자는 이미지를 그립니다.
page.Contents.Add(new Aspose.Pdf.Operators.Do(ximage.Name));
// GRestore 연산자 사용: 이 연산자는 그래픽 상태를 복원합니다.
page.Contents.Add(new Aspose.Pdf.Operators.GRestore());
dataDir = dataDir + "AddImage_out.pdf";
// 업데이트된 문서 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage added successfully.\nFile saved at " + dataDir); 
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에 이미지를 추가하는 방법을 배웠습니다. 문서 열기부터 업데이트된 버전 저장까지 모든 단계를 자세히 다루었습니다. 이 가이드를 따르면 이제 C# 및 Aspose.PDF를 사용하여 프로그래밍 방식으로 이미지를 PDF 파일에 포함할 수 있습니다.

### PDF 파일에 이미지 추가에 대한 FAQ

#### Q: PDF 문서에 이미지를 추가하려는 이유는 무엇입니까?

A: PDF 문서에 이미지를 추가하면 시각적 콘텐츠가 향상되고, 추가 컨텍스트가 제공되거나, PDF 파일에 로고와 그래픽이 포함될 수 있습니다.

#### Q: PDF 문서 내의 특정 페이지에 이미지를 추가할 수 있습니까?

A: 예, 이미지를 추가하려는 페이지를 지정할 수 있습니다. 제공된 코드에서 이미지는 PDF 문서의 두 번째 페이지에 추가됩니다.

#### Q: 추가된 이미지의 위치와 크기를 어떻게 조정하나요?

 A: 다음을 수정할 수 있습니다.`lowerLeftX`, `lowerLeftY`, `upperRightX` , 그리고`upperRightY` 코드의 변수를 사용하여 이미지의 좌표를 설정하고 페이지에서의 크기와 위치를 제어합니다.

#### Q: 이 방법을 사용하면 어떤 유형의 이미지 형식을 추가할 수 있나요?

A: 제공된 코드 예제에서는 JPG 이미지(`aspose-logo.jpg`). .NET용 Aspose.PDF는 PNG, BMP, GIF 등을 포함한 다양한 이미지 형식을 지원합니다.

#### Q: 추가된 이미지가 지정된 좌표 내에 맞는지 어떻게 확인합니까?

 A: 좌표와 크기를 조정하세요.`Rectangle` 물체 (`rectangle`이미지의 크기와 페이지에서의 원하는 위치를 일치시킵니다.

#### Q: 단일 PDF 페이지에 여러 이미지를 추가할 수 있습니까?

A: 예, 각 이미지에 대한 프로세스를 반복하고 그에 따라 좌표 및 기타 매개변수를 조정하여 단일 PDF 페이지에 여러 이미지를 추가할 수 있습니다.

####  Q: 어떻게 되나요?`GSave` and `GRestore` operator work in the code?

 답:`GSave` 연산자는 현재 그래픽 상태를 저장하므로 전체 그래픽 컨텍스트에 영향을 주지 않고 변경할 수 있습니다. 그만큼`GRestore` 연산자는 변경이 이루어진 후 이전 그래픽 상태를 복원합니다.

#### Q: 지정된 경로에서 이미지 파일을 찾을 수 없으면 어떻게 되나요?

A: 지정된 경로에서 이미지 파일을 찾을 수 없으면 이미지 스트림을 로드하려고 할 때 코드에서 예외가 발생합니다. 이미지 파일이 올바른 디렉터리에 있는지 확인하세요.

#### Q: 이미지 배치와 모양을 추가로 맞춤 설정할 수 있나요?

 A: 예.`Matrix`개체를 만들고 코드 내에서 다른 연산자를 조정합니다. 고급 사용자 정의에 대해서는 Aspose.PDF 문서를 참조하세요.

#### Q: 이미지가 PDF에 성공적으로 추가되었는지 테스트하려면 어떻게 해야 합니까?

A: 제공된 코드를 적용하여 이미지를 추가한 후 수정된 PDF 파일을 열고 이미지가 지정된 페이지에 올바른 위치로 표시되는지 확인하세요.

#### Q: 이미지를 추가하면 PDF 문서의 원본 내용에 영향을 미치나요?

A: 이미지를 추가해도 PDF 문서의 원본 내용에는 영향을 미치지 않습니다. 시각적 요소를 포함하여 문서를 향상시킵니다.