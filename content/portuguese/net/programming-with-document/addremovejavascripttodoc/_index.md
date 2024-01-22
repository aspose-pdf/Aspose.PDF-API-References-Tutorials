---
title: Adicionar Remover Javascript ao documento PDF
linktitle: Adicionar remover Javascript ao documento
second_title: Referência da API Aspose.PDF para .NET
description: Aprenda como adicionar e remover JavaScript em documentos PDF usando Aspose.PDF for .NET. Guia passo a passo com tutoriais de código para scripts em nível de documento.
type: docs
weight: 30
url: /pt/net/programming-with-document/addremovejavascripttodoc/
---
Para adicionar e remover JavaScript em documentos PDF, utilizaremos a biblioteca Aspose.PDF para .NET. Esta poderosa biblioteca nos permite manipular arquivos PDF em aplicativos .NET. Siga as instruções passo a passo abaixo para adicionar e remover JavaScript usando Aspose.PDF for .NET.

## Passo 1: Crie um novo documento PDF

 Comece criando uma nova instância do`Document` classe fornecida por Aspose.PDF para .NET. Este servirá como o documento PDF onde adicionaremos o JavaScript.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
```

## Etapa 2: adicionar JavaScript no nível do documento

 Para adicionar JavaScript no nível do documento, use o`JavaScript` propriedade do`Document` aula. Atribua funções JavaScript a chaves no dicionário JavaScript.

```csharp
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");
```

 Neste tutorial, adicionamos duas funções JavaScript,`func1` e`func2`, para o documento PDF.

## Etapa 3: remover JavaScript em nível de documento

 Para remover o JavaScript no nível do documento, carregue o documento PDF e acesse o`JavaScript`dicionário. Itere sobre as chaves e remova a função JavaScript desejada.

```csharp
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;

foreach (string key in keys)
{
    Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed");
```

 Neste tutorial, removemos o`func1` Função JavaScript do documento PDF.

## Etapa 4: salvar e verificar as alterações

Salve o documento PDF modificado e verifique as alterações.

```csharp
Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

Este código salvará o documento PDF modificado e exibirá a mensagem de sucesso.

### Exemplo de código-fonte para Adicionar Remover Javascript de documentos PDF usando Aspose.PDF para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
doc.JavaScript["func1"] = "function func1() { hello(); }";
doc.JavaScript["func2"] = "function func2() { hello(); }";
doc.Save(dataDir + "AddJavascript.pdf");

// Remover JavaScript no nível do documento
Document doc1 = new Document(dataDir + "AddJavascript.pdf");
IList keys = (System.Collections.IList)doc1.JavaScript.Keys;
Console.WriteLine("=============================== ");
foreach (string key in keys)
{
	Console.WriteLine(key + " ==> " + doc1.JavaScript[key]);
}

doc1.JavaScript.Remove("func1");
Console.WriteLine("Key 'func1' removed ");
Console.WriteLine("=============================== ");

Console.WriteLine("\nJavascript added/removed successfully to a document.");
```

## Conclusão

Neste artigo, fornecemos um guia passo a passo para adicionar e remover JavaScript de documentos PDF usando Aspose.PDF for .NET. Seguindo as instruções e utilizando os tutoriais de código fornecidos, você pode facilmente incorporar JavaScript em seus documentos PDF e removê-lo quando necessário. JavaScript permite funcionalidade dinâmica e interatividade em seus arquivos PDF, melhorando a experiência do usuário.


### Perguntas frequentes sobre como adicionar e remover javascript ao documento PDF

#### P: O que é Aspose.PDF para .NET?

R: Aspose.PDF for .NET é uma biblioteca poderosa que permite aos desenvolvedores manipular arquivos PDF em aplicativos .NET de maneira eficaz. Ele fornece recursos abrangentes para trabalhar com documentos PDF de forma programática.

#### P: Como posso adicionar JavaScript a um documento PDF usando Aspose.PDF for .NET?

 R: Você pode adicionar JavaScript no nível do documento usando o`JavaScript` propriedade do`Document` aula. Simplesmente atribua funções JavaScript às chaves do dicionário JavaScript.

#### P: Posso remover JavaScript de um documento PDF usando Aspose.PDF for .NET?

 R: Sim, você pode remover JavaScript de um documento PDF acessando o`JavaScript` dicionário e removendo a função JavaScript desejada.

#### P: O Aspose.PDF for .NET é adequado para projetos profissionais?

R: Com certeza, o Aspose.PDF for .NET é amplamente utilizado em projetos profissionais para manipulação e geração de PDF. Oferece alto desempenho e funcionalidade confiável.

#### P: Quais são os benefícios de adicionar JavaScript a um documento PDF?

R: Adicionar JavaScript a um documento PDF permite criar arquivos PDF interativos e dinâmicos. Você pode implementar validação de formulário, realizar cálculos e adicionar vários recursos de interatividade para aprimorar a experiência do usuário.