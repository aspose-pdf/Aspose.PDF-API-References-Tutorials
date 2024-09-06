---
title: PDF 파일의 이미지 정보
linktitle: PDF 파일의 이미지 정보
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 이미지 정보를 추출합니다.
type: docs
weight: 160
url: /ko/net/programming-with-images/image-information/
---
이 가이드에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 이미지에 대한 정보를 추출하는 방법을 단계별로 안내합니다. 이미 환경을 설정했는지 확인하고 아래 단계를 따르세요.

## 1단계: 문서 디렉토리 정의

 올바른 문서 디렉토리를 설정했는지 확인하세요. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 코드에 PDF 문서가 있는 디렉토리 경로를 추가합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 소스 PDF 파일 로드

 이 단계에서는 다음을 사용하여 소스 PDF 파일을 로드합니다.`Document` Aspose.PDF 클래스. 사용하세요`Document` 생성자를 사용하여 PDF 문서의 경로를 전달합니다.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## 3단계: 기본 해상도 설정

이 단계에서는 이미지의 기본 해상도를 설정합니다. 이 예에서 기본 해상도는 72로 설정됩니다.

```csharp
int defaultResolution = 72;
```

## 4단계: 객체 및 카운터 초기화

이 단계에서는 이미지 정보를 검색하는 데 필요한 객체와 카운터를 초기화합니다.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## 5단계: 문서의 첫 번째 페이지에서 연산자 순환

이 단계에서는 문서의 첫 페이지에 있는 연산자를 살펴보며 이미지 관련 작업을 식별해 보겠습니다.

```csharp
foreach(Operator op in doc.Pages[1].Contents)
{
```

## 6단계: 운영자 관리 및 이미지 정보 추출

이 단계에서는 다양한 유형의 연산자를 관리하고 이미지에 대한 정보를 추출합니다.

```csharp
Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;

//변환에 대한 GSave 및 GRestore 작업 처리
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// 변환을 위한 ConcatenateMatrix 연산을 처리합니다.
else if (opCtm != null)
{
     // 변환 행렬을 적용합니다
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
        (float)opCtm.Matrix.A,
        (float)opCtm.Matrix.B,
        (float)opCtm.Matrix.C,
        (float)opCtm.Matrix.D,
        (float)opCtm.Matrix.E,
        (float)opCtm.Matrix.F);


     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     keep on going;
}
// 이미지에 대한 Do 작업 처리
else if (opDo != null)
{
     if (imageNames.Contains(opDo.Name))
     {
         // 이미지를 검색합니다
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // 이미지의 크기를 검색합니다
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // 위의 정보를 토대로 해상도를 계산해보세요
         double resHorizontal = originalWidth * defaultResolution / scaledWidth;
         double resVertical = originalHeight * defaultResolution / scaledHeight;
         // 이미지 정보 표시
         Console.Out.WriteLine(
                 string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
     }
}
```

### .NET용 Aspose.PDF를 사용한 이미지 정보에 대한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 원본 PDF 파일을 로드합니다
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// 이미지의 기본 해상도를 정의합니다
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// 이미지 이름을 보관할 배열 목록 객체를 정의합니다.
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// 스택할 객체 삽입
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// 문서의 첫 페이지에 모든 연산자를 가져옵니다.
foreach (Operator op in doc.Pages[1].Contents)
{
	// GSave/GRestore 연산자를 사용하여 변환을 이전에 설정된 상태로 되돌립니다.
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// 현재 변환 행렬을 정의하므로 ConcatenateMatrix 객체를 인스턴스화합니다.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// 리소스에서 객체를 그리는 Do 연산자를 만듭니다. Form 객체와 Image 객체를 그립니다.
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//이전 상태를 저장하고 현재 상태를 스택 맨 위로 푸시합니다.
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// 현재 상태를 버리고 이전 상태를 복원합니다.
		graphicsState.Pop();
	}
	else if (opCtm != null)
	{
		System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
		   (float)opCtm.Matrix.A,
		   (float)opCtm.Matrix.B,
		   (float)opCtm.Matrix.C,
		   (float)opCtm.Matrix.D,
		   (float)opCtm.Matrix.E,
		   (float)opCtm.Matrix.F);
		// 현재 행렬에 상태 행렬을 곱합니다.
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// 이것이 이미지 그리기 연산자인 경우
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// 첫 번째 PDF 페이지의 이미지를 보관하기 위해 XImage 객체를 생성합니다.
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// 이미지 크기 가져오기
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// 이미지의 높이와 너비 정보 가져오기
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// 위 정보를 기반으로 해상도를 계산합니다.
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// 각 이미지의 치수 및 해상도 정보 표시
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## 결론

