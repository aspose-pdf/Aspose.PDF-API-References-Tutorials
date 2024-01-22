---
title: PDF 파일에서 파일 압축 비활성화
linktitle: PDF 파일에서 파일 압축 비활성화
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 파일 압축을 비활성화하는 방법을 알아보세요. 쉬운 취급을 위한 단계별 가이드입니다.
type: docs
weight: 30
url: /ko/net/programming-with-attachments/disable-files-compression/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF에서 파일 압축을 비활성화하는 다음 C# 소스 코드를 단계별로 안내합니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

### 1단계: 문서 디렉터리 설정

제공된 소스 코드에서 파일 압축을 비활성화하려는 PDF 파일이 있는 디렉터리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉터리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2단계: 기존 PDF 문서 열기

지정된 경로를 사용하여 기존 PDF 문서를 엽니다.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 3단계: 첨부 파일로 추가할 새 파일 설정

첨부 파일로 추가하려는 새 파일을 구성합니다. 이 예에서는 이름이 "test_out.txt"이고 설명이 "예제 텍스트 파일"인 텍스트 파일을 추가합니다.

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### 4단계: 파일 압축 비활성화

FileSpecification 개체의 Encoding 속성을 FileEncoding.None으로 설정하여 파일 압축을 비활성화합니다.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### 5단계: 문서의 첨부 파일 컬렉션에 첨부 파일 추가

문서의 첨부 파일 컬렉션에 첨부 파일을 추가합니다.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### 6단계: 새 출력 파일 저장

마지막으로 지정된 디렉터리에 "DisableFilesCompression_out.pdf"라는 이름으로 결과 새 PDF 파일을 저장합니다.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### .NET용 Aspose.PDF를 사용하여 파일 압축 비활성화를 위한 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// 첨부 파일로 추가할 새 파일 설정
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Encoding proparty를 FileEncoding.None으로 설정하여 지정합니다.
fileSpecification.Encoding = FileEncoding.None;
//문서의 첨부 파일 컬렉션에 첨부 파일 추가
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// 새 출력 저장
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## 결론

이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF에서 파일 압축을 비활성화하는 방법을 설명했습니다. 이제 이 지식을 사용하여 압축 없이 첨부 파일의 무결성을 유지할 수 있습니다.

## PDF 파일의 파일 압축 비활성화에 대한 FAQ

#### Q: PDF 문서에서 파일 압축을 비활성화하려는 이유는 무엇입니까?

답변: 파일 압축을 비활성화하면 PDF 문서 내의 첨부 파일이 압축되지 않은 상태로 유지되어 원본 품질과 내용이 유지됩니다.

#### Q: 파일 압축을 비활성화하면 PDF 첨부 파일에 어떤 이점이 있습니까?

A: 압축을 비활성화하면 압축 프로세스 중에 발생할 수 있는 데이터 또는 품질 손실을 방지하여 첨부된 파일이 있는 그대로 표시됩니다.

#### Q: 이 튜토리얼을 사용하여 특정 첨부 파일에 대한 압축을 선택적으로 비활성화할 수 있습니까?

A: 예, 이 튜토리얼에서는 PDF 문서의 개별 첨부 파일에 대한 파일 압축을 비활성화하여 세밀한 제어를 제공하는 방법을 안내합니다.

#### Q: 어떤 유형의 첨부 파일에 대해 압축을 비활성화할 수 있습니까?

A: 이미지, 문서, 스프레드시트 등과 같은 모든 유형의 첨부 파일에 대해 압축을 비활성화하여 무결성이 유지되도록 할 수 있습니다.

#### Q: 압축을 비활성화하면 PDF 문서의 전체 파일 크기에 영향을 줍니까?

A: 첨부 파일 압축을 비활성화하면 압축되지 않은 파일이 더 많은 공간을 차지하므로 PDF 문서의 전체 파일 크기가 약간 증가할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 파일 압축 비활성화 프로세스를 어떻게 촉진합니까?

A: .NET용 Aspose.PDF는 제공된 소스 코드에 설명된 대로 첨부 파일에 대한 파일 압축을 비활성화할 수 있는 사용하기 쉬운 API를 제공합니다.

#### Q: 필요한 경우 나중에 첨부 파일 압축을 다시 활성화할 수 있습니까?

A: 예. 필요한 경우 첨부 파일의 설정을 수정하여 압축을 다시 활성화할 수 있습니다.

#### Q: 압축을 지원하는 장치나 소프트웨어에서 PDF를 열면 어떻게 됩니까?

A: 압축을 지원하는 장치나 소프트웨어에서 PDF를 열면 첨부 파일이 압축되지 않은 상태로 표시되어 파일 크기와 렌더링 성능에 잠재적으로 영향을 미칠 수 있습니다.

#### Q: 압축 비활성화가 권장되는 특정 시나리오가 있습니까?

A: 고해상도 이미지나 민감한 문서와 같이 원본 품질과 데이터 무결성을 유지하는 것이 중요한 첨부 파일의 경우 압축을 비활성화하는 것이 좋습니다.