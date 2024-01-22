---
title: PDF 파일에 썸네일 이미지 만들기
linktitle: PDF 파일에 썸네일 이미지 만들기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일로 썸네일 이미지를 쉽게 생성할 수 있습니다.
type: docs
weight: 100
url: /ko/net/programming-with-images/create-thumbnail-images/
---
이 가이드는 .NET용 Aspose.PDF를 사용하여 PDF 파일에서 썸네일 이미지를 만드는 방법을 단계별로 안내합니다. 이미 환경을 설정했는지 확인하고 아래 단계를 따르세요.

## 1단계: 문서 디렉터리 정의

 시작하기 전에 문서에 대한 올바른 디렉토리를 설정했는지 확인하십시오. 바꾸다`"YOUR DOCUMENT DIRECTORY"` PDF 파일이 포함된 디렉터리 경로가 포함된 코드에

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 디렉터리에 있는 모든 PDF 파일의 이름 가져오기

 이 단계에서는 C#을 사용하여 지정된 디렉터리에 있는 모든 PDF 파일의 이름을 검색합니다.`Directory` 수업. 파일은 문자열 배열로 저장됩니다.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## 3단계: 모든 PDF 파일과 해당 페이지 찾아보기

 이 단계에서는 모든 PDF 파일과 해당 페이지를 살펴보고 이미지 축소판을 만듭니다. 우리는`for` 모든 파일을 반복하는 루프입니다.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //PDF 문서 열기
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // 문서의 모든 페이지를 살펴보세요.
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // 썸네일 이미지를 저장하기 위한 스트림 생성
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // 해결 개체 만들기
             Resolution resolution = new Resolution(300);
            
             // 지정된 속성을 사용하여 JPEG 장치 생성
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // 특정 페이지를 변환하고 이미지를 스트림에 저장
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // 스트림 닫기
             imageStream.Close();
         }
     }
}
```

### .NET용 Aspose.PDF를 사용하여 썸네일 이미지 생성을 위한 샘플 소스 코드 
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
//특정 디렉토리에 있는 모든 PDF 파일의 이름을 검색합니다.
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
			//해결 객체 생성
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, 해상도, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//특정 페이지를 변환하고 이미지를 스트리밍에 저장
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//스트림 닫기
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## 결론

축하합니다! .NET용 Aspose.PDF를 사용하여 PDF 파일에서 이미지 축소판을 성공적으로 만들었습니다. 이미지 썸네일은 지정된 디렉토리에 저장됩니다. 이제 이러한 축소판을 사용하여 PDF 파일의 시각적 미리보기를 표시할 수 있습니다.

### PDF 파일의 썸네일 이미지 생성에 대한 FAQ

#### Q: .NET용 Aspose.PDF를 사용하여 PDF 파일에서 썸네일 이미지를 만드는 목적은 무엇입니까?

A: PDF 파일에서 축소판 이미지를 생성하면 PDF의 각 페이지에 대한 작은 시각적 미리 보기를 생성할 수 있으므로 콘텐츠를 빠르게 미리 보고 탐색하는 데 유용할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 어떻게 PDF 파일에서 썸네일 이미지 생성을 용이하게 합니까?

A: .NET용 Aspose.PDF는 PDF 문서를 열고, 해당 페이지를 반복하고, 썸네일 이미지를 만들고, 다음을 사용하여 지정된 디렉터리에 저장하는 단계별 프로세스를 제공합니다.`JpegDevice` 수업.

#### Q: 썸네일 이미지 생성을 시작하기 전에 문서 디렉터리를 정의하는 것이 왜 중요한가요?

A: 문서 디렉토리를 지정하면 PDF 파일이 올바르게 위치되고 결과 썸네일 이미지가 원하는 출력 경로에 저장됩니다.

####  Q: 어떻게 되나요?`Document` class in Aspose.PDF for .NET help in the creation of thumbnail images?

 답:`Document` 클래스를 사용하면 PDF 문서를 열고 조작할 수 있습니다. 이 경우 썸네일 이미지가 생성될 PDF 파일을 로드하는 데 사용됩니다.

####  Q: 어떤 역할을 하나요?`JpegDevice` class play in the creation of thumbnail images?

 답:`JpegDevice` 클래스는 PDF 페이지를 축소판 이미지로 사용되는 JPEG 이미지로 변환하는 일을 담당합니다. 너비, 높이, 해상도, 품질과 같은 속성을 지정할 수 있습니다.

#### Q: PDF 문서의 각 페이지는 어떻게 개별 축소판 이미지로 변환됩니까?

 A: 중첩된`for`루프는 각 PDF 파일과 해당 페이지를 반복하는 데 사용됩니다. 각 페이지에 대해 지정된 속성을 사용하여 JPEG 장치가 생성되고`Process` 메소드는 페이지를 썸네일 이미지로 변환하고 스트림에 저장하는 데 사용됩니다.

#### Q: 생성 과정에서 결과 썸네일 이미지의 해상도나 품질을 조정할 수 있습니까?

 A: 예.`JpegDevice` 각 페이지를 변환하기 전에 개체를 선택하세요.

#### Q: 생성 프로세스 후에 생성된 썸네일 이미지를 내 프로젝트나 애플리케이션에서 어떻게 활용할 수 있나요?

A: 결과 썸네일 이미지는 PDF 파일의 시각적 미리보기를 제공하는 데 사용될 수 있으므로 사용자가 콘텐츠를 빠르게 식별하고 탐색하는 데 도움이 됩니다.

#### : 이 생성 프로세스를 사용하여 PDF 파일에서 생성할 수 있는 축소판 이미지 수에 제한이 있습니까?

A: 생성된 축소판 이미지 수는 각 PDF 문서의 페이지 수에 따라 다릅니다. 각 페이지는 별도의 썸네일 이미지로 변환됩니다.