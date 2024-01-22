---
title: PDF 파일의 이미지 정보
linktitle: PDF 파일의 이미지 정보
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 이미지 정보를 추출합니다.
type: docs
weight: 160
url: /ko/net/programming-with-images/image-information/
---
이 가이드는 Aspose.PDF for .NET을 사용하여 PDF 파일의 이미지에 대한 정보를 추출하는 방법을 단계별로 안내합니다. 이미 환경을 설정했는지 확인하고 아래 단계를 따르세요.

## 1단계: 문서 디렉터리 정의

 올바른 문서 디렉터리를 설정했는지 확인하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 문서가 있는 디렉토리의 경로가 포함된 코드에

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 원본 PDF 파일 로드

 이 단계에서는 다음을 사용하여 소스 PDF 파일을 로드합니다.`Document` Aspose.PDF의 클래스입니다. 사용`Document` 생성자를 선택하고 PDF 문서의 경로를 전달합니다.

```csharp
Document doc = new Document(dataDir + "ImageInformation.pdf");
```

## 3단계: 기본 해상도 설정

이 단계에서는 이미지의 기본 해상도를 설정합니다. 이 예에서는 기본 해상도가 72로 설정되어 있습니다.

```csharp
int defaultResolution = 72;
```

## 4단계: 개체 및 카운터 초기화

이 단계에서는 이미지 정보를 검색하는 데 필요한 개체와 카운터를 초기화합니다.

```csharp
System.Collections.Stack graphicsState = new System.Collections.Stack();
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
```

## 5단계: 문서의 첫 번째 페이지에서 연산자를 순환합니다.

이 단계에서는 문서 첫 페이지의 연산자를 살펴보고 이미지 관련 작업을 식별합니다.

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

//변환을 위한 GSave 및 GRestore 작업 처리
if (opSaveState != null)
{
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
}
else if (opRestoreState != null)
{
     graphicsState. Pop();
}
// 변환을 위한 ConcatenateMatrix 작업 처리
else if (opCtm != null)
{
     // 변환 행렬 적용
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
         // 이미지 검색
         XImage image = doc.Pages[1].Resources.Images[opDo.Name];
         // 이미지의 크기 검색
         double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
         double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
         // 위의 정보를 바탕으로 해상도를 계산합니다.
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

### .NET용 Aspose.PDF를 사용하는 이미지 정보의 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 소스 PDF 파일 로드
Document doc = new Document(dataDir+ "ImageInformation.pdf");
// 이미지의 기본 해상도 정의
int defaultResolution = 72;
System.Collections.Stack graphicsState = new System.Collections.Stack();
// 이미지 이름을 담을 배열 목록 개체를 정의합니다.
System.Collections.ArrayList imageNames = new System.Collections.ArrayList(doc.Pages[1].Resources.Images.Names);
// 스택할 개체 삽입
graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));
// 문서의 첫 페이지에 있는 모든 연산자를 가져옵니다.
foreach (Operator op in doc.Pages[1].Contents)
{
	// GSave/GRestore 연산자를 사용하여 변환을 이전 설정으로 되돌립니다.
	Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
	Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
	// 현재 변환 행렬을 정의하는 ConcatenateMatrix 객체를 인스턴스화합니다.
	Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
	// 리소스에서 개체를 그리는 Do 연산자를 만듭니다. Form 객체와 Image 객체를 그립니다.
	Aspose.Pdf.Operators.Do opDo = op as Aspose.Pdf.Operators.Do;
	if (opSaveState != null)
	{
		//이전 상태를 저장하고 현재 상태를 스택 맨 위로 푸시합니다.
		graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
	}
	else if (opRestoreState != null)
	{
		// 현재 상태를 버리고 이전 상태를 복원
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
		// 현재 행렬과 상태 행렬을 곱합니다.
		((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
		continue;
	}
	else if (opDo != null)
	{
		// 이미지 그리기 연산자인 경우
		if (imageNames.Contains(opDo.Name))
		{
			System.Drawing.Drawing2D.Matrix lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
			// 첫 번째 PDF 페이지의 이미지를 보관할 XImage 개체 만들기
			XImage image = doc.Pages[1].Resources.Images[opDo.Name];
			// 이미지 크기 가져오기
			double scaledWidth = Math.Sqrt(Math.Pow(lastCTM.Elements[0], 2) + Math.Pow(lastCTM.Elements[1], 2));
			double scaledHeight = Math.Sqrt(Math.Pow(lastCTM.Elements[2], 2) + Math.Pow(lastCTM.Elements[3], 2));
			// 이미지의 높이 및 너비 정보 가져오기
			double originalWidth = image.Width;
			double originalHeight = image.Height;
			// 위의 정보를 바탕으로 해상도를 계산합니다.
			double resHorizontal = originalWidth * defaultResolution / scaledWidth;
			double resVertical = originalHeight * defaultResolution / scaledHeight;
			// 각 이미지의 크기 및 해상도 정보 표시
			Console.Out.WriteLine(
					string.Format(dataDir + "image {0} ({1:.##}:{2:.##}): res {3:.##} x {4:.##}",
								 opDo.Name, scaledWidth, scaledHeight, resHorizontal,
								 resVertical));
		}
	}
}
```

## 결론

축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF 파일에서 이미지 정보를 추출하는 방법을 배웠습니다. 애플리케이션의 다양한 이미지 처리 작업에 이 정보를 사용할 수 있습니다.

### PDF 파일의 이미지 정보에 대한 FAQ

#### Q: Aspose.PDF for .NET을 사용하여 PDF 문서에서 이미지 정보를 추출하는 목적은 무엇입니까?

A: PDF 문서에서 이미지 정보를 추출하면 문서 내 이미지의 크기, 해상도 및 기타 속성에 대한 통찰력을 얻을 수 있습니다. 이 정보는 이미지 처리, 분석 또는 최적화 작업에 사용될 수 있습니다.

#### Q: .NET용 Aspose.PDF는 PDF 문서에서 이미지 정보를 추출하는 데 어떻게 도움이 됩니까?

A: Aspose.PDF for .NET은 이미지를 포함하여 PDF 문서의 내용에 액세스하고 분석하는 도구를 제공합니다. 제공된 코드는 다양한 연산자를 사용하여 이미지 정보를 추출하고 표시하는 방법을 보여줍니다.

#### Q: 이 방법을 사용하면 어떤 종류의 이미지 정보를 추출할 수 있나요?

답변: 이 방법을 사용하면 PDF 문서 내의 이미지에 대한 크기 조정, 해상도 및 이미지 이름과 같은 정보를 추출하고 표시할 수 있습니다.

#### Q: 코드는 PDF 문서 내에서 이미지 관련 연산자를 어떻게 식별하고 처리합니까?

A: 코드는 PDF 문서의 지정된 페이지에서 연산자를 반복합니다. 이미지 작업, 변환 및 렌더링과 관련된 연산자를 식별하고 처리합니다.

#### Q: 기본 해상도의 의미는 무엇이며, 코드에서는 어떻게 사용되나요?

A: 기본 해상도는 이미지의 실제 해상도를 계산하기 위한 기준점으로 사용됩니다. 코드는 크기와 기본 해상도 설정을 기반으로 각 이미지의 해상도를 계산합니다.

#### Q: 추출된 이미지 정보는 실제 상황에서 어떻게 활용될 수 있나요?

A: 추출된 이미지 정보는 이미지 품질 평가, 이미지 최적화, 이미지 썸네일 생성, 이미지 관련 의사결정 프로세스 촉진 등의 작업에 사용될 수 있습니다.

#### Q: 추가 이미지 관련 속성을 추출하도록 코드를 수정할 수 있습니까?

A: 예, 코드를 사용자 정의하여 색상 공간, 픽셀 심도, 이미지 유형 등 이미지의 추가 속성을 추출할 수 있습니다.

#### Q: 이미지 정보 추출 프로세스는 리소스 집약적인가요, 아니면 시간 소모적인가요?

A: 이미지 정보 추출 프로세스는 효율적이고 성능에 최적화되어 리소스 사용 및 처리 시간에 미치는 영향을 최소화합니다.

#### Q: 개발자는 PDF 문서에서 이미지 정보를 식별하고 추출함으로써 어떤 이점을 얻을 수 있습니까?

A: 개발자는 PDF 문서 내의 이미지 특성에 대한 통찰력을 얻을 수 있으므로 이미지 조작, 처리 및 최적화에 관해 정보에 입각한 결정을 내릴 수 있습니다.

#### Q: 이미지가 포함된 PDF 문서의 일괄 처리에 이 방법을 사용할 수 있습니까?

A: 예, 이 방법은 여러 페이지나 문서를 반복하고, 이미지 정보를 추출하고, 이미지 관련 작업을 수행함으로써 일괄 처리로 확장될 수 있습니다.