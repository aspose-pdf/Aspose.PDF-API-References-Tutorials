---
title: 글꼴 포함 취소 및 PDF 파일 최적화
linktitle: 글꼴 포함 취소 및 PDF 파일 최적화
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 포함되지 않은 글꼴을 얻고 PDF 파일을 최적화하는 방법을 알아보세요. 단계별 가이드.
type: docs
weight: 370
url: /ko/net/programming-with-document/unembedfonts/
---
.NET용 Aspose.PDF는 PDF 문서 작업에 필요한 다양한 기능을 제공하는 강력한 라이브러리입니다. 그 기능 중 하나는 PDF 문서에서 포함되지 않은 글꼴을 가져오는 것입니다. 이는 PDF 문서에서 글꼴을 추출하여 다른 응용 프로그램에서 사용해야 하는 경우 유용할 수 있습니다.

.NET용 Aspose.PDF의 포함되지 않은 글꼴 가져오기 기능에 대한 다음 C# 소스 코드를 설명하는 단계별 가이드를 제공합니다.

## 1단계: 문서 디렉터리 경로 설정

시작하기 전에 PDF 문서가 있는 디렉토리의 경로를 설정해야 합니다. 이 경로를 "dataDir"이라는 변수에 저장합니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"YOUR DOCUMENT DIRECTORY"를 PDF 문서가 있는 디렉토리의 실제 경로로 바꾸십시오.

## 2단계: PDF 문서 열기

 첫 번째 단계는 원하는 PDF 문서를 로드하는 것입니다.`Document` .NET용 Aspose.PDF 클래스입니다. 다음 코드 조각은 PDF 문서를 로드하는 방법을 보여줍니다.

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 3단계: UnembedFonts 옵션 설정

 PDF 문서에서 포함 취소된 글꼴을 얻으려면`UnembedFonts` 옵션`true` . 이 옵션은 다음에서 사용할 수 있습니다.`OptimizationOptions` 수업. 다음 코드 조각은 설정 방법을 보여줍니다.`UnembedFonts` 옵션:

```csharp
// UnembedFonts 옵션 설정
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## 4단계: PDF 문서 최적화

 설정한 후`UnembedFonts` 옵션을 사용하여 PDF 문서를 최적화할 수 있습니다.`OptimizeResources` 의 방법`Document` 수업. 다음 코드 조각은 PDF 문서를 최적화하는 방법을 보여줍니다.

```csharp
// OptimizationOptions를 사용하여 PDF 문서 최적화
pdfDocument.OptimizeResources(optimizeOptions);
```

## 5단계: 업데이트된 문서 저장

 PDF 문서가 최적화되면 다음을 사용하여 업데이트된 문서를 저장할 수 있습니다.`Save` 의 방법`Document`수업. 다음 코드 조각은 업데이트된 문서를 저장하는 방법을 보여줍니다.

```csharp
// 업데이트된 문서 저장
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 6단계: 원본 및 축소된 파일 크기 가져오기

 마지막으로 다음을 사용하여 PDF 문서의 원본 및 축소된 파일 크기를 얻을 수 있습니다.`FileInfo` System.IO 클래스입니다. 다음 코드 조각은 원본 파일 크기와 축소된 파일 크기를 가져오는 방법을 보여줍니다.

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### .NET용 Aspose.PDF를 사용하여 포함되지 않은 글꼴 가져오기에 대한 예제 소스 코드

다음은 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 포함되지 않은 글꼴을 가져오는 전체 예제 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// UnembedFonts 옵션 설정
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
// OptimizationOptions를 사용하여 PDF 문서 최적화
pdfDocument.OptimizeResources(optimizeOptions);
// 업데이트된 문서 저장
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 문서에서 포함되지 않은 글꼴을 가져오는 방법을 시연했습니다. 단계별 가이드를 따르면 C# 애플리케이션에서 이 기능을 쉽게 구현할 수 있습니다. 추출된 글꼴을 별도로 사용하거나 다양한 플랫폼에서 일관된 글꼴 사용을 보장해야 하는 경우 글꼴 포함을 취소하는 것이 유리할 수 있습니다.

## FAQ

#### Q: PDF 문서에서 글꼴 포함을 취소하는 목적은 무엇입니까?

답변: PDF 문서에서 글꼴 포함을 취소하면 포함된 글꼴을 추출하여 다른 응용 프로그램에서 사용할 수 있습니다. 이는 일관된 글꼴 렌더링을 보장하고 문서의 시각적 모양을 유지하는 데 유용할 수 있습니다.

#### Q: C# 코드에서 문서 디렉터리 경로를 어떻게 지정합니까?

 A: 문서 디렉터리의 경로를 지정하려면`"YOUR DOCUMENT DIRECTORY"` PDF 문서가 있는 디렉토리의 실제 경로가 포함된 코드에

####  Q: 무엇을 하는가?`UnembedFonts` option do, and where is it set?

 답:`UnembedFonts` 옵션에서 사용 가능`OptimizationOptions` 클래스를 사용하여 PDF 문서에서 글꼴 포함 취소를 활성화하거나 비활성화합니다. 이 옵션을 설정하려면`true`, 다음 코드를 사용하십시오.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### Q: 최적화 과정에서 변경한 내용을 되돌릴 수 있나요?

A: .NET용 Aspose.PDF는 최적화 중에 원본 PDF 문서를 영구적으로 변경하지 않습니다. 최적화 프로세스는 원본을 그대로 유지한 채 문서 사본에 대해 수행됩니다.

#### Q: 최적화 후 원본 파일 크기와 축소된 파일 크기는 어떻게 확인할 수 있나요?

A: 다음을 사용할 수 있습니다.`FileInfo` 클래스`System.IO` 원본 파일 크기와 축소된 파일 크기를 얻으려면 이를 달성하기 위한 예제 코드 조각은 다음과 같습니다.

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```