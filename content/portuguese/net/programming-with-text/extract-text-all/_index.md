---
title: Extrair texto todo em arquivo PDF
linktitle: Extrair texto AllIn PDF File
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como extrair todo o texto em um arquivo PDF usando o Aspose.PDF para .NET.
type: docs
weight: 180
url: /pt/net/programming-with-text/extract-text-all/
---
Este tutorial guiará você pelo processo de extração de todo o texto em arquivo PDF usando Aspose.PDF para .NET. O código-fonte C# fornecido demonstra as etapas necessárias.

## Requisitos
Antes de começar, certifique-se de ter o seguinte:

- Visual Studio ou qualquer outro compilador C# instalado em sua máquina.
- Biblioteca Aspose.PDF para .NET. Você pode baixá-la do site oficial do Aspose ou usar um gerenciador de pacotes como o NuGet para instalá-la.

## Etapa 1: Configurar o projeto
1. Crie um novo projeto C# no seu ambiente de desenvolvimento preferido.
2. Adicione uma referência à biblioteca Aspose.PDF para .NET.

## Etapa 2: Importar os namespaces necessários
No arquivo de código onde você deseja extrair o texto, adicione as seguintes diretivas using no topo do arquivo:

```csharp
using Aspose.Pdf;
using System.IO;
```

## Etapa 3: Defina o diretório do documento
 No código, localize a linha que diz`string dataDir = "YOUR DOCUMENT DIRECTORY";` e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho para o diretório onde seus documentos estão armazenados.

## Etapa 4: Abra o documento PDF
 Abra um documento PDF existente usando o`Document`construtor e passando o caminho para o arquivo PDF de entrada.

```csharp
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
```

## Etapa 5: Extraia todo o texto
 Criar um`TextAbsorber`objeto para extrair texto do documento. Então, aceite o absorber para todas as páginas.

```csharp
TextAbsorber textAbsorber = new TextAbsorber();
pdfDocument.Pages.Accept(textAbsorber);
```

## Etapa 6: Obtenha o texto extraído
 Acesse o texto extraído do`TextAbsorber` objeto.

```csharp
string extractedText = textAbsorber.Text;
```

## Etapa 7: Salve o texto extraído
 Criar um`TextWriter` e abra o arquivo onde você quer salvar o texto extraído. Grave o texto extraído no arquivo e feche o stream.

```csharp
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
tw.WriteLine(extractedText);
tw. Close();
```

### Exemplo de código-fonte para Extrair Texto Todo usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document pdfDocument = new Document(dataDir + "ExtractTextAll.pdf");
// Crie um objeto TextAbsorber para extrair texto
TextAbsorber textAbsorber = new TextAbsorber();
// Aceite o absorvedor para todas as páginas
pdfDocument.Pages.Accept(textAbsorber);
// Obter o texto extraído
string extractedText = textAbsorber.Text;
// Crie um escritor e abra o arquivo
TextWriter tw = new StreamWriter(dataDir + "extracted-text.txt");
// Escreva uma linha de texto no arquivo
tw.WriteLine(extractedText);
// Feche o fluxo
tw.Close();
```

## Conclusão
Você extraiu com sucesso todo o texto de um documento PDF usando Aspose.PDF for .NET. O texto extraído foi salvo no arquivo de saída especificado.

### Perguntas frequentes

#### P: Qual é o propósito deste tutorial?

R: Este tutorial serve como um guia para ajudar você a extrair todo o texto de um arquivo PDF usando o Aspose.PDF para .NET. O código-fonte C# que o acompanha fornece instruções passo a passo para realizar esta tarefa.

#### P: Quais namespaces devo importar?

R: No arquivo de código onde você pretende extrair o texto, inclua as seguintes diretivas using no início do arquivo:

```csharp
using Aspose.Pdf;
using System.IO;
```

#### P: Como especifico o diretório do documento?

 A: Localize a linha`string dataDir = "YOUR DOCUMENT DIRECTORY";` no código e substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

#### P: Como abro um documento PDF existente?

 R: Na Etapa 4, você abrirá um documento PDF existente usando o`Document` construtor e fornecendo o caminho para o arquivo PDF de entrada.

#### P: Como faço para extrair todo o texto do documento?

 A: A etapa 5 envolve a criação de um`TextAbsorber` objeto para extrair texto do documento PDF. Então, você aceitará o absorber para todas as páginas.

#### P: Como acesso o texto extraído?

 A: A etapa 6 orienta você no acesso ao texto extraído do`TextAbsorber` objeto.

#### P: Como faço para salvar o texto extraído em um arquivo?

 A: Na Etapa 7, você criará um`TextWriter`, abra o arquivo onde deseja salvar o texto extraído, grave o texto extraído no arquivo e feche o fluxo.

#### P: Qual é a principal lição deste tutorial?

R: Ao seguir este tutorial, você aprendeu como extrair todo o texto de um documento PDF usando o Aspose.PDF for .NET. O texto extraído foi salvo em um arquivo de saída especificado, permitindo que você analise e manipule o conteúdo textual do documento.