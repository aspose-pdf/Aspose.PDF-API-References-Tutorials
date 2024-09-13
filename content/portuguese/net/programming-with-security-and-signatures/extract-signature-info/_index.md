---
title: Extrair informações de assinatura
linktitle: Extrair informações de assinatura
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como extrair assinaturas digitais e informações de certificado de documentos PDF usando Aspose.PDF para .NET. Um guia passo a passo completo para desenvolvedores C#.
type: docs
weight: 80
url: /pt/net/programming-with-security-and-signatures/extract-signature-info/
---
## Introdução

No mundo digital de hoje, garantir a segurança e a integridade dos documentos é crucial. Um dos métodos comuns usados para proteger PDFs é adicionar uma assinatura digital. No entanto, recuperar e verificar os detalhes da assinatura pode às vezes ser um desafio, especialmente quando você está lidando com vários certificados. Neste guia, nós o guiaremos pelo processo de extração de informações de assinatura de documentos PDF usando o Aspose.PDF para .NET, tornando a tarefa muito fácil. Você aprenderá como acessar campos de assinatura, extrair informações de certificado e salvá-las em um arquivo.

## Pré-requisitos

Antes de começar, vamos garantir que você tenha tudo pronto para começar.

-  Biblioteca Aspose.PDF para .NET: Se você ainda não a tem, pode baixá-la do[Página de download do Aspose.PDF para .NET](https://releases.aspose.com/pdf/net/). 
- Ambiente de desenvolvimento .NET: você precisará de um IDE como o Visual Studio.
- Conhecimento básico de C#: A familiaridade com C# é útil para entender os trechos de código neste tutorial.
- Documento PDF com assinatura digital: para fins de teste, certifique-se de ter um arquivo PDF que contenha pelo menos uma assinatura digital.

## Importando namespaces necessários

Antes de pular para o código, é importante importar os namespaces necessários. Esses namespaces permitirão que você acesse a funcionalidade Aspose.PDF e trabalhe com documentos PDF.

```csharp
using System.IO;
using Aspose.Pdf.Forms;
using Aspose.Pdf;
using System;
```

Agora que você configurou o essencial, vamos passar para o processo real de extração de informações de assinatura de um PDF.

## Etapa 1: Configurando o diretório de documentos

 Antes de trabalhar em um documento PDF, você precisa especificar o local do arquivo que você usará. Você pode substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real do diretório onde seus PDFs estão armazenados.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
string input = dataDir + "ExtractSignatureInfo.pdf";
```

Aqui, especificamos o diretório que contém o arquivo PDF e o próprio nome do arquivo. Certifique-se de que o arquivo exista naquele diretório!

## Etapa 2: Carregando o documento PDF

 Agora que você configurou seu diretório, a próxima etapa é carregar o documento PDF usando o`Document` aula do Aspose.PDF.

```csharp
using (Document pdfDocument = new Document(input))
{
    // Processe o PDF aqui.
}
```

 Esta linha de código inicializa um`Document`objeto que representa o arquivo PDF. O`using` A declaração garante que os recursos sejam limpos após o documento ser processado.

## Etapa 3: Acessando campos de formulário

Nesta etapa, faremos um loop por todos os campos de formulário no documento PDF. Como as assinaturas são normalmente armazenadas como campos de formulário, esta etapa nos ajudará a identificar os campos de assinatura.

```csharp
foreach (Field field in pdfDocument.Form)
{
    // Identifique os campos de assinatura aqui.
}
```

 Ao iterar através do`Form` propriedade do`Document` objeto, podemos examinar cada campo do formulário para verificar se é um campo de assinatura.

## Etapa 4: Identificando campos de assinatura

 Depois de acessar os campos do formulário, o próximo passo é identificar quais são os campos de assinatura. Podemos fazer isso convertendo cada campo para um`SignatureField` objeto.

```csharp
SignatureField sf = field as SignatureField;
if (sf != null)
{
    // Extrair informações de assinatura.
}
```

 Aqui, usamos o`as` palavra-chave para tentar converter cada campo de formulário para um`SignatureField`. Se a conversão for bem-sucedida, sabemos que o campo é uma assinatura.

## Etapa 5: Extraindo o Certificado

Agora que você identificou o campo de assinatura, a próxima tarefa é extrair o certificado da assinatura. Os certificados contêm informações cruciais sobre o signatário e a validade da assinatura.

```csharp
Stream cerStream = sf.ExtractCertificate();
```

 O`ExtractCertificate` método retorna um`Stream` objeto contendo os dados do certificado. Este fluxo pode ser usado para salvar o certificado para posterior análise ou armazenamento.

## Etapa 6: Salvando o certificado em um arquivo

 Depois de extrair o certificado, a etapa final é salvá-lo em um arquivo. Neste caso, salvaremos o certificado como um`.cer` arquivo.

```csharp
if (cerStream != null)
{
    using (cerStream)
    {
        byte[] bytes = new byte[cerStream.Length];
        using (FileStream fs = new FileStream(dataDir + @"input.cer", FileMode.CreateNew))
        {
            cerStream.Read(bytes, 0, bytes.Length);
            fs.Write(bytes, 0, bytes.Length);
        }
    }
}
```

Neste bloco de código, nós:

1. Verifique se o fluxo do certificado não é nulo.
2. Leia os dados do certificado em uma matriz de bytes.
3.  Escreva a matriz de bytes em um`.cer` arquivo no diretório de documentos.

## Conclusão

Extrair assinaturas digitais e suas informações de certificado relacionadas de documentos PDF usando Aspose.PDF para .NET é bastante direto quando dividido em etapas simples. Quer você esteja auditando documentos, verificando assinaturas ou apenas armazenando certificados para guarda, este tutorial o equipa com o conhecimento para fazer isso de forma eficiente. Lembre-se, proteger e verificar documentos é essencial no mundo digital de hoje, e usar ferramentas como Aspose.PDF para .NET torna isso muito mais fácil de manusear.

## Perguntas frequentes

### Posso extrair várias assinaturas de um PDF usando o Aspose.PDF para .NET?
Sim, o código percorre todos os campos do formulário no documento, permitindo que você extraia várias assinaturas, se elas existirem.

### O que acontece se nenhuma assinatura for encontrada no PDF?
Se não houver campos de assinatura presentes, o código simplesmente os ignorará sem gerar erro.

### Posso usar essa abordagem para verificar a validade de uma assinatura?
Embora você possa extrair o certificado, verificar a validade de uma assinatura requer etapas adicionais, como verificar a cadeia de confiança do certificado.

### É possível extrair outros dados de campos de formulário usando o Aspose.PDF para .NET?
Sim, o Aspose.PDF permite que você acesse e manipule vários tipos de campos de formulário em um PDF, não apenas campos de assinatura.

### Como posso visualizar os detalhes do certificado extraído?
 Depois que o certificado for salvo como um`.cer` arquivo, você pode abri-lo usando qualquer visualizador de certificado ou importá-lo para um armazenamento de certificados do sistema para inspeção posterior.