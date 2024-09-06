---
title: 글꼴 임베드 해제 및 PDF 파일 최적화
linktitle: 글꼴 임베드 해제 및 PDF 파일 최적화
second_title: .NET API 참조를 위한 Aspose.PDF
description: Aspose.PDF for .NET을 사용하여 Unembed Fonts를 얻고 PDF 파일을 최적화하는 방법을 알아보세요. 단계별 가이드.
type: docs
weight: 370
url: /ko/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET은 PDF 문서에서 작업할 수 있는 광범위한 기능을 제공하는 강력한 라이브러리입니다. 그 기능 중 하나는 PDF 문서에서 임베드되지 않은 글꼴을 가져오는 것입니다. PDF 문서에서 글꼴을 추출하여 다른 애플리케이션에서 사용해야 하는 경우 유용할 수 있습니다.

.NET용 Aspose.PDF의 글꼴 임베드 해제 기능에 대한 다음 C# 소스 코드를 설명하는 단계별 가이드를 제공합니다.

## 1단계: 문서 디렉토리 경로 설정

시작하기 전에 PDF 문서가 있는 디렉토리 경로를 설정해야 합니다. 이 경로를 "dataDir"이라는 변수에 저장합니다.

```csharp
// 문서 디렉토리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

"YOUR DOCUMENT DIRECTORY"를 PDF 문서가 있는 디렉토리의 실제 경로로 바꾸세요.

## 2단계: PDF 문서 열기

 첫 번째 단계는 이를 수행하려는 PDF 문서를 로드하는 것입니다.`Document` .NET용 Aspose.PDF 클래스. 다음 코드 조각은 PDF 문서를 로드하는 방법을 보여줍니다.

```csharp
// 문서 열기
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 3단계: UnembedFonts 옵션 설정

 PDF 문서에서 내장되지 않은 글꼴을 가져오려면 다음을 설정해야 합니다.`UnembedFonts` 옵션`true` . 이 옵션은 다음에서 사용할 수 있습니다.`OptimizationOptions` 클래스. 다음 코드 조각은 다음을 설정하는 방법을 보여줍니다.`UnembedFonts` 옵션:

```csharp
// UnembedFonts 옵션 설정
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## 4단계: PDF 문서 최적화

 설정 후`UnembedFonts` 옵션을 사용하면 PDF 문서를 최적화할 수 있습니다.`OptimizeResources` 의 방법`Document` 클래스. 다음 코드 조각은 PDF 문서를 최적화하는 방법을 보여줍니다.

```csharp
// OptimizationOptions를 사용하여 PDF 문서 최적화
pdfDocument.OptimizeResources(optimizeOptions);
```

## 5단계: 업데이트된 문서 저장

 PDF 문서가 최적화되면 다음을 사용하여 업데이트된 문서를 저장할 수 있습니다.`Save` 의 방법`Document`클래스. 다음 코드 조각은 업데이트된 문서를 저장하는 방법을 보여줍니다.

```csharp
// 업데이트된 문서 저장
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 6단계: 원본 및 축소된 파일 크기 가져오기

 마지막으로, 다음을 사용하여 PDF 문서의 원본 파일 크기와 축소된 파일 크기를 얻을 수 있습니다.`FileInfo` System.IO 클래스입니다. 다음 코드 조각은 원본 및 축소된 파일 크기를 가져오는 방법을 보여줍니다.

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### .NET용 Aspose.PDF를 사용하여 임베드되지 않은 글꼴 가져오기 예제 소스 코드

다음은 Aspose.PDF for .NET을 사용하여 PDF 문서에서 내장되지 않은 글꼴을 가져오는 전체 예제 소스 코드입니다.

```csharp
// 문서 디렉토리의 경로입니다.
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

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 문서에서 임베드되지 않은 글꼴을 가져오는 방법을 보여주었습니다. 단계별 가이드를 따르면 C# 애플리케이션에서 이 기능을 쉽게 구현할 수 있습니다. 추출된 글꼴을 별도로 작업하거나 다양한 플랫폼에서 일관된 글꼴 사용을 보장해야 할 때 글꼴 임베드 해제가 유용할 수 있습니다.

## 자주 묻는 질문

#### 질문: PDF 문서에서 글꼴을 포함 해제하는 목적은 무엇입니까?

A: PDF 문서에서 글꼴을 언임베드하면 임베드된 글꼴을 추출하여 다른 애플리케이션에서 사용할 수 있습니다. 이는 일관된 글꼴 렌더링을 보장하고 문서의 시각적 모양을 보존하는 데 유용할 수 있습니다.

#### 질문: C# 코드에서 문서 디렉토리 경로를 어떻게 지정하나요?

 A: 문서 디렉토리 경로를 지정하려면 다음을 바꾸세요.`"YOUR DOCUMENT DIRECTORY"` PDF 문서가 있는 디렉토리의 실제 경로를 코드에 넣습니다.

####  Q: 무슨 일이야?`UnembedFonts` option do, and where is it set?

 A: 그`UnembedFonts` 옵션은 다음에서 사용 가능합니다.`OptimizationOptions` 클래스는 PDF 문서에서 글꼴을 임베드 해제하는 것을 활성화하거나 비활성화합니다. 이 옵션을 설정하려면`true`다음 코드를 사용하세요:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### 질문: 최적화 과정에서 변경한 내용을 되돌릴 수 있나요?

A: Aspose.PDF for .NET은 최적화 중에 원본 PDF 문서에 영구적인 변경을 하지 않습니다. 최적화 프로세스는 문서 사본에서 수행되며 원본은 그대로 유지됩니다.

#### 질문: 최적화 후 원본 파일 크기와 줄어든 파일 크기를 어떻게 확인할 수 있나요?

 A: 다음을 사용할 수 있습니다.`FileInfo` 의 클래스`System.IO` 원본 및 축소된 파일 크기를 얻으려면. 다음은 이를 달성하기 위한 예제 코드 조각입니다.

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```