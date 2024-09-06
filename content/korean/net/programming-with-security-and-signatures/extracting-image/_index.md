---
title: 이미지 추출
linktitle: 이미지 추출
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 PDF 문서에서 이미지를 쉽게 추출하세요.
type: docs
weight: 70
url: /ko/net/programming-with-security-and-signatures/extracting-image/
---
PDF 문서에서 이미지를 추출하는 것은 많은 경우에 유용할 수 있습니다. Aspose.PDF for .NET을 사용하면 다음 소스 코드를 사용하여 이미지를 쉽게 추출할 수 있습니다.

## 1단계: 필요한 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 가져오기 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 이미지를 추출하려는 PDF 파일이 들어 있는 폴더의 경로를 지정해야 합니다. 바꾸기`"YOUR DOCUMENTS DIRECTORY"` 다음 코드에서는 문서 폴더의 실제 경로를 사용합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## 3단계: PDF 문서에서 이미지 추출

이제 다음 코드를 사용하여 PDF 문서에서 이미지를 추출해 보겠습니다.

```csharp
using (Document pdfDocument = new Document(input))
{
foreach(Field field in pdfDocument.Form)
{
SignatureField sf = field as SignatureField;
if (sf != null)
{
string outFile = dataDir + @"output_out.jpg";
using (Stream imageStream = sf.ExtractImage())
{
if (imageStream != null)
{
using (Image image = Bitmap.FromStream(imageStream))
{
image.Save(outFile, ImageFormat.Jpeg);
}
}
}
}
}
}
```

이 예에서 우리는 PDF 문서의 각 폼 필드를 반복합니다. 서명 필드가 발견되면 연관된 이미지를 추출하여 JPEG 파일에 저장합니다.

### .NET용 Aspose.PDF를 사용하여 이미지 추출을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir+ @"ExtractingImage.pdf";
using (Document pdfDocument = new Document(input))
{
	foreach (Field field in pdfDocument.Form)
	{
		SignatureField sf = field as SignatureField;
		if (sf != null)
		{
			string outFile = dataDir+ @"output_out.jpg";
			using (Stream imageStream = sf.ExtractImage())
			{
				if (imageStream != null)
				{
					using (System.Drawing.Image image = Bitmap.FromStream(imageStream))
					{
						image.Save(outFile, System.Drawing.Imaging.ImageFormat.Jpeg);
					}
				}
			}
		}
	}
}
```

## 결론

축하합니다! 이제 Aspose.PDF for .NET을 사용하여 PDF 문서에서 이미지를 추출하는 단계별 가이드가 있습니다. 이 코드를 자신의 프로젝트에 통합하여 이미지를 추출하고 필요에 따라 사용할 수 있습니다.

고급 이미지 추출 및 PDF 문서 조작 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.


### 자주 묻는 질문

#### 질문: Aspose.PDF for .NET은 초보자에게 적합합니까?

A: C# 프로그래밍에 대한 지식이 조금 있으면 도움이 되지만, 이 튜토리얼은 초보자 친화적으로 설계되어 각 단계를 안내합니다.

#### 질문: 한 번에 여러 이미지를 추출할 수 있나요?

A: 물론입니다! 루프를 구현하고 제공된 코드를 조정하면 단일 PDF 문서에서 여러 이미지를 추출할 수 있습니다.

#### 질문: Aspose.PDF for .NET이 이미지 추출을 위한 유일한 솔루션인가요?

답변: 다른 도구도 있지만 .NET용 Aspose.PDF는 효율성과 포괄적인 기능으로 유명합니다.

#### 질문: 추출한 이미지를 상업적 목적으로 사용할 수 있나요?

대답: 네, 추출한 후에는 상업 프로젝트를 포함한 필요에 따라 이미지를 사용하실 수 있습니다.

#### 질문: Aspose.PDF를 이용한 PDF 조작에 대한 추가 리소스는 어디에서 찾을 수 있나요?

답변: Aspose.PDF for .NET을 사용하여 고급 PDF 조작에 대한 풍부한 리소스와 통찰력을 제공하는 공식 문서를 방문하세요.