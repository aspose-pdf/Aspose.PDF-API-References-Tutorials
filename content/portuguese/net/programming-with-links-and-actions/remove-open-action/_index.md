---
title: Remover ação aberta
linktitle: Remover ação aberta
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como remover a ação aberta de um PDF usando o Aspose.PDF para .NET.
type: docs
weight: 80
url: /pt/net/programming-with-links-and-actions/remove-open-action/
---
Aprenda como remover a ação aberta de um arquivo PDF usando o Aspose.PDF para .NET com este guia passo a passo.

## Etapa 1: Configurando o ambiente

Certifique-se de ter configurado seu ambiente de desenvolvimento com um projeto C# e as referências Aspose.PDF apropriadas.

## Etapa 2: Carregando o arquivo PDF

Defina o caminho do diretório dos seus documentos e carregue o arquivo PDF usando o seguinte código:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Abra o documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## Etapa 3: Excluir a ação aberta

 Remova a ação aberta do documento definindo o`OpenAction` propriedade para nulo:

```csharp
document. OpenAction = null;
```

## Etapa 4: Salve o documento atualizado

 Salve o documento atualizado usando o`Save` método:

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## Etapa 5: Exibindo o resultado

Exiba uma mensagem indicando que a ação aberta foi removida com sucesso e especifique o local do arquivo salvo:

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### Código-fonte de exemplo para Remover Ação Aberta usando Aspose.PDF para .NET 
```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Abrir documento
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
// Remover ação de abertura de documento
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
// Salvar documento atualizado
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## Conclusão

Parabéns! Agora você sabe como remover a ação aberta de um PDF usando o Aspose.PDF para .NET. Use esse conhecimento para personalizar as propriedades e o comportamento de arquivos PDF em seus projetos.

Agora que você concluiu este guia, pode aplicar esses conceitos aos seus próprios projetos e explorar ainda mais os recursos oferecidos pelo Aspose.PDF para .NET.

### Perguntas frequentes 

#### P: O que é a "ação aberta" em um arquivo PDF?

R: A "ação de abertura" em um arquivo PDF é uma instrução que especifica o que deve acontecer quando o PDF é aberto. Pode incluir ações como navegar para uma página ou local específico dentro do documento, iniciar um aplicativo externo ou exibir uma visualização específica.

#### P: Por que eu desejaria remover a ação de abertura de um arquivo PDF?

R: Remover a ação de abrir pode aumentar a segurança, a experiência do usuário e o controle sobre como o PDF é apresentado quando aberto. Por exemplo, você pode querer impedir a navegação automática ou desabilitar certas ações ao abrir o documento.

#### P: Como o Aspose.PDF para .NET ajuda a remover a ação de abertura?

A: Aspose.PDF para .NET fornece APIs para manipular vários aspectos de arquivos PDF. Este tutorial demonstra como remover a ação open usando código C#.

#### P: Há algum risco ou consideração potencial ao remover a ação aberta?

R: Remover a ação de abrir pode alterar o comportamento padrão do PDF, então garanta que ele esteja alinhado com a experiência do usuário pretendida. Teste o PDF modificado completamente para confirmar que a remoção não afeta outras funcionalidades.

#### P: Posso personalizar a ação aberta para executar outras ações?

R: Sim, o Aspose.PDF para .NET permite que você personalize a ação de abertura definindo-a para vários tipos de ações, como navegar para uma página específica ou executar JavaScript.

#### P: Posso remover ações abertas de PDFs protegidos por senha?
R: Sim, você pode remover ações abertas de PDFs protegidos por senha, desde que forneça as credenciais apropriadas para acessar e modificar o documento.

#### P: A remoção da ação aberta é reversível?

R: Não, depois que a ação de abertura for removida e o PDF for salvo, a ação de abertura original não poderá ser restaurada a partir do PDF modificado.

#### P: Como posso verificar se a ação aberta foi removida com sucesso?

R: Após remover a ação aberta usando o código fornecido, abra o PDF modificado e confirme se nenhuma ação específica ocorre ao abrir.

#### P: Posso remover ações abertas de vários arquivos PDF simultaneamente?

R: Sim, você pode usar a mesma abordagem para remover ações abertas de vários arquivos PDF em um cenário de processamento em lote.