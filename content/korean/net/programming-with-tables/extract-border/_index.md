---
title: PDF 파일에서 테두리 추출
linktitle: PDF 파일에서 테두리 추출
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 테두리를 추출하는 방법을 알아보세요.
type: docs
weight: 80
url: /ko/net/programming-with-tables/extract-border/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 테두리를 추출하는 방법을 알아 보겠습니다. C#의 소스코드를 단계별로 설명하겠습니다. 이 튜토리얼이 끝나면 PDF 문서에서 테두리를 추출하여 이미지로 저장하는 방법을 알게 됩니다. 시작하자!

## 1단계: 환경 설정
먼저 .NET용 Aspose.PDF를 사용하여 C# 개발 환경을 설정했는지 확인하세요. 라이브러리에 참조를 추가하고 필요한 네임스페이스를 가져옵니다.

## 2단계: PDF 문서 로드
이 단계에서는 지정된 파일에서 PDF 문서를 로드합니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

"YOUR DOCUMENT DIRECTORY"를 PDF 파일이 있는 실제 디렉토리로 바꾸십시오.

## 3단계: 모서리 추출
문서에 포함된 작업을 반복하여 PDF 문서에서 테두리를 추출하겠습니다.

```csharp
Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
     // 모든 콘텐츠 작업 처리
     foreach(Operator op in doc.Pages[1].Contents)
     {
         // 동작 종류를 확인하세요
         // ...
         // 각 작업을 처리하는 코드 추가
     }
}
```

 우리는`graphicsState` 그래픽 상태를 저장하기 위한 스택, 추출된 테두리를 캡처하기 위한 비트맵 이미지,`GraphicsPath` 그리기 경로를 저장하는 객체와 상태 및 색상을 추적하는 기타 변수입니다.

## 4단계: 거래 처리
이 단계에서는 문서의 각 작업을 처리하여 테두리를 추출합니다.

```csharp
// 동작 종류를 확인하세요
if (opSaveState != null)
{
     // 이전 상태를 저장하고 현재 상태를 스택의 맨 위로 푸시합니다.
     graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opRestoreState != null)
{
     // 현재 상태를 삭제하고 이전 상태를 복원합니다.
     graphicsState. Pop();
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opCtm != null)
{
     // 현재 변환 행렬을 검색합니다.
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // 현재 행렬과 상태 행렬을 곱합니다.
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // 마지막 그리기 점 업데이트
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // 선 그리기 처리
     // ...
     // 선 그리기를 처리하는 코드 추가
}
// ...
// 다른 작업을 위한 else if 블록 추가
```

조건을 사용하여 작업 유형을 확인하고 각 작업에 적합한 코드를 실행합니다.

## 5단계: 이미지 백업
마지막으로 추출된 테두리가 포함된 비트맵 이미지를 지정된 파일에 저장합니다.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

출력 이미지를 저장하려면 올바른 디렉터리와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.PDF를 사용하여 테두리 추출의 소스 코드 예

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// 기본 CTM 매트릭스 값은 1,0,0,1,0,0입니다.
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//시스템.드로잉 좌표계는 왼쪽 위를 기반으로 하고 PDF 좌표계는 왼쪽 아래를 기반으로 하므로 반전 행렬을 적용해야 합니다.
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// 모든 컨텐츠 명령 처리
	foreach (Operator op in doc.Pages[1].Contents)
	{
		Aspose.Pdf.Operators.GSave opSaveState = op as Aspose.Pdf.Operators.GSave;
		Aspose.Pdf.Operators.GRestore opRestoreState = op as Aspose.Pdf.Operators.GRestore;
		Aspose.Pdf.Operators.ConcatenateMatrix opCtm = op as Aspose.Pdf.Operators.ConcatenateMatrix;
		Aspose.Pdf.Operators.MoveTo opMoveTo = op as Aspose.Pdf.Operators.MoveTo;
		Aspose.Pdf.Operators.LineTo opLineTo = op as Aspose.Pdf.Operators.LineTo;
		Aspose.Pdf.Operators.Re opRe = op as Aspose.Pdf.Operators.Re;
		Aspose.Pdf.Operators.EndPath opEndPath = op as Aspose.Pdf.Operators.EndPath;
		Aspose.Pdf.Operators.Stroke opStroke = op as Aspose.Pdf.Operators.Stroke;
		Aspose.Pdf.Operators.Fill opFill = op as Aspose.Pdf.Operators.Fill;
		Aspose.Pdf.Operators.EOFill opEOFill = op as Aspose.Pdf.Operators.EOFill;
		Aspose.Pdf.Operators.SetRGBColor opRGBFillColor = op as Aspose.Pdf.Operators.SetRGBColor;
		Aspose.Pdf.Operators.SetRGBColorStroke opRGBStrokeColor = op as Aspose.Pdf.Operators.SetRGBColorStroke;

		if (opSaveState != null)
		{
			//이전 상태를 저장하고 현재 상태를 스택 맨 위로 푸시합니다.
			graphicsState.Push(((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Clone());
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opRestoreState != null)
		{
			// 현재 상태를 버리고 이전 상태를 복원
			graphicsState.Pop();
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
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
			lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
		}
		else if (opMoveTo != null)
		{
			lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
		}
		else if (opLineTo != null)
		{
			System.Drawing.PointF linePoint = new System.Drawing.PointF((float)opLineTo.X, (float)opLineTo.Y);
			graphicsPath.AddLine(lastPoint, linePoint);

			lastPoint = linePoint;
		}
		else if (opRe != null)
		{
			System.Drawing.RectangleF re = new System.Drawing.RectangleF((float)opRe.X, (float)opRe.Y, (float)opRe.Width, (float)opRe.Height);
			graphicsPath.AddRectangle(re);
		}
		else if (opEndPath != null)
		{
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opRGBFillColor != null)
		{
			fillColor = opRGBFillColor.getColor();
		}
		else if (opRGBStrokeColor != null)
		{
			strokeColor = opRGBStrokeColor.getColor();
		}
		else if (opStroke != null)
		{
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.DrawPath(new System.Drawing.Pen(strokeColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opFill != null)
		{
			graphicsPath.FillMode = FillMode.Winding;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
		else if (opEOFill != null)
		{
			graphicsPath.FillMode = FillMode.Alternate;
			graphicsPath.Transform(lastCTM);
			graphicsPath.Transform(inversionMatrix);
			gr.FillPath(new System.Drawing.SolidBrush(fillColor), graphicsPath);
			graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
		}
	}
}
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);

Console.WriteLine("\nBorder extracted successfully as image.\nFile saved at " + dataDir);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 테두리를 추출하는 방법을 배웠습니다. 이 단계별 가이드를 사용하여 다른 PDF 문서에서 테두리를 추출할 수 있습니다.

### PDF 파일의 테두리 추출에 대한 FAQ

#### Q: PDF 파일에서 테두리를 추출하는 목적은 무엇입니까?

A: PDF 파일에서 테두리를 추출하는 것은 다양한 목적에 유용할 수 있습니다. 이를 통해 테이블, 다이어그램, 그래픽 요소 등 문서의 구조적 요소를 분리하고 분석할 수 있습니다. 추출된 테두리를 사용하여 PDF 문서 내 콘텐츠의 레이아웃, 크기 및 위치를 식별할 수 있습니다.

#### 질문: PDF 문서 내의 특정 페이지나 영역에서 테두리를 추출할 수 있습니까?

A: 예, 제공된 C# 소스 코드를 수정하여 PDF 문서 내의 특정 페이지나 영역에서 테두리를 추출할 수 있습니다. 조작하여`doc.Pages` 수집하고 사용자 정의 기준을 지정하면 특정 페이지나 관심 영역에서 테두리를 추출하도록 선택할 수 있습니다.

#### Q: 출력 이미지 형식과 품질을 어떻게 사용자 정의할 수 있나요?

 A: 제공된 C# 코드에서는 추출된 테두리가 PNG 이미지로 저장됩니다. 출력 이미지 형식을 변경하려면`ImageFormat.Png` 매개변수`bitmap.Save` JPEG, BMP 또는 GIF와 같은 지원되는 다른 이미지 형식에 대한 방법입니다. 또한 요구 사항에 따라 이미지 품질이나 압축 설정을 조정할 수 있습니다.

#### Q: 추출된 테두리에 대해 어떤 다른 작업을 수행할 수 있습니까?

A: 테두리를 이미지로 추출한 후에는 이미지 처리 라이브러리나 알고리즘을 사용하여 추가로 처리할 수 있습니다. 필요한 경우 이미지를 분석하고, 이미지 필터를 적용하고, 패턴을 감지하거나 OCR(광학 문자 인식)을 수행하여 이미지에서 텍스트를 추출할 수 있습니다.

#### Q: 복잡한 PDF 문서에서 테두리를 추출할 때 제한 사항이나 고려 사항이 있습니까?

A: PDF 문서의 복잡성에 따라 추출 과정이 달라질 수 있습니다. 여러 레이어, 투명도 또는 고급 그래픽이 포함된 복잡한 PDF의 경우 테두리를 정확하게 추출하려면 추가 처리 또는 조정이 필요할 수 있습니다. 신뢰할 수 있는 결과를 보장하려면 다양한 PDF 문서에서 추출 프로세스를 철저하게 테스트하는 것이 중요합니다.