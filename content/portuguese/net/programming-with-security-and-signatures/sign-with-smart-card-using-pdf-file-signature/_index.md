---
title: Assinar com cartão inteligente usando assinatura de arquivo PDF
linktitle: Assinar com cartão inteligente usando assinatura de arquivo PDF
second_title: Referência da API do Aspose.PDF para .NET
description: Aprenda como assinar arquivos PDF usando um cartão inteligente com Aspose.PDF para .NET. Siga este guia passo a passo para assinaturas digitais seguras.
type: docs
weight: 110
url: /pt/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## Introdução

Na era digital, proteger documentos é mais crucial do que nunca. Seja um contrato, um acordo ou qualquer informação sensível, garantir que o documento seja autêntico e não tenha sido adulterado é primordial. Insira assinaturas digitais! Hoje, vamos nos aprofundar em como assinar um arquivo PDF usando um cartão inteligente com Aspose.PDF para .NET. Esta biblioteca poderosa permite que os desenvolvedores manipulem e criem documentos PDF de forma eficiente, incluindo a adição de assinaturas digitais seguras. Então, pegue seu cartão inteligente e vamos começar!

## Pré-requisitos

Antes de pularmos para os detalhes de assinar um arquivo PDF, vamos garantir que você tenha tudo o que precisa. Aqui está uma lista de verificação para ajudar você a se preparar:

1.  Aspose.PDF para .NET: Certifique-se de ter a biblioteca Aspose.PDF instalada. Você pode baixá-la do[site](https://releases.aspose.com/pdf/net/).
2. Visual Studio: um ambiente de desenvolvimento onde você pode escrever e executar seu código .NET.
3. Cartão inteligente: você precisará de um cartão inteligente com um certificado digital válido instalado.
4. Conhecimento básico de C#: A familiaridade com a programação em C# será benéfica, pois escreveremos trechos de código nessa linguagem.
5. Documento PDF: Um arquivo PDF de amostra (como`blank.pdf`) para testar nosso processo de assinatura.

Com esses pré-requisitos em vigor, você está pronto para mergulhar no código!

## Pacotes de importação

Primeiro, vamos importar os pacotes necessários. Você precisará adicionar referências à biblioteca Aspose.PDF no seu projeto. Veja como você pode fazer isso:

1. Abra o Visual Studio.
2. Crie um novo projeto ou abra um existente.
3.  Clique com o botão direito do mouse no seu projeto no Solution Explorer e selecione`Manage NuGet Packages`.
4.  Procurar`Aspose.PDF` e instale a versão mais recente.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Agora que importamos os pacotes necessários, vamos analisar o código passo a passo.

## Etapa 1: configure seu documento

O primeiro passo do nosso processo é configurar o documento PDF que queremos assinar. Veja como você pode fazer isso:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
 Neste snippet, definimos o caminho para nosso diretório de documentos e criamos uma instância do`Document` classe usando um arquivo PDF de exemplo chamado`blank.pdf` . Certifique-se de substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real onde seu PDF está localizado.

## Etapa 2: inicializar PdfFileSignature

 Em seguida, inicializaremos o`PdfFileSignature` classe, que é responsável por lidar com o processo de assinatura.

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
Aqui, criamos uma instância de`PdfFileSignature` vinculá-lo ao nosso documento PDF. Isso prepara o documento para assinatura.

## Etapa 3: Acesse o certificado do cartão inteligente

Agora vem a parte crucial — acessar o certificado digital armazenado no seu smart card. É assim que podemos fazer:

### Abra o Certificate Store

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
Abrimos o certificate store localizado no perfil do usuário atual. Isso nos permite acessar os certificados instalados na sua máquina, incluindo aqueles no seu smart card.

### Selecione o certificado

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
Este código solicita que o usuário selecione um certificado da coleção. A interface do usuário exibirá todos os certificados disponíveis, permitindo que você escolha aquele associado ao seu smart card.

## Etapa 4: Crie a assinatura externa

Depois de selecionar seu certificado, o próximo passo é criar uma assinatura externa usando o certificado selecionado.

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
Aqui, criamos uma instância de`ExternalSignature` usando o certificado selecionado. Este objeto será usado para assinar o documento PDF.

## Etapa 5: Defina a aparência da assinatura

Agora, vamos definir a aparência da nossa assinatura. É aqui que você pode personalizar como sua assinatura aparece no documento.

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
 Neste snippet, especificamos a aparência da assinatura fornecendo o caminho para um arquivo de imagem (como um logotipo ou um gráfico de assinatura). Certifique-se de substituir`"demo.png"` com a imagem real que você deseja usar.

## Etapa 6: Assine o PDF

Com tudo configurado, é hora de assinar o documento PDF!

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
Nesta etapa, chamamos de`Sign` método em nosso`pdfSign` objeto. Aqui está o que cada parâmetro significa:
- `1`: O número da página onde a assinatura aparecerá.
- `"Reason"`: O motivo da assinatura do documento.
- `"Contact"`: Informações de contato do signatário.
- `"Location"`: A localização do signatário.
- `true`: Indica se deve criar uma assinatura visível.
- `new System.Drawing.Rectangle(100, 100, 200, 200)`: A posição e o tamanho da assinatura no PDF.
- `externalSignature`: O objeto de assinatura que criamos anteriormente.

 Por fim, salvamos o documento assinado como`externalSignature2.pdf`.

## Etapa 7: Verifique a assinatura

Após assinar o documento, é essencial verificar se a assinatura é válida. Veja como fazer isso:

### Inicializar processo de verificação

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
 Criamos uma nova instância de`PdfFileSignature` para o documento assinado. Então recuperamos os nomes de todas as assinaturas presentes no documento.

### Verificar validade da assinatura

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
Fazemos um loop por cada nome de assinatura e verificamos sua validade. Se alguma assinatura falhar na verificação, uma exceção é lançada, indicando que a assinatura não é válida.

## Conclusão

E aí está! Você assinou com sucesso um documento PDF usando um cartão inteligente com Aspose.PDF para .NET. Este processo não apenas protege seu documento, mas também adiciona uma camada de autenticidade que é crucial no mundo digital de hoje. Quer você esteja lidando com contratos, documentos legais ou qualquer informação sensível, saber como implementar assinaturas digitais é uma habilidade valiosa. 

## Perguntas frequentes

### O que é Aspose.PDF para .NET?
Aspose.PDF para .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, manipular e converter documentos PDF em aplicativos .NET.

### Preciso de um cartão inteligente para assinar PDFs?
Embora um cartão inteligente não seja obrigatório, ele é altamente recomendado para assinaturas digitais seguras, pois fornece uma camada adicional de segurança.

### Posso usar qualquer arquivo PDF para assinar?
Sim, você pode usar qualquer arquivo PDF, mas certifique-se de que ele não esteja protegido por senha. Se estiver, você precisará desbloqueá-lo primeiro.

### E se eu não tiver um certificado digital?
Você pode obter um certificado digital de uma autoridade de certificação (CA) confiável ou usar um certificado autoassinado para fins de teste.

### Existe uma versão de teste do Aspose.PDF disponível?
 Sim, você pode baixar uma versão de teste gratuita no[Site Aspose](https://releases.aspose.com/).