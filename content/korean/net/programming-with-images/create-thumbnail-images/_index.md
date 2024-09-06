---
title: PDF 파일에 썸네일 이미지 생성
linktitle: PDF 파일에 썸네일 이미지 생성
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 이용하여 PDF 파일에 썸네일 이미지를 쉽게 만들 수 있습니다.
type: docs
weight: 100
url: /ko/net/programming-with-images/create-thumbnail-images/
---
이 가이드에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에 썸네일 이미지를 만드는 방법을 단계별로 안내합니다. 이미 환경을 설정했는지 확인하고 아래 단계를 따르세요.

## 1단계: 문서 디렉토리 정의

시작하기 전에 문서에 대한 올바른 디렉토리를 설정했는지 확인하세요. 바꾸기`"YOUR DOCUMENT DIRECTORY"` PDF 파일이 있는 디렉토리 경로를 코드에 추가합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 디렉토리에 있는 모든 PDF 파일의 이름 가져오기

 이 단계에서는 C#를 사용하여 지정된 디렉토리에 있는 모든 PDF 파일의 이름을 검색합니다.`Directory`클래스. 파일은 문자열 배열에 저장됩니다.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## 3단계: 모든 PDF 파일과 해당 페이지 탐색

 이 단계에서는 모든 PDF 파일과 해당 페이지를 살펴보고 이미지 축소판을 만듭니다.`for` 모든 파일을 반복하기 위한 루프입니다.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // PDF 문서를 엽니다
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // 문서의 모든 페이지를 살펴보세요
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // 썸네일 이미지를 저장하기 위한 스트림을 생성합니다.
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //Resolution 객체를 생성합니다
             Resolution resolution = new Resolution(300);
            
             // 지정된 속성을 사용하여 JPEG 장치를 만듭니다.
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // 특정 페이지를 변환하고 이미지를 스트림에 저장합니다.
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // 스트림을 닫습니다
             imageStream.Close();
         }
     }
}
```

### .NET용 Aspose.PDF를 사용하여 썸네일 이미지 생성을 위한 샘플 소스 코드 
```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 특정 디렉토리에 있는 모든 PDF 파일의 이름을 검색합니다.
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// 배열의 모든 파일 항목을 반복합니다.
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//문서 열기
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Resolution 객체 생성
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, 해상도, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//특정 페이지를 변환하고 이미지를 스트리밍으로 저장합니다.
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//스트림 닫기
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## 결론

축하합니다! Aspose.PDF for .NET을 사용하여 PDF 파일에서 이미지 썸네일을 성공적으로 만들었습니다. 이미지 썸네일은 지정된 디렉토리에 저장됩니다. 이제 이러한 썸네일을 사용하여 PDF 파일의 시각적 미리보기를 표시할 수 있습니다.

### PDF 파일에 썸네일 이미지를 만드는 방법에 대한 FAQ

#### 질문: Aspose.PDF for .NET을 사용하여 PDF 파일에서 썸네일 이미지를 만드는 목적은 무엇입니까?

답변: PDF 파일에서 썸네일 이미지를 만들면 PDF의 각 페이지에 대한 작은 시각적 미리보기를 생성할 수 있습니다. 이는 콘텐츠를 빠르게 미리 보고 탐색하는 데 유용할 수 있습니다.

#### 질문: Aspose.PDF for .NET은 어떻게 PDF 파일에서 축소판 이미지를 만드는 데 도움을 주나요?

 A: Aspose.PDF for .NET은 PDF 문서를 열고, 페이지를 반복하고, 축소판 이미지를 만들고, 다음을 사용하여 지정된 디렉토리에 저장하는 단계별 프로세스를 제공합니다.`JpegDevice` 수업.

#### 질문: 썸네일 이미지를 만들기 전에 문서 디렉토리를 정의하는 것이 중요한 이유는 무엇입니까?

답변: 문서 디렉토리를 지정하면 PDF 파일이 올바른 위치에 저장되고, 생성된 축소판 이미지가 원하는 출력 경로에 저장됩니다.

####  Q: 어떻게`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 A: 그`Document` 클래스를 사용하면 PDF 문서를 열고 조작할 수 있습니다. 이 경우, 썸네일 이미지가 생성될 PDF 파일을 로드하는 데 사용됩니다.

####  Q: 어떤 역할을 하나요?`JpegDevice` class play in the creation of thumbnail images?

 A: 그`JpegDevice` 클래스는 PDF 페이지를 JPEG 이미지로 변환하는 역할을 하며, 이는 썸네일 이미지로 사용됩니다. 너비, 높이, 해상도, 품질과 같은 속성을 지정할 수 있습니다.

#### 질문: PDF 문서의 각 페이지가 개별 축소판 이미지로 어떻게 변환되나요?

 A: 중첩된`for` 루프는 각 PDF 파일과 해당 페이지를 반복하는 데 사용됩니다. 각 페이지에 대해 지정된 속성이 있는 JPEG 장치가 생성되고`Process` 이 방법은 페이지를 썸네일 이미지로 변환하고 스트림에 저장하는 데 사용됩니다.

#### 질문: 생성 과정에서 최종 썸네일 이미지의 해상도나 품질을 조정할 수 있나요?

A: 예, 해상도, 너비, 높이, 품질과 같은 속성을 구성하여 수정할 수 있습니다.`JpegDevice` 각 페이지를 변환하기 전에 개체를 선택합니다.

#### 질문: 생성된 썸네일 이미지를 생성 과정 후에 프로젝트나 애플리케이션에서 어떻게 활용할 수 있나요?

답변: 생성된 썸네일 이미지는 PDF 파일의 시각적 미리보기를 제공하는 데 사용할 수 있으며, 이를 통해 사용자는 콘텐츠를 빠르게 식별하고 탐색할 수 있습니다.

#### : 이 생성 프로세스를 사용하여 PDF 파일에서 생성할 수 있는 썸네일 이미지 수에 제한이 있습니까?

A: 생성되는 썸네일 이미지의 수는 각 PDF 문서의 페이지 수에 따라 달라집니다. 각 페이지는 별도의 썸네일 이미지로 변환됩니다.