---
title: PDF 파일에서 문자 강조
linktitle: PDF 파일에서 문자 강조
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 파일에서 문자를 강조 표시하는 방법을 알아보세요.
type: docs
weight: 240
url: /ko/net/programming-with-text/highlight-character-in-pdf/
---
이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 파일에서 문자를 강조 표시하는 방법을 설명합니다. 제공된 C# 소스 코드를 사용하여 PDF에서 문자를 강조 표시하는 단계별 프로세스를 살펴보겠습니다.

## 요구 사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET 라이브러리용 Aspose.PDF가 설치되었습니다.
- C# 프로그래밍에 대한 기본적인 이해.

## 1단계: 문서 디렉토리 설정

 먼저 입력 PDF 파일이 있는 디렉토리 경로를 설정해야 합니다. 바꾸기`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` PDF 파일 경로가 있는 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: PDF 문서 로드

 다음으로, 다음을 사용하여 입력 PDF 문서를 로드합니다.`Aspose.Pdf.Document` 수업.

```csharp
Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
```

## 3단계: PDF를 이미지로 변환

 문자를 강조하기 위해 PDF 문서를 다음을 사용하여 이미지로 변환합니다.`PdfConverter` 클래스. 변환을 위한 해상도를 설정하고 이미지를 검색합니다.`Bitmap` 물체.

```csharp
int resolution = 150;
using (MemoryStream ms = new MemoryStream())
{
     PdfConverter conv = new PdfConverter(pdfDocument);
     conv. Resolution = new Resolution(resolution, resolution);
     conv. GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
     Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
```

## 4단계: 문자 강조

 PDF 문서의 각 페이지를 반복하고 다음을 사용합니다.`TextFragmentAbsorber` 객체는 페이지의 모든 단어를 찾습니다. 그런 다음 텍스트 조각, 세그먼트 및 문자를 반복하여 사각형을 사용하여 강조 표시합니다.

```csharp
using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
{
     // 크기 및 변형 설정
     float scale = resolution / 72f;
     gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);

     // 페이지 반복
     for (int i = 0; i < pdfDocument.Pages.Count; i++)
     {
         Page page = pdfDocument.Pages[1];

         //페이지의 모든 단어를 찾으세요
         TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
         textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
         page. Accept(textFragmentAbsorber);
         TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

         // 텍스트 조각을 반복합니다
         foreach(TextFragment textFragment in textFragmentCollection)
         {
             if (i == 0)
             {
                 // 문자 강조
                 gr.DrawRectangle(
                     Think.Yellow,
                     (float)textFragment.Position.XIndent,
                     (float)textFragment.Position.YIndent,
                     (float)textFragment.Rectangle.Width,
                     (float)textFragment.Rectangle.Height);

                 // 세그먼트를 통한 루프
                 foreach(TextSegment segment in textFragment.Segments)
                 {
                     // 하이라이트 세그먼트
                     gr.DrawRectangle(
                         Think Green,
                         (float)segment.Rectangle.LLX,
                         (float)segment.Rectangle.LLY,
                         (float)segment.Rectangle.Width,
                         (float)segment.Rectangle.Height);

                     // 문자 반복
                     foreach(CharInfo characterInfo in segment.Characters)
                     {
                         // 하이라이트캐릭터
                         gr.DrawRectangle(
                             Think.Black,
                             (float)characterInfo.Rectangle.LLx,
                             (float)characterInfo.Rectangle.LLY,
                             (float)characterInfo.Rectangle.Width,
                             (float)characterInfo.Rectangle.Height);
                     }
                 }
             }
         }
     }
}
```

## 5단계: 출력 이미지 저장

마지막으로 강조된 문자가 포함된 수정된 이미지를 지정된 출력 파일에 저장합니다.

```csharp
dataDir = dataDir + "HighlightCharacterInPDF_out.png";
bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
```