축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF 파일에서 이미지 정보를 추출하는 방법을 배웠습니다. 이 정보를 응용 프로그램에서 다양한 이미지 처리 작업에 사용할 수 있습니다.

### PDF 파일의 이미지 정보에 대한 FAQ

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 문서에서 이미지 정보를 추출하는 목적은 무엇입니까?

A: PDF 문서에서 이미지 정보를 추출하면 문서 내 이미지의 크기, 해상도 및 기타 속성에 대한 통찰력을 얻을 수 있습니다. 이 정보는 이미지 처리, 분석 또는 최적화 작업에 사용할 수 있습니다.

#### 질문: Aspose.PDF for .NET은 PDF 문서에서 이미지 정보를 추출하는 데 어떻게 도움이 되나요?

A: Aspose.PDF for .NET은 이미지를 포함한 PDF 문서의 내용에 액세스하고 분석하는 도구를 제공합니다. 제공된 코드는 다양한 연산자를 사용하여 이미지 정보를 추출하고 표시하는 방법을 보여줍니다.

#### 질문: 이 방법을 사용하면 어떤 종류의 이미지 정보를 추출할 수 있나요?

답변: 이 방법을 사용하면 PDF 문서 내 이미지의 크기, 해상도, 이미지 이름 등의 정보를 추출하여 표시할 수 있습니다.

#### 질문: 코드는 PDF 문서 내에서 이미지 관련 연산자를 어떻게 식별하고 처리하나요?

A: 이 코드는 PDF 문서의 지정된 페이지에서 연산자를 반복합니다. 이미지 작업, 변환 및 렌더링과 관련된 연산자를 식별하고 처리합니다.

#### 질문: 기본 해상도의 중요성은 무엇이며, 코드에서 어떻게 사용됩니까?

A: 기본 해상도는 이미지의 실제 해상도를 계산하는 기준점으로 사용됩니다. 코드는 각 이미지의 크기와 기본 해상도 설정을 기반으로 해상도를 계산합니다.

#### 질문: 추출된 이미지 정보를 실제 상황에 어떻게 활용할 수 있나요?

A: 추출된 이미지 정보는 이미지 품질 평가, 이미지 최적화, 이미지 썸네일 생성, 이미지 관련 의사 결정 프로세스 촉진 등의 작업에 사용할 수 있습니다.

#### 질문: 추가적인 이미지 관련 속성을 추출하도록 코드를 수정할 수 있나요?

대답: 네, 이미지의 색상 공간, 픽셀 심도, 이미지 유형 등 추가 속성을 추출하기 위해 코드를 사용자 지정할 수 있습니다.

#### 질문: 이미지 정보 추출 과정은 리소스나 시간이 많이 소모되나요?

답변: 이미지 정보 추출 프로세스는 효율적이며 성능에 최적화되어 있어 리소스 사용 및 처리 시간에 미치는 영향을 최소화합니다.

#### 질문: 개발자는 PDF 문서에서 이미지 정보를 식별하고 추출하면 어떤 이점을 얻을 수 있나요?

답변: 개발자는 PDF 문서 내 이미지의 특성에 대한 통찰력을 얻어 이미지 조작, 처리 및 최적화와 관련하여 정보에 입각한 결정을 내릴 수 있습니다.

#### 질문: 이 방법을 이미지가 포함된 PDF 문서의 일괄 처리에 사용할 수 있나요?

대답: 네, 이 방법은 여러 페이지나 문서를 반복하고, 이미지 정보를 추출하고, 이미지 관련 작업을 수행함으로써 일괄 처리로 확장될 수 있습니다.