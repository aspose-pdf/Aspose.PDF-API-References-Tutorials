---
title: 이미지 추출 중
linktitle: 이미지 추출 중
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 문서에서 이미지를 쉽게 추출할 수 있습니다.
type: docs
weight: 70
url: /ko/net/programming-with-security-and-signatures/extracting-image/
---
PDF 문서에서 이미지를 추출하는 것은 많은 경우에 유용할 수 있습니다. .NET용 Aspose.PDF를 사용하면 다음 소스 코드를 사용하여 이미지를 쉽게 추출할 수 있습니다.

## 1단계: 필수 라이브러리 가져오기

시작하기 전에 C# 프로젝트에 필요한 라이브러리를 가져와야 합니다. 필요한 가져오기 지시문은 다음과 같습니다.

```csharp
using Aspose.Pdf;
using System.Drawing;
using System.Drawing.Imaging;
```

## 2단계: 문서 폴더 경로 설정

 이 단계에서는 이미지를 추출하려는 PDF 파일이 포함된 폴더의 경로를 지정해야 합니다. 바꾸다`"YOUR DOCUMENTS DIRECTORY"`다음 코드에 문서 폴더의 실제 경로를 입력하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string input = dataDir + @"ExtractingImage.pdf";
```

## 3단계: PDF 문서에서 이미지 추출

이제 다음 코드를 사용하여 PDF 문서에서 이미지를 추출하겠습니다.

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

이 예에서는 PDF 문서에 있는 양식의 각 필드를 반복합니다. 서명 필드가 발견되면 관련 이미지를 추출하여 JPEG 파일로 저장합니다.

### .NET용 Aspose.PDF를 사용하여 이미지를 추출하기 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
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

축하합니다! 이제 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 이미지를 추출하는 단계별 가이드가 제공됩니다. 이 코드를 자신의 프로젝트에 통합하여 이미지를 추출하고 필요에 따라 사용할 수 있습니다.

고급 이미지 추출 및 PDF 문서 조작 기능에 대한 자세한 내용은 공식 Aspose.PDF 문서를 확인하세요.


### FAQ

#### Q: Aspose.PDF for .NET은 초보자에게 적합합니까?

A: C# 프로그래밍에 어느 정도 익숙해지면 도움이 되지만, 튜토리얼은 초보자에게 친숙하도록 설계되어 각 단계를 안내합니다.

#### Q: 여러 이미지를 한 번에 추출할 수 있나요?

답: 물론이죠! 루프를 구현하고 제공된 코드를 적용하면 단일 PDF 문서에서 여러 이미지를 추출할 수 있습니다.

#### Q: Aspose.PDF for .NET이 이미지 추출을 위한 유일한 솔루션입니까?

A: 다른 도구도 사용할 수 있지만 .NET용 Aspose.PDF는 효율성과 포괄적인 기능으로 유명합니다.

#### Q: 추출된 이미지를 상업적 목적으로 사용할 수 있나요?

A: 예, 일단 추출된 이미지는 상업 프로젝트를 포함하여 필요에 따라 사용할 수 있습니다.

#### Q: Aspose.PDF를 사용한 PDF 조작에 대한 추가 리소스는 어디에서 찾을 수 있나요?

A: .NET용 Aspose.PDF를 사용한 고급 PDF 조작에 대한 풍부한 리소스와 통찰력을 보려면 공식 문서를 방문하세요.