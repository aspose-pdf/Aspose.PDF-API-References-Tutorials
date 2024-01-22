---
title: PDF 파일에 획 텍스트 채우기
linktitle: PDF 파일에 획 텍스트 채우기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 텍스트를 쉽게 채우고 윤곽을 잡는 방법을 알아보세요.
type: docs
weight: 90
url: /ko/net/programming-with-stamps-and-watermarks/fill-stroke-text/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 텍스트를 채우고 윤곽선을 그리는 방법을 단계별로 안내합니다. 제공된 C# 소스 코드를 사용하여 PDF 파일의 텍스트에 채우기 및 윤곽선 색상을 적용하는 방법을 보여 드리겠습니다.

## 1단계: 환경 설정

시작하기 전에 다음 사항이 있는지 확인하세요.

- 설치된 .NET 개발 환경.
- .NET용 Aspose.PDF 라이브러리가 다운로드되어 프로젝트에서 참조됩니다.

## 2단계: TextState 객체 생성

첫 번째 단계는 고급 속성을 전달하는 TextState 개체를 만드는 것입니다. 방법은 다음과 같습니다.

```csharp
// 고급 속성을 전송하기 위한 TextState 객체 생성
TextState ts = new TextState();

// 외곽선 색상 설정
ts.StrokingColor = Color.Gray;

// 텍스트 렌더링 모드 정의
ts.RenderingMode = TextRenderingMode.StrokeText;
```

위의 코드는 새로운 TextState 객체를 생성하고 윤곽선 색상과 텍스트 렌더링 방법을 설정합니다.

## 3단계: PDF 문서 로드

이제 TextState 개체가 준비되었으므로 텍스트 채우기 및 윤곽선을 적용할 PDF 문서를 로드할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// PDF 문서를 입력으로 로드
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
```

위의 코드는 Aspose.PDF.Facades 라이브러리의 PdfFileStamp 클래스를 사용하여 기존 PDF 문서를 로드합니다.

## 4단계: 텍스트에 채우기 및 획 추가

이제 PDF 문서가 로드되었으므로 텍스트에 채우기와 윤곽선을 추가할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 정의된 텍스트와 속성으로 스탬프(Stamp)를 생성합니다.
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// TextState 개체 바인딩
stamp.BindTextState(ts);

// 원점 X, Y 설정
stamp.SetOrigin(100, 100);
stamp. Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp. IsBackground = false;

// 문서에 스탬프 추가
fileStamp.AddStamp(stamp);
```

위의 코드는 지정된 텍스트와 정의된 채우기 및 획 속성을 사용하여 스탬프를 만듭니다.

## 5단계: 출력 문서 저장

텍스트 스탬프가 추가되면 수정된 PDF 문서를 저장할 수 있습니다. 방법은 다음과 같습니다.

```csharp
// 수정된 문서를 저장하세요
fileStamp.Save(dataDir + "output_out.pdf");
fileStamp.Close();
```

위 코드는 편집된 PDF 문서를 지정된 디렉토리에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 획 텍스트 채우기의 샘플 소스 코드 
```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 고급 속성을 전송하기 위한 TextState 객체 생성
TextState ts = new TextState();

// 획 색상 설정
ts.StrokingColor = Color.Gray;

// 텍스트 렌더링 모드 설정
ts.RenderingMode = TextRenderingMode.StrokeText;

// 입력 PDF 문서 로드
Facades.PdfFileStamp fileStamp = new Facades.PdfFileStamp(new Aspose.Pdf.Document(dataDir + "input.pdf"));
Aspose.Pdf.Facades.Stamp stamp = new Aspose.Pdf.Facades.Stamp();
stamp.BindLogo(new Facades.FormattedText("PAID IN FULL", System.Drawing.Color.Gray, "Arial", Facades.EncodingType.Winansi, true, 78));

// TextState 바인딩
stamp.BindTextState(ts);

// X,Y 원점 설정
stamp.SetOrigin(100, 100);
stamp.Opacity = 5;
stamp.BlendingSpace = Facades.BlendingColorSpace.DeviceRGB;
stamp.Rotation = 45.0F;
stamp.IsBackground = false;

// 스탬프 추가
fileStamp.AddStamp(stamp);
fileStamp.Save(dataDir + "ouput_out.pdf");
fileStamp.Close();

```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 PDF 문서에서 텍스트를 채우고 윤곽을 잡는 방법을 배웠습니다. 이제 이 지식을 적용하여 PDF 문서의 채우기 및 윤곽선 색상을 사용자 정의할 수 있습니다.

### PDF 파일의 채우기 획 텍스트에 대한 FAQ

#### Q: PDF 문서에서 텍스트를 채우고 윤곽을 잡는다는 것은 무엇을 의미하며, 언제 그렇게 해야 합니까?

A: PDF 문서에서 텍스트를 채우고 윤곽을 잡는 작업에는 텍스트 문자 내부(채우기)와 텍스트 주변의 테두리(윤곽선)에 색상을 적용하는 작업이 포함됩니다. 이는 텍스트의 시각적 모양을 향상시키거나, 강조점을 만들거나, PDF 내의 특정 내용을 강조하는 데 사용할 수 있습니다.

#### Q: 제공된 C# 소스 코드는 PDF 파일의 텍스트 채우기 및 개요를 어떻게 수행합니까?

 A: 제공된 소스 코드는`TextState` 윤곽선 색상 및 렌더링 모드와 같은 고급 텍스트 속성을 정의하는 개체입니다. 그런 다음 Aspose.PDF.Facades를 사용하여 기존 PDF 문서를 로드하고 지정된 채우기 및 획 속성이 있는 텍스트가 포함된 스탬프를 만들고 문서에 스탬프를 추가합니다.

####  Q: 이 프로그램의 목적은 무엇입니까?`TextState` object in the code?

 답:`TextState`개체는 텍스트 윤곽선(획) 색상 및 렌더링 모드를 포함한 고급 텍스트 속성을 정의하는 데 사용됩니다. 획 및 채우기 측면에서 텍스트가 표시되는 방식을 사용자 정의할 수 있습니다.

#### Q: 동일한 텍스트의 다른 부분에 다른 채우기 및 윤곽선 색상을 적용할 수 있습니까?

 A: 예, 코드를 수정하여 다른 생성을 생성할 수 있습니다.`TextState` 채우기 및 윤곽선 색상이 뚜렷한 개체를 만들고 별도의 도구를 사용하여 텍스트의 특정 부분에 적용합니다.`Stamp` 사물.

#### 질문: PDF 문서에 이미 있는 텍스트에 채우기 및 윤곽선 색상을 적용할 수 있습니까?

 A: 예, 유사한 원리를 사용하여 적절한 텍스트 개체를 선택하고 원하는 개체가 포함된 스탬프로 추가하여 PDF 문서의 기존 텍스트에 채우기 및 윤곽선 색상을 적용할 수 있습니다.`TextState` 속성.

#### Q: 채워진 텍스트와 윤곽선이 있는 텍스트의 불투명도와 혼합을 어떻게 조정할 수 있나요?

 답변: 제공된 코드를 사용하면 다음을 사용하여 스탬프의 불투명도 및 혼합 속성을 설정할 수 있습니다.`Opacity` 그리고`BlendingSpace`각각 속성. 이러한 값을 조정하여 원하는 시각적 효과를 얻을 수 있습니다.

#### 질문: 동일한 PDF 문서 내의 여러 스탬프에 다양한 채우기 및 윤곽선 색상을 적용하려면 어떻게 해야 합니까?

 A: 여러 개를 만들 수 있습니다.`TextState` 채우기 및 윤곽선 색상이 다른 개체를 만든 다음 별도의 개체를 만듭니다.`Stamp` 각 텍스트 세트에 대한 개체는 고유한 색상으로 표시됩니다. 다음을 사용하여 동일한 PDF 문서에 이러한 스탬프를 추가합니다.`PdfFileStamp` 수업.

#### Q: 윤곽선 및 채워진 텍스트에 Arial 이외의 글꼴을 사용할 수 있습니까?

 A: 예, 글꼴 이름 매개변수를 수정하여 글꼴을 변경할 수 있습니다.`FormattedText` 스탬프를 생성할 때 생성자입니다. 시스템에서 사용 가능한 모든 글꼴을 사용할 수 있습니다.

#### Q: 윤곽선과 채워진 텍스트의 회전 각도를 어떻게 수정할 수 있나요?

 A: 제공된 코드를 사용하면 스탬프의 회전 각도를 설정할 수 있습니다.`Rotation` 재산. 이 속성을 조정하여 텍스트에 대해 원하는 회전 각도를 지정할 수 있습니다.

#### Q: 페이지에서 윤곽선과 채워진 텍스트의 위치와 크기를 어떻게 제어할 수 있나요?

A: 다음을 사용할 수 있습니다.`SetOrigin` 의 방법`Stamp` 페이지에서 스탬프 위치의 X 및 Y 좌표를 설정하는 개체입니다. 또한, 다음에서 글꼴 크기를 조정할 수 있습니다.`FormattedText` 텍스트의 크기를 제어하는 생성자.