### .NET용 Aspose.PDF를 사용하여 PDF에서 문자 강조 표시를 위한 샘플 소스 코드 
```csharp
try
{
	// 문서 디렉토리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	int resolution = 150;
	Aspose.Pdf.Document pdfDocument = new Aspose.Pdf.Document(dataDir + "input.pdf");
	using (MemoryStream ms = new MemoryStream())
	{
		PdfConverter conv = new PdfConverter(pdfDocument);
		conv.Resolution = new Resolution(resolution, resolution);
		conv.GetNextImage(ms, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap bmp = (Bitmap)Bitmap.FromStream(ms);
		using (System.Drawing.Graphics gr = System.Drawing.Graphics.FromImage(bmp))
		{
			float scale = resolution / 72f;
			gr.Transform = new System.Drawing.Drawing2D.Matrix(scale, 0, 0, -scale, 0, bmp.Height);
			for (int i = 0; i < pdfDocument.Pages.Count; i++)
			{
				Page page = pdfDocument.Pages[1];
				// 모든 단어를 찾기 위해 TextAbsorber 객체를 생성합니다.
				TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber(@"[\S]+");
				textFragmentAbsorber.TextSearchOptions.IsRegularExpressionUsed = true;
				page.Accept(textFragmentAbsorber);
				// 추출된 텍스트 조각을 가져옵니다
				TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
				// 조각을 반복합니다
				foreach (TextFragment textFragment in textFragmentCollection)
				{
					if (i == 0)
					{
						gr.DrawRectangle(
						Pens.Yellow,
						(float)textFragment.Position.XIndent,
						(float)textFragment.Position.YIndent,
						(float)textFragment.Rectangle.Width,
						(float)textFragment.Rectangle.Height);
						for (int segNum = 1; segNum <= textFragment.Segments.Count; segNum++)
						{
							TextSegment segment = textFragment.Segments[segNum];
							for (int charNum = 1; charNum <= segment.Characters.Count; charNum++)
							{
								CharInfo characterInfo = segment.Characters[charNum];
								Aspose.Pdf.Rectangle rect = page.GetPageRect(true);
								Console.WriteLine("TextFragment = " + textFragment.Text + "    Page URY = " + rect.URY +
												  "   TextFragment URY = " + textFragment.Rectangle.URY);
								gr.DrawRectangle(
								Pens.Black,
								(float)characterInfo.Rectangle.LLX,
								(float)characterInfo.Rectangle.LLY,
								(float)characterInfo.Rectangle.Width,
								(float)characterInfo.Rectangle.Height);
							}
							gr.DrawRectangle(
							Pens.Green,
							(float)segment.Rectangle.LLX,
							(float)segment.Rectangle.LLY,
							(float)segment.Rectangle.Width,
							(float)segment.Rectangle.Height);
						}
					}
				}
			}
		}
		dataDir = dataDir + "HighlightCharacterInPDF_out.png";
		bmp.Save(dataDir, System.Drawing.Imaging.ImageFormat.Png);
	}
	Console.WriteLine("\nCharacters highlighted successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http:// Www.aspose.com/purchase/default.aspx.");
}
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서에서 문자를 강조 표시하는 방법을 알아보았습니다. 단계별 가이드를 따르고 제공된 C# 코드를 실행하면 PDF에서 문자를 강조 표시하고 출력을 이미지로 저장할 수 있습니다.

### 자주 묻는 질문

#### 질문: "PDF 파일에서 문자 강조 표시" 튜토리얼의 목적은 무엇인가요?

A: "PDF 파일에서 문자 강조 표시" 튜토리얼은 .NET용 Aspose.PDF 라이브러리를 사용하여 PDF 문서 내의 문자를 강조 표시하는 방법을 설명합니다. 이 튜토리얼은 이를 달성하기 위한 단계별 가이드와 C# 소스 코드를 제공합니다.

#### 질문: PDF 문서에서 문자를 강조 표시하는 이유는 무엇인가요?

답변: PDF 문서에서 문자를 강조하면 특정 콘텐츠를 강조하거나 특정 텍스트를 더 눈에 띄고 구별하기 쉽게 만드는 등 다양한 목적으로 유용할 수 있습니다.

#### 질문: 문서 디렉토리를 어떻게 설정하나요?

A: 문서 디렉토리를 설정하려면:

1.  바꾸다`"YOUR DOCUMENT DIRECTORY"` 에서`dataDir` 입력 PDF 파일이 있는 디렉토리의 경로를 포함하는 변수입니다.

#### 질문: PDF 문서를 로드하고 이미지로 변환하려면 어떻게 해야 하나요?

 A: 튜토리얼에서는`Aspose.Pdf.Document` 클래스는 입력 PDF 문서를 로드하는 데 사용됩니다. 그런 다음,`PdfConverter` 클래스는 PDF 문서를 이미지로 변환하는 데 사용됩니다. 이미지의 해상도가 설정되고 이미지는 다음과 같이 검색됩니다.`Bitmap` 물체.

#### 질문: PDF 문서 이미지에서 문자를 강조 표시하려면 어떻게 해야 하나요?

A: 이 튜토리얼은 PDF 문서의 각 페이지를 반복하면서 단어를 찾는 과정을 안내합니다.`TextFragmentAbsorber`그리고 텍스트 조각, 세그먼트 및 문자를 반복하면서 사각형을 사용하여 강조 표시합니다.

#### 질문: 강조 표시된 문자와 세그먼트의 모양을 사용자 지정할 수 있나요?

대답: 네, 그리기 작업에 사용된 색상과 스타일을 수정하여 강조 표시된 문자와 세그먼트의 모양을 사용자 지정할 수 있습니다.

#### 질문: 강조된 문자가 포함된 수정된 이미지를 어떻게 저장합니까?

 A: 이 튜토리얼에서는 강조 표시된 문자가 있는 수정된 이미지를 지정된 출력 파일에 저장하는 방법을 보여줍니다.`Save` 의 방법`Bitmap` 수업.

#### 질문: 이 튜토리얼을 사용하려면 유효한 Aspose 라이선스가 필요합니까?

A: 네, 이 튜토리얼이 제대로 작동하려면 유효한 Aspose 라이선스가 필요합니다. Aspose 웹사이트에서 전체 라이선스를 구매하거나 30일 임시 라이선스를 얻을 수 있습니다.