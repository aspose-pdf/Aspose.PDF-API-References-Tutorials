---
title: 방향 변경
linktitle: 방향 변경
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET으로 PDF의 페이지 방향을 변경하는 단계별 가이드. 쉽게 따라할 수 있고 프로젝트에 구현할 수 있습니다.
type: docs
weight: 10
url: /ko/net/programming-with-pdf-pages/change-orientation/
---
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지 방향을 변경하는 단계별 프로세스를 안내합니다. 번들로 제공되는 C# 소스 코드를 설명하고 이 기능을 이해하고 자신의 프로젝트에 구현하는 데 도움이 되는 포괄적인 가이드를 제공합니다. 이 튜토리얼을 마치면 Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지 방향을 변경하는 방법을 알게 됩니다.

## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- 개발 환경에 설치된 .NET용 Aspose.PDF

## 1단계: 문서 디렉토리 정의
먼저, 문서 디렉토리 경로를 설정해야 합니다. 이는 입력 PDF 파일이 있는 위치이며 수정된 출력 PDF 파일을 저장할 위치입니다. "YOUR DOCUMENTS DIRECTORY"를 적절한 경로로 바꾸세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: PDF 문서 로드
 그런 다음 다음을 사용하여 입력 파일에서 PDF 문서를 로드할 수 있습니다.`Document` Aspose.PDF 클래스. PDF 파일에 대한 올바른 경로를 지정해야 합니다.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## 3단계: 페이지 방향 변경
이제 문서의 각 페이지를 살펴보고 방향을 변경해 보겠습니다. 각 페이지에서 미디어 상자의 크기를 수정합니다(`MediaBox`) 너비와 높이를 바꿔서, 미디어 상자의 좌표를 조정하여 페이지의 위치를 유지합니다. 마지막으로, 페이지 회전을 90도로 설정합니다.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## 4단계: 수정된 PDF 문서 저장
 마지막으로 수정된 PDF 문서를 출력 파일에 저장할 수 있습니다.`Save()` 의 방법`Document`클래스. 올바른 경로와 파일 이름을 지정해야 합니다.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### .NET용 Aspose.PDF를 사용한 Change Orientation의 샘플 소스 코드 

```csharp

// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// 변경되는 페이지 크기를 보상하기 위해 페이지를 위로 이동해야 합니다.
	// (페이지의 하단 가장자리는 0,0이고 정보는 일반적으로 다음 위치에서 배치됩니다.
	// 페이지 상단. 그래서 우리는 차이점에 대한 연인 가장자리를 위로 이동합니다.
	// 오래된 높이와 새로운 높이.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// 때로는 CropBox를 설정해야 할 수도 있습니다(원본 파일에 설정된 경우)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// 페이지 회전 각도 설정
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// 출력 파일 저장
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## 결론
이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서의 페이지 방향을 변경하는 방법을 알아보았습니다. 위에 설명된 단계를 따르면 자신의 프로젝트에서 이 기능을 쉽게 구현할 수 있습니다. Aspose.PDF 설명서를 더 탐색하여 PDF 파일 작업에 유용한 다른 기능을 발견하세요.

### 자주 묻는 질문

#### 질문: PDF 문서에서 페이지 방향을 바꾸는 목적은 무엇인가요?

A: PDF 문서에서 페이지 방향을 변경하면 페이지의 내용을 90도 회전할 수 있습니다. 이는 원본 내용을 다른 방향으로 표시하거나 인쇄해야 하는 경우(예: 세로 모드에서 가로 모드로 전환하거나 그 반대)에 유용할 수 있습니다.

#### 질문: PDF 문서에서 특정 페이지의 방향을 변경할 수 있나요?

 A: 네, PDF 문서에서 특정 페이지의 방향을 변경할 수 있습니다. 제공된 C# 소스 코드에서`foreach` 루프는 문서의 각 페이지를 살펴보고 방향을 변경하는 데 사용됩니다. 특정 페이지의 방향만 변경하려는 경우 루프를 수정하여 페이지 번호나 기타 기준에 따라 해당 페이지를 타겟팅할 수 있습니다.

#### 질문: 페이지 방향을 변경하면 페이지의 콘텐츠 레이아웃에 영향을 미칩니까?

A: 네, 페이지 방향을 변경하면 페이지의 콘텐츠 레이아웃에 영향을 미칩니다. 콘텐츠는 90도 회전되고 페이지의 너비와 높이가 바뀝니다. 결과적으로 페이지의 콘텐츠 배치와 정렬이 변경될 수 있습니다.

#### 질문: 90도가 아닌 다른 각도로 페이지를 회전할 수 있나요?

 A: 제공된 C# 소스 코드에서 페이지 회전은 다음을 사용하여 90도로 설정됩니다.`page.Rotate = Rotate.on90;` . 그러나 필요한 경우 회전 각도를 다른 값으로 변경할 수 있습니다. 예를 들어 다음을 사용할 수 있습니다.`Rotate.on180` 페이지를 180도 회전하거나`Rotate.on270` 270도 회전시키세요.

#### 질문: 방향을 변경한 후 페이지 내용이 넘쳐나는 경우 어떻게 처리해야 하나요?

A: 페이지 방향을 변경할 때 페이지의 크기가 변경될 수 있으며, 이로 인해 콘텐츠 오버플로가 발생할 수 있습니다. 이를 처리하려면 페이지의 콘텐츠 레이아웃과 서식을 조정해야 할 수 있습니다. Aspose.PDF for .NET에서 제공하는 기능(예: 요소 크기 조정, 여백 조정 또는 콘텐츠 재정비)을 사용하여 방향 변경 후 페이지 콘텐츠가 제대로 맞는지 확인할 수 있습니다.