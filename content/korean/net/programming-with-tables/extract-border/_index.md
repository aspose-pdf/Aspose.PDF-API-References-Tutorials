---
title: PDF 파일에서 테두리 추출
linktitle: PDF 파일에서 테두리 추출
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 테두리를 추출하는 방법을 알아보세요.
type: docs
weight: 80
url: /ko/net/programming-with-tables/extract-border/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 테두리를 추출하는 방법을 알아봅니다. C# 소스 코드를 단계별로 설명합니다. 이 튜토리얼을 마치면 PDF 문서에서 테두리를 추출하여 이미지로 저장하는 방법을 알게 됩니다. 시작해 봅시다!

## 1단계: 환경 설정
먼저 Aspose.PDF for .NET으로 C# 개발 환경을 설정했는지 확인하세요. 라이브러리에 참조를 추가하고 필요한 네임스페이스를 가져옵니다.

## 2단계: PDF 문서 로딩
이 단계에서는 지정된 파일에서 PDF 문서를 로드합니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

"YOUR DOCUMENT DIRECTORY"를 PDF 파일이 있는 실제 디렉토리로 바꿔야 합니다.

## 3단계: 엣지 추출
PDF 문서에 포함된 연산을 반복하여 문서에서 테두리를 추출합니다.

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
         // 작업 유형을 확인하세요
         // ...
         // 각 작업을 처리하기 위한 코드를 추가합니다.
     }
}
```

 우리는 만듭니다`graphicsState` 그래픽 상태를 저장하기 위한 스택, 추출된 테두리를 캡처하기 위한 비트맵 이미지`GraphicsPath` 그리기 경로와 상태 및 색상을 추적하기 위한 기타 변수를 저장하는 객체입니다.

## 4단계: 거래 처리
이 단계에서는 문서의 각 작업을 처리하여 테두리를 추출합니다.

```csharp
// 작업 유형을 확인하세요
if (opSaveState != null)
{
     // 이전 상태를 저장하고 현재 상태를 스택 맨 위로 푸시합니다.
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
     // 현재 변환 행렬을 검색합니다
     System.Drawing.Drawing2D.Matrix cm = new System.Drawing.Drawing2D.Matrix(
         (float)opCtm.Matrix.A,
         (float)opCtm.Matrix.B,
         (float)opCtm.Matrix.C,
         (float)opCtm.Matrix.D,
         (float)opCtm.Matrix.E,
         (float)opCtm.Matrix.F);

     // 현재 행렬에 상태 행렬을 곱합니다.
     ((System.Drawing.Drawing2D.Matrix)graphicsState.Peek()).Multiply(cm);
     lastCTM = (System.Drawing.Drawing2D.Matrix)graphicsState.Peek();
}
else if (opMoveTo != null)
{
     // 마지막 그리기 지점을 업데이트합니다
     lastPoint = new System.Drawing.PointF((float)opMoveTo.X, (float)opMoveTo.Y);
}
else if (opLineTo != null)
{
     // 선 그리기를 처리하다
     // ...
     // 선 그리기를 처리하기 위한 코드 추가
}
// ...
// 다른 작업을 위해 else if 블록을 추가합니다.
```

조건을 사용하여 연산 유형을 확인하고 각 연산에 적합한 코드를 실행합니다.

## 5단계: 백업 이미지
마지막으로 추출된 테두리가 포함된 비트맵 이미지를 지정된 파일에 저장합니다.

```csharp
dataDir = dataDir + "ExtractBorder_out.png";
bitmap.Save(dataDir, ImageFormat.Png);
```

출력 이미지를 저장하려면 올바른 디렉토리와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.PDF를 사용하여 테두리 추출을 위한 예제 소스 코드

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "input.pdf");

Stack graphicsState = new Stack();
System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap((int)doc.Pages[1].PageInfo.Width, (int)doc.Pages[1].PageInfo.Height);
System.Drawing.Drawing2D.GraphicsPath graphicsPath = new System.Drawing.Drawing2D.GraphicsPath();
// 기본 ctm 매트릭스 값은 1,0,0,1,0,0입니다.
System.Drawing.Drawing2D.Matrix lastCTM = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, 0);
//시스템.그리기 좌표계는 좌측 상단을 기준으로 하고, pdf 좌표계는 좌측 하단을 기준으로 하므로 역행렬을 적용해야 합니다.
System.Drawing.Drawing2D.Matrix inversionMatrix = new System.Drawing.Drawing2D.Matrix(1, 0, 0, -1, 0, (float)doc.Pages[1].PageInfo.Height);
System.Drawing.PointF lastPoint = new System.Drawing.PointF(0, 0);
System.Drawing.Color fillColor = System.Drawing.Color.FromArgb(0, 0, 0);
System.Drawing.Color strokeColor = System.Drawing.Color.FromArgb(0, 0, 0);

using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bitmap))
{
	gr.SmoothingMode = SmoothingMode.HighQuality;
	graphicsState.Push(new System.Drawing.Drawing2D.Matrix(1, 0, 0, 1, 0, 0));

	// 모든 내용 명령을 처리합니다
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
			// 현재 상태를 버리고 이전 상태를 복원합니다.
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

			// 현재 행렬에 상태 행렬을 곱합니다.
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
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 테두리를 추출하는 방법을 알아보았습니다. 이 단계별 가이드를 사용하여 다른 PDF 문서에서 테두리를 추출할 수 있습니다.

### PDF 파일에서 테두리 추출에 대한 FAQ

#### 질문: PDF 파일에서 테두리를 추출하는 목적은 무엇인가요?

A: PDF 파일에서 테두리를 추출하는 것은 다양한 목적에 유용할 수 있습니다. 이를 통해 표, 다이어그램 또는 그래픽 요소와 같은 문서의 구조적 요소를 분리하고 분석할 수 있습니다. 추출된 테두리를 사용하여 PDF 문서 내 콘텐츠의 레이아웃, 치수 및 위치를 식별할 수 있습니다.

#### 질문: PDF 문서 내 특정 페이지나 영역의 테두리를 추출할 수 있나요?

A: 네, 제공된 C# 소스 코드를 수정하여 PDF 문서 내의 특정 페이지나 영역에서 테두리를 추출할 수 있습니다.`doc.Pages` 테두리를 수집하고 사용자 정의 기준을 지정하여 특정 페이지나 관심 영역에서 테두리를 추출할 수 있습니다.

#### 질문: 출력 이미지 형식과 품질을 어떻게 사용자 지정할 수 있나요?

 A: 제공된 C# 코드에서 추출된 테두리는 PNG 이미지로 저장됩니다. 출력 이미지 형식을 변경하려면 다음을 수정할 수 있습니다.`ImageFormat.Png` 매개변수에서`bitmap.Save` JPEG, BMP 또는 GIF와 같은 다른 지원되는 이미지 형식으로 변환하는 방법. 또한 요구 사항에 따라 이미지 품질이나 압축 설정을 조정할 수 있습니다.

#### 질문: 추출된 테두리에서 어떤 다른 작업을 수행할 수 있나요?

A: 테두리를 이미지로 추출한 후에는 이미지 처리 라이브러리나 알고리즘을 사용하여 추가로 처리할 수 있습니다. 이미지를 분석하고, 이미지 필터를 적용하고, 패턴을 감지하거나, 필요한 경우 OCR(광학 문자 인식)을 수행하여 이미지에서 텍스트를 추출할 수 있습니다.

#### 질문: 복잡한 PDF 문서에서 테두리를 추출할 때 제한 사항이나 고려 사항이 있나요?

A: 추출 프로세스는 PDF 문서의 복잡성에 따라 다를 수 있습니다. 여러 레이어, 투명도 또는 고급 그래픽이 있는 복잡한 PDF는 테두리를 정확하게 추출하기 위해 추가 처리 또는 조정이 필요할 수 있습니다. 신뢰할 수 있는 결과를 보장하기 위해 다양한 PDF 문서에서 추출 프로세스를 철저히 테스트하는 것이 필수적입니다.