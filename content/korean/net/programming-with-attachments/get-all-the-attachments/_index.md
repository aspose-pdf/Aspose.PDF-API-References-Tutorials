---
title: PDF 파일의 모든 첨부 파일 가져오기
linktitle: PDF 파일의 모든 첨부 파일 가져오기
second_title: .NET API 참조용 Aspose.PDF
description: .NET용 Aspose.PDF를 사용하여 PDF 파일의 모든 첨부 파일을 얻는 방법을 알아보세요. 쉬운 취급을 위한 단계별 가이드입니다.
type: docs
weight: 40
url: /ko/net/programming-with-attachments/get-all-the-attachments/
---
이 튜토리얼에서는 .NET용 Aspose.PDF를 사용하여 PDF 파일의 모든 첨부 파일을 가져오기 위해 다음 C# 소스 코드를 단계별로 안내합니다.

시작하기 전에 Aspose.PDF 라이브러리를 설치하고 개발 환경을 설정했는지 확인하세요. 또한 C# 프로그래밍에 대한 기본 지식이 있어야 합니다.

### 1단계: 문서 디렉터리 설정

제공된 소스 코드에서 첨부 파일을 가져오려는 PDF 파일이 있는 디렉터리를 지정해야 합니다. "dataDir" 변수를 원하는 디렉터리로 변경합니다.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### 2단계: 기존 PDF 문서 열기

지정된 경로를 사용하여 기존 PDF 문서를 엽니다.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### 3단계: 첨부 파일 컬렉션 얻기

문서에서 첨부 파일 모음을 가져옵니다.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### 4단계: 첨부 파일 검색

컬렉션을 살펴보며 모든 첨부 파일을 가져오고 해당 정보를 표시합니다. 또한 첨부 파일을 개별 파일로 저장합니다.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// 객체 매개변수에 추가 정보가 포함되어 있는지 확인하세요.
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// 첨부파일을 검색하여 파일로 저장
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### .NET용 Aspose.PDF를 사용하여 모든 첨부 파일 가져오기의 샘플 소스 코드 

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// 문서 열기
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// 내장된 파일 컬렉션 가져오기
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// 포함된 파일 수를 가져옵니다.
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// 컬렉션을 반복하여 모든 첨부 파일을 가져옵니다.
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
	Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
	//매개변수 객체에 매개변수가 포함되어 있는지 확인하세요.
	if (fileSpecification.Params != null)
	{
		Console.WriteLine("CheckSum: {0}",
		fileSpecification.Params.CheckSum);
		Console.WriteLine("Creation Date: {0}",
		fileSpecification.Params.CreationDate);
		Console.WriteLine("Modification Date: {0}",
		fileSpecification.Params.ModDate);
		Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
	}
	// 첨부 파일을 가져와 파일이나 스트림에 쓰기
	byte[] fileContent = new byte[fileSpecification.Contents.Length];
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## 결론

이 튜토리얼에서는 Aspose.PDF for .NET을 사용하여 PDF 파일에서 모든 첨부 파일을 가져오는 방법을 설명했습니다. 이제 이 지식을 사용하여 PDF 파일에서 첨부 파일을 추출하고 조작할 수 있습니다.

## PDF 파일의 모든 첨부 파일을 얻기 위한 FAQ

#### Q: PDF 문서에서 모든 첨부 파일을 검색해야 하는 이유는 무엇입니까?

A: 첨부 파일을 검색하면 PDF에 포함된 추가 파일에 액세스하고 조작할 수 있으므로 보관, 공유 또는 추가 처리에 유용할 수 있습니다.

#### Q: PDF 문서에 어떤 유형의 파일을 첨부할 수 있나요?

A: PDF 문서에는 이미지, 문서, 스프레드시트, 오디오 파일 등을 포함한 다양한 첨부 파일이 포함될 수 있습니다.

#### Q: 이 튜토리얼은 .NET용 Aspose.PDF를 사용하여 PDF에서 첨부 파일을 검색하는 데 어떻게 도움이 됩니까?

A: 이 튜토리얼에서는 PDF 문서 내의 모든 첨부 파일에 액세스하고 검색하기 위한 단계별 지침과 C# 소스 코드를 제공합니다.

#### Q: 이 튜토리얼을 사용하여 모든 첨부 파일 대신 특정 첨부 파일을 검색할 수 있습니까?

A: 예. 제공된 코드를 수정하여 요구 사항에 따라 첨부 파일을 선택적으로 검색할 수 있습니다.

#### Q: 이 튜토리얼을 사용하여 각 첨부 파일에 대해 어떤 정보를 얻을 수 있습니까?

A: 이 튜토리얼에서는 첨부 파일 이름, 설명, MIME 유형, 생성 날짜, 수정 날짜 및 크기와 같은 세부 정보를 검색하고 표시하는 방법을 보여줍니다.

#### Q: 이 튜토리얼을 사용하여 검색된 첨부 파일은 어떻게 저장됩니까?

A: 튜토리얼에서는 검색된 각 첨부 파일을 지정된 디렉터리에 별도의 파일로 저장하는 과정을 안내합니다.

#### Q: 이 지식을 사용하여 비밀번호로 보호된 PDF 파일에서 첨부 파일을 추출할 수 있습니까?

A: 예, 유사한 원칙을 적용하여 .NET용 Aspose.PDF를 사용하여 비밀번호로 보호된 PDF 파일에서 첨부 파일을 검색할 수 있습니다.

#### Q: .NET용 Aspose.PDF는 어떻게 첨부 파일 검색을 용이하게 합니까?

A: Aspose.PDF for .NET은 PDF 문서의 첨부 파일에 쉽게 액세스하고 조작할 수 있는 직관적인 API를 제공합니다.

#### Q: 첨부 파일 검색이 권장되는 특정 시나리오가 있습니까?

A: 첨부 파일 검색은 이미지, 오디오 파일 또는 추가 문서 추출과 같이 PDF에 포함된 파일에 액세스해야 할 때 유용합니다.