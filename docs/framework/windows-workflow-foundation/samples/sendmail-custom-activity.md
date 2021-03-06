---
title: Atividade personalizado de SendMail
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: e7cc64e68c3d78b9ee7ec813700e96a52c239141
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182778"
---
# <a name="sendmail-custom-activity"></a>Atividade personalizado de SendMail
Este exemplo demonstra como criar uma atividade personalizada que derive de <xref:System.Activities.AsyncCodeActivity> para enviar email SMTP usando para uso em um aplicativo de fluxo de trabalho. A atividade personalizada usa <xref:System.Net.Mail.SmtpClient> os recursos de enviar e-mails de forma assíncrona e enviar e-mails com autenticação. Também fornece alguns recursos de usuário final como o modo de teste, a substituição de token, os modelos de arquivo, e o caminho da operação de teste.  
  
 A tabela a seguir detalha os argumentos para atividades de `SendMail` .  
  
|Nome|Type|Descrição|  
|-|-|-|  
|Host|String|Endereço do host de servidor SMTP.|  
|Porta|String|Porta de serviço SMTP no host.|  
|EnableSsl|bool|Especifica se <xref:System.Net.Mail.SmtpClient> usar secure sockets (SSL) para criptografar a conexão.|  
|UserName|String|Nome de usuário para configurar as credenciais para autenticar a propriedade de <xref:System.Net.Mail.SmtpClient.Credentials%2A> de retorno.|  
|Senha|String|Senha para configurar as credenciais para autenticar a propriedade de <xref:System.Net.Mail.SmtpClient.Credentials%2A> de retorno.|  
|Assunto|<xref:System.Activities.InArgument%601>\<> de corda|Assunto de mensagem.|  
|Corpo|<xref:System.Activities.InArgument%601>\<> de corda|Corpo da mensagem.|  
|Anexos|<xref:System.Activities.InArgument%601>\<> de corda|Coleta de anexos usada para armazenar dados anexados a esta mensagem de e-mail.|  
|De|<xref:System.Net.Mail.MailAddress>|Do endereço para esta mensagem de e-mail.|  
|Para|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Coleção de endereços que contém os destinatários desta mensagem de e-mail.|  
|CC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Coleção de endereços que contém os destinatários da cópia de carbono (CC) para esta mensagem de e-mail.|  
|BCC|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|Coleção de endereços que contém os destinatários da cópia de carbono cego (BCC) para esta mensagem de e-mail.|  
|Tokens|<xref:System.Activities.InArgument%601><seqüência iDictionary,\<>> de seqüência|Tokens a substituição no corpo. Esse recurso permite que os usuários especifiquem alguns valores no corpo do que pode ser substituído pelos tokens fornecidos posteriormente usando essa propriedade.|  
|BodyTemplateFilePath|String|Caminho de um modelo para o corpo. A atividade de `SendMail` copia o conteúdo do arquivo a sua propriedade body.<br /><br /> O modelo pode conter os tokens que são substituídos pelos conteúdos da propriedade tokens.|  
|TestMailTo|<xref:System.Net.Mail.MailAddress>|Quando esta propriedade é definida, todos os e-mails são enviados para o endereço especificado nela.<br /><br /> Esta propriedade destina-se a ser usada ao testar fluxos de trabalho. Por exemplo, quando você quiser ter certeza de que todos os e-mails são enviados sem enviá-los para os destinatários reais.|  
|TestDropPath|String|Quando esta propriedade é definida, todos os e-mails também são salvos no arquivo especificado.<br /><br /> Esta propriedade destina-se a ser usada quando você estiver testando ou depurando fluxos de trabalho, para garantir que o formato e o conteúdo dos e-mails de saída sejam apropriados.|  
  
## <a name="solution-contents"></a>Conteúdo de solução  
 A solução contém dois projetos.  
  
|Project|Descrição|Arquivos importantes|  
|-------------|-----------------|---------------------|  
|SendMail|A atividade de SendMail|1. SendMail.cs: implementação da atividade principal<br />2. SendMailDesigner.xaml e SendMailDesigner.xaml.cs: designer para a atividade do SendMail<br />3. MailTemplateBody.htm: modelo para o e-mail a ser enviado.|  
|SendMailTestClient|Cliente para testar a atividade de SendMail.  Este projeto mostra duas maneiras para chamar a atividade de SendMail: declarativamente, e programaticamente.|1. Sequence1.xaml: fluxo de trabalho que invoca a atividade sendmail.<br />2. Program.cs: invoca sequence1 e também cria um fluxo de trabalho programática que usa o SendMail.|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a>Configuração adicional de atividade de SendMail  
 Embora não mostrado no exemplo, os usuários podem executar a configuração de adição de atividade de SendMail. As três seções a seguir demonstram como este é feita.  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a>Enviando um email usando os tokens especificados no corpo  
 Este snippet de código demonstra como você pode enviar email com tokens no corpo. Observe como os tokens são fornecidos na propriedade body. Os valores para estes tokens são fornecidos para a propriedade tokens.  
  
```csharp  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a>Enviando um email usando um modelo  
 Este snippet mostra como enviar um email usando tokens de um modelo no corpo. Observe que ao definir a propriedade de `BodyTemplateFilePath` não precisamos de fornecer o valor para a propriedade body (o conteúdo do arquivo de modelo serão copiados para o corpo).  
  
```csharp  
new SendMail  
{
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a>Enviar email no modo de teste  
 Este trecho de código mostra como definir as duas `TestMailTo` propriedades de teste: `john.doe@contoso.con` definindo para todas as mensagens serão enviadas (sem considerar os valores de To, Cc, Bcc). Definindo TestDropPath todos os email de saída também serão gravados no caminho fornecido. Essas propriedades podem ser definidas independentes (não são relacionadas).  
  
```csharp  
new SendMail  
{
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a>Instruções de configuração  
 O acesso a um servidor SMTP é necessário para esse exemplo.  
  
 Para obter mais informações sobre como configurar um servidor SMTP, consulte os links a seguir.  
  
- [Configurando o serviço SMTP (IIS 6.0)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))  
  
- [IIS 7.0: Configurar o email SMTP](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))  
  
- [Como instalar o serviço SMTP](https://docs.microsoft.com/previous-versions/tn-archive/aa997480(v=exchg.65))  
  
 Os emuladores SMTP fornecidos por terceiros estão disponíveis para download.  
  
##### <a name="to-run-this-sample"></a>Para executar este exemplo  
  
1. Usando o Visual Studio 2010, abra o arquivo de solução SendMail.sln.  
  
2. Certifique-se de que você tem acesso a um servidor SMTP válido. Consulte as instruções de configuração.  
  
3. Configure o programa com o endereço do servidor e de e-mail e de e-mail.  
  
     Para executar corretamente esta amostra, talvez seja necessário configurar o valor dos endereços de e-mail de From e To e o endereço do servidor SMTP em Program.cs e em Sequence.xaml. Você precisará alterar o endereço nos dois lugares como o envia email de programa em duas maneiras diferentes  
  
4. Para criar a solução, pressione CTRL+SHIFT+B.  
  
5. Para executar a solução, pressione CTRL+F5.  
  
> [!IMPORTANT]
> Os exemplos podem já estar instalados no seu computador. Verifique o seguinte diretório (padrão) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se esse diretório não existir, vá para [a Windows Communication Foundation (WCF) e para o Windows Workflow Foundation (WF) Amostras para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para baixar todas as Amostras e amostras da [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (Windows Communication Foundation). Este exemplo está localizado no seguinte diretório.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
