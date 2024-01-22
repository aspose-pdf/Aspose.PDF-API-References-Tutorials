---
title: 다중 레이어 PDF 파일 만들기 두 번째 접근 방식
linktitle: 다중 레이어 PDF 파일 만들기 두 번째 접근 방식
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 다층 PDF 파일을 만드는 방법을 알아보세요. 텍스트와 이미지가 포함된 동적 PDF를 생성하기 위한 소스 코드가 포함된 단계별 가이드입니다.
type: docs
weight: 80
url: /ko/net/programming-with-document/createmultilayerpdfsecondapproach/
---
이 튜토리얼에서는 .NET용 Aspose.PDF의 두 번째 접근 방식을 사용하여 다중 레이어 PDF 파일을 만드는 방법을 살펴보겠습니다. 자세한 설명과 함께 단계별 가이드를 제공하고 전체 소스 코드를 포함하겠습니다. 이 튜토리얼을 따르면 .NET 애플리케이션에서 Aspose.PDF 라이브러리를 사용하여 여러 레이어가 있는 PDF 문서를 생성할 수 있습니다.

이제 단계별 가이드를 시작해 보겠습니다.

## 1단계: 환경 설정

먼저 Visual Studio를 열고 새 C# 프로젝트를 만듭니다. 프로젝트에서 Aspose.PDF 라이브러리를 참조했는지 확인하세요. 환경을 설정하고 나면 다음 단계로 진행할 준비가 된 것입니다.

## 2단계: 변수 초기화

이 단계에서는 필요한 변수를 초기화하겠습니다. 문서 디렉토리 경로를 설정하고 PDF 레이어에 대한 색상 변수를 정의해야 합니다. 코드 조각은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## 3단계: PDF 문서 만들기

다음으로 PDF 문서를 나타내는 Aspose.Pdf.Document 클래스의 새 인스턴스를 만듭니다. 코드 조각은 다음과 같습니다.

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 4단계: 문서에 페이지 추가

이 단계에서는 PDF 문서에 새 페이지를 추가합니다. 코드 조각은 다음과 같습니다.

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 5단계: 페이지에 텍스트 추가

이제 페이지에 텍스트 조각을 추가하겠습니다. 텍스트는 빨간색의 단락 3 세그먼트로 표시됩니다. 코드 조각은 다음과 같습니다.

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## 6단계: 페이지에 이미지 추가

이 단계에서는 페이지에 이미지를 추가하겠습니다. 이미지는 특정 크기의 부동 상자로 배치됩니다. 코드 조각은 다음과 같습니다.

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## 7단계: PDF 저장

이 단계에서는 PDF를 파일로 저장합니다.

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### .NET용 Aspose.PDF를 사용하여 다층 PDF 두 번째 접근 방식을 생성하기 위한 예제 소스 코드입니다.

```csharp   
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

## 결론

이 기사에서는 Aspose.PDF for .NET의 두 번째 접근 방식을 사용하여 다층 PDF를 만드는 방법을 배웠습니다. 다층 PDF를 생성하는 데 필요한 단계별 지침과 전체 소스 코드를 제공했습니다.

### FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 다층 PDF를 만드는 두 번째 접근 방식은 무엇입니까?

A: .NET용 Aspose.PDF를 사용하여 다층 PDF를 생성하는 두 번째 접근 방식은 부동 상자를 사용하여 텍스트 및 이미지와 같은 콘텐츠 요소를 PDF 문서 내의 다른 레이어에 배치하고 추가하는 것입니다.

#### 질문: 두 번째 접근 방식을 사용하여 PDF 문서에 두 개 이상의 레이어를 추가할 수 있습니까?

A: 예, 두 번째 접근 방식을 사용하면 더 많은 부동 상자를 추가하고 그에 따라 위치를 지정하여 PDF 문서에 여러 레이어를 추가할 수 있습니다. 각 플로팅 상자는 별도의 레이어를 나타내며 각 상자에 콘텐츠 요소를 추가하여 여러 레이어를 만들 수 있습니다.

#### Q: 다중 레이어 PDF를 생성하기 위해 두 번째 접근 방식을 사용하면 어떤 이점이 있습니까?

답변: 두 번째 접근 방식을 사용하면 PDF 문서에 있는 콘텐츠 요소의 위치와 가시성을 정밀하게 제어할 수 있습니다. 레이어 관리와 콘텐츠 정렬에 더 큰 유연성을 제공하므로 복잡한 대화형 문서를 더 쉽게 만들 수 있습니다.

#### Q: Aspose.PDF for .NET은 복잡하고 대화형인 PDF 문서를 만드는 데 적합합니까?

A: 예, .NET용 Aspose.PDF는 복잡하고 대화형인 PDF 문서를 생성하기 위한 광범위한 기능을 제공하는 강력한 라이브러리입니다. 텍스트, 이미지, 표, 하이퍼링크, 양식 필드 추가, 고급 PDF 작업 지원 등 다양한 기능을 제공합니다.

#### Q: 두 번째 접근 방식에서 부동 상자의 모양과 속성을 사용자 정의할 수 있습니까?

A: 예, 크기, 위치, 배경색, 불투명도 등 부동 상자의 모양과 속성을 사용자 정의할 수 있습니다. .NET용 Aspose.PDF는 부동 상자의 스타일 지정 및 위치 지정을 위한 다양한 옵션을 제공합니다.