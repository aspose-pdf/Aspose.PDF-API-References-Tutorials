---
title: PDF를 SVG로
linktitle: PDF를 SVG로
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF를 SVG로 변환하는 단계별 가이드입니다.
type: docs
weight: 180
url: /ko/net/document-conversion/pdf-to-svg/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF를 SVG 형식으로 변환하는 과정을 안내합니다. SVG(Scalable Vector Graphics)는 그래픽의 품질과 크기를 유지하는 데 도움이 되는 벡터 이미지 형식입니다. 아래 단계에 따라 PDF 파일을 SVG 형식으로 변환할 수 있습니다.

## 전제조건
시작하기 전에 다음 전제 조건을 충족하는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- 시스템에 설치된 .NET용 Aspose.PDF 라이브러리.
- Visual Studio와 같은 개발 환경.

## 1단계: PDF 문서 로드
이 단계에서는 .NET용 Aspose.PDF를 사용하여 소스 PDF 파일을 로드합니다. 아래 코드를 따르십시오.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// PDF 문서 로드
Document doc = new Document(dataDir + "input.pdf");
```

 꼭 교체하세요`"YOUR DOCUMENTS DIRECTORY"` PDF 파일이 있는 실제 디렉토리를 사용하세요.

## 2단계: SVG 저장 옵션 인스턴스화
PDF 파일을 로드한 후 SVG 저장 옵션을 인스턴스화합니다. 다음 코드를 사용하세요.

```csharp
// SvgSaveOptions 객체 인스턴스화
SvgSaveOptions saveOptions = new SvgSaveOptions();
// Zip 아카이브의 SVG 이미지를 압축하지 마세요.
saveOptions.CompressOutputToZipArchive = false;
```

## 3단계: 결과 SVG 파일 저장
이제 변환된 PDF 파일을 SVG 형식으로 저장하겠습니다. 다음 코드를 사용하세요.

```csharp
// 출력을 SVG 파일로 저장
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

 위의 코드는 변환된 PDF를 파일 이름과 함께 SVG 형식으로 저장합니다.`"PDFToSVG_out.svg"`.

### .NET용 Aspose.PDF를 사용하여 PDF를 SVG로 변환하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// PDF 문서 로드
Document doc = new Document(dataDir + "input.pdf");
// SvgSaveOptions 개체 인스턴스화
SvgSaveOptions saveOptions = new SvgSaveOptions();
// SVG 이미지를 Zip 아카이브로 압축하지 마세요.
saveOptions.CompressOutputToZipArchive = false;
// 출력을 SVG 파일로 저장
doc.Save(dataDir + "PDFToSVG_out.svg", saveOptions);
```

## 결론
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일을 SVG 형식으로 변환하는 단계별 프로세스를 다루었습니다. 위에 설명된 지침을 따르면 이제 PDF 파일을 SVG 형식으로 변환할 수 있습니다. 이 기능은 벡터 이미지로 변환할 때 그래픽 품질과 크기를 유지하려는 경우에 유용합니다.

### FAQ

#### Q: PDF를 SVG로 변환하는 동안 결과 SVG 파일의 해상도나 크기를 제어할 수 있습니까?

 A: 예, .NET용 Aspose.PDF를 사용하여 PDF를 SVG로 변환하는 동안 결과 SVG 파일의 해상도나 크기를 제어할 수 있습니다. 그만큼`SvgSaveOptions` 클래스는 다음과 같은 속성을 제공합니다.`PageSavingCallback` 그리고`SaveFormat` 해상도, 페이지 크기 또는 SVG 출력과 관련된 기타 매개변수를 설정할 수 있습니다. 요구 사항에 따라 이러한 옵션을 사용자 정의하여 SVG 파일의 품질과 크기를 제어할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 암호화되거나 비밀번호로 보호된 PDF를 SVG로 변환하는 것을 지원합니까?

A: 예, .NET용 Aspose.PDF는 암호화되거나 비밀번호로 보호된 PDF를 SVG 형식으로 변환하는 것을 지원합니다. 비밀번호로 보호된 PDF를 로드할 때 다음을 사용하여 비밀번호를 제공할 수 있습니다.`Document` 클래스 생성자 또는`Password` PDF를 로드하기 전의 속성입니다. .NET용 Aspose.PDF는 PDF에서 SVG로의 변환 프로세스 중에 암호 해독을 처리합니다.

#### Q: 전체 문서 대신 PDF의 특정 페이지만 SVG로 변환할 수 있나요?

A: 예, .NET용 Aspose.PDF를 사용하면 전체 문서 대신 PDF의 특정 페이지만 SVG로 변환할 수 있습니다. 출력을 SVG 파일로 저장하기 전에 페이지 번호나 범위를 지정하여 변환하려는 페이지를 선택할 수 있습니다. 이렇게 하면 PDF에서 원하는 페이지만 추출하여 SVG 형식으로 변환할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 모든 SVG 버전과 호환됩니까?

A: .NET용 Aspose.PDF는 SVG 1.1(Scalable Vector Graphics) 사양과 호환되도록 설계되었습니다. SVG 1.1 표준에 따라 SVG 파일 생성을 지원합니다. 그러나 SVG 2.0이 SVG 사양의 최신 버전으로 도입되었습니다. .NET용 Aspose.PDF는 대부분의 경우 SVG 2.0에서 여전히 잘 작동할 수 있지만 사용하려는 특정 SVG 기능과의 호환성 및 잠재적 제한 사항을 확인하는 것이 좋습니다.