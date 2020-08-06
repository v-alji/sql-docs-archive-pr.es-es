---
title: Enviar un mensaje de correo electrónico HTML con la tarea Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Send Mail task [Integration Services]
- Script task [Integration Services], examples
- Script task [Integration Services], HTML mail message
ms.assetid: dd2b1eef-b04f-4946-87ab-7bc56bb525ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6c1a967b52a84e1ff9c2e54c48e40f4d149b2dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744208"
---
# <a name="sending-an-html-mail-message-with-the-script-task"></a><span data-ttu-id="a725d-102">Enviar un mensaje de correo electrónico HTML con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="a725d-102">Sending an HTML Mail Message with the Script Task</span></span>
  <span data-ttu-id="a725d-103">La tarea SendMail de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] solamente admite los mensajes de correo en texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="a725d-103">The [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] SendMail task only supports mail messages in plain text format.</span></span> <span data-ttu-id="a725d-104">Sin embargo, puede enviar con facilidad los mensajes de correo HTML mediante la tarea Script y las funciones de correo de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a725d-104">However you can easily send HTML mail messages by using the Script task and the mail capabilities of the .NET Framework.</span></span>

> [!NOTE]
>  <span data-ttu-id="a725d-105">Si desea crear una tarea que pueda reutilizar más fácilmente en varios paquetes, considere la posibilidad de utilizar el código de este ejemplo de tarea Script como punto inicial de una tarea personalizada.</span><span class="sxs-lookup"><span data-stu-id="a725d-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="a725d-106">Para más información, vea [Desarrollar una tarea personalizada](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="a725d-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="a725d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a725d-107">Description</span></span>
 <span data-ttu-id="a725d-108">En el ejemplo siguiente se usa el espacio de nombres `System.Net.Mail` para configurar y enviar un mensaje de correo HTML.</span><span class="sxs-lookup"><span data-stu-id="a725d-108">The following example uses the `System.Net.Mail` namespace to configure and send an HTML mail message.</span></span> <span data-ttu-id="a725d-109">El script obtiene los campos Para, De, Asunto y el cuerpo del correo electrónico de las variables de paquete, los usa para crear un nuevo `MailMessag`e y establece su propiedad `IsBodyHtml` en `True`.</span><span class="sxs-lookup"><span data-stu-id="a725d-109">The script obtains the To, From, Subject, and body of the e-mail from package variables, uses them to create a new `MailMessag`e, and sets its `IsBodyHtml` property to `True`.</span></span> <span data-ttu-id="a725d-110">A continuación, obtiene el nombre del servidor SMTP de otra variable de paquete, inicializa una instancia de `System.Net.Mail.SmtpClient` y llama a su método `Send` para enviar el mensaje HTML.</span><span class="sxs-lookup"><span data-stu-id="a725d-110">Then it obtains the SMTP server name from another package variable, initializes an instance of `System.Net.Mail.SmtpClient`, and calls its `Send` method to send the HTML message.</span></span> <span data-ttu-id="a725d-111">En el ejemplo se encapsula el mensaje enviando la funcionalidad en una subrutina que se puede reutilizar en otros scripts.</span><span class="sxs-lookup"><span data-stu-id="a725d-111">The sample encapsulates the message sending functionality in a subroutine that could be reused in other scripts.</span></span>

#### <a name="to-configure-this-script-task-example-without-an-smtp-connection-manager"></a><span data-ttu-id="a725d-112">Para configurar este ejemplo de tarea Script sin un administrador de conexiones SMTP</span><span class="sxs-lookup"><span data-stu-id="a725d-112">To configure this Script Task example without an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="a725d-113">Cree las variables de cadena con nombre `HtmlEmailTo`, `HtmlEmailFrom`y `HtmlEmailSubject`, y asígneles los valores adecuados para un mensaje de pruebas válido.</span><span class="sxs-lookup"><span data-stu-id="a725d-113">Create string variables named `HtmlEmailTo`, `HtmlEmailFrom`, and `HtmlEmailSubject` and assign appropriate values to them for a valid test message.</span></span>

2.  <span data-ttu-id="a725d-114">Cree una variable de cadena con nombre `HtmlEmailBody` y asígnele una cadena de marcado HTML.</span><span class="sxs-lookup"><span data-stu-id="a725d-114">Create a string variable named `HtmlEmailBody` and assign a string of HTML markup to it.</span></span> <span data-ttu-id="a725d-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a725d-115">For example:</span></span>

    ```
    <html><body><h1>Testing</h1><p>This is a <b>test</b> message.</p></body></html>
    ```

3.  <span data-ttu-id="a725d-116">Cree una variable de cadena con nombre `HtmlEmailServer` y asigne el nombre de un servidor SMTP disponible que acepte mensajes salientes anónimos.</span><span class="sxs-lookup"><span data-stu-id="a725d-116">Create a string variable named `HtmlEmailServer` and assign the name of an available SMTP server that accepts anonymous outgoing messages.</span></span>

4.  <span data-ttu-id="a725d-117">Asigne las cinco variables a la propiedad **ReadOnlyVariables** de una nueva tarea Script.</span><span class="sxs-lookup"><span data-stu-id="a725d-117">Assign all five of these variables to the **ReadOnlyVariables** property of a new Script task.</span></span>

5.  <span data-ttu-id="a725d-118">Importe los espacios de nombres `System.Net` y `System.Net.Mail` en su código.</span><span class="sxs-lookup"><span data-stu-id="a725d-118">Import the `System.Net` and `System.Net.Mail` namespaces into your code.</span></span>

 <span data-ttu-id="a725d-119">En el código de ejemplo de este tema se obtiene el nombre del servidor SMTP de una variable de paquete.</span><span class="sxs-lookup"><span data-stu-id="a725d-119">The sample code in this topic obtains the SMTP server name from a package variable.</span></span> <span data-ttu-id="a725d-120">Sin embargo, también podría aprovechar un administrador de conexiones SMTP para encapsular la información de conexión y extraer el nombre del servidor del administrador de conexiones en su código.</span><span class="sxs-lookup"><span data-stu-id="a725d-120">However, you could also take advantage of an SMTP connection manager to encapsulate the connection information, and extract the server name from the connection manager in your code.</span></span> <span data-ttu-id="a725d-121">El método <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> del administrador de conexiones SMTP devuelve a una cadena en el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="a725d-121">The <xref:Microsoft.SqlServer.Dts.ManagedConnections.SMTPConn.AcquireConnection%2A> method of the SMTP connection manager returns a string in the following format:</span></span>

 `SmtpServer=smtphost;UseWindowsAuthentication=False;EnableSsl=False;`

 <span data-ttu-id="a725d-122">Puede usar el método `String.Split` para separar esta lista de argumentos en una matriz de cadenas individuales en cada signo de punto y coma (;) o signo igual (=) y, a continuación, extraer el segundo argumento (subíndice 1) de la matriz como el nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="a725d-122">You can use the `String.Split` method to separate this argument list into an array of individual strings at each semicolon (;) or equal sign (=), and then extract the second argument (subscript 1) from the array as the server name.</span></span>

#### <a name="to-configure-this-script-task-example-with-an-smtp-connection-manager"></a><span data-ttu-id="a725d-123">Para configurar este ejemplo de tarea Script con un administrador de conexiones SMTP</span><span class="sxs-lookup"><span data-stu-id="a725d-123">To configure this Script Task example with an SMTP Connection Manager</span></span>

1.  <span data-ttu-id="a725d-124">Modifique la tarea Script que configuró anteriormente quitando la variable `HtmlEmailServer` de la lista **ReadOnlyVariables**.</span><span class="sxs-lookup"><span data-stu-id="a725d-124">Modify the Script task configured earlier by removing the `HtmlEmailServer` variable from the list of **ReadOnlyVariables**.</span></span>

2.  <span data-ttu-id="a725d-125">Reemplace la línea de código que obtiene el nombre de servidor:</span><span class="sxs-lookup"><span data-stu-id="a725d-125">Replace the line of code that obtains the server name:</span></span>

    ```
    Dim smtpServer As String = _
      Dts.Variables("HtmlEmailServer").Value.ToString
    ```

     <span data-ttu-id="a725d-126">con las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="a725d-126">with the following lines:</span></span>

    ```
    Dim smtpConnectionString As String = _
      DirectCast(Dts.Connections("SMTP Connection Manager").AcquireConnection(Dts.Transaction), String)
    Dim smtpServer As String = _
      smtpConnectionString.Split(New Char() {"="c, ";"c})(1)
    ```

## <a name="code"></a><span data-ttu-id="a725d-127">Código</span><span class="sxs-lookup"><span data-stu-id="a725d-127">Code</span></span>

```vb
Public Sub Main()

  Dim htmlMessageTo As String = _
    Dts.Variables("HtmlEmailTo").Value.ToString
  Dim htmlMessageFrom As String = _
    Dts.Variables("HtmlEmailFrom").Value.ToString
  Dim htmlMessageSubject As String = _
    Dts.Variables("HtmlEmailSubject").Value.ToString
  Dim htmlMessageBody As String = _
    Dts.Variables("HtmlEmailBody").Value.ToString
  Dim smtpServer As String = _
    Dts.Variables("HtmlEmailServer").Value.ToString

  SendMailMessage( _
      htmlMessageTo, htmlMessageFrom, _
      htmlMessageSubject, htmlMessageBody, _
      True, smtpServer)

  Dts.TaskResult = ScriptResults.Success

End Sub

Private Sub SendMailMessage( _
    ByVal SendTo As String, ByVal From As String, _
    ByVal Subject As String, ByVal Body As String, _
    ByVal IsBodyHtml As Boolean, ByVal Server As String)

  Dim htmlMessage As MailMessage
  Dim mySmtpClient As SmtpClient

  htmlMessage = New MailMessage( _
    SendTo, From, Subject, Body)
  htmlMessage.IsBodyHtml = IsBodyHtml

  mySmtpClient = New SmtpClient(Server)
  mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials
  mySmtpClient.Send(htmlMessage)

End Sub
```

```csharp
public void Main()
        {

            string htmlMessageTo = Dts.Variables["HtmlEmailTo"].Value.ToString();
            string htmlMessageFrom = Dts.Variables["HtmlEmailFrom"].Value.ToString();
            string htmlMessageSubject = Dts.Variables["HtmlEmailSubject"].Value.ToString();
            string htmlMessageBody = Dts.Variables["HtmlEmailBody"].Value.ToString();
            string smtpServer = Dts.Variables["HtmlEmailServer"].Value.ToString();

            SendMailMessage(htmlMessageTo, htmlMessageFrom, htmlMessageSubject, htmlMessageBody, true, smtpServer);

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private void SendMailMessage(string SendTo, string From, string Subject, string Body, bool IsBodyHtml, string Server)
        {

            MailMessage htmlMessage;
            SmtpClient mySmtpClient;

            htmlMessage = new MailMessage(SendTo, From, Subject, Body);
            htmlMessage.IsBodyHtml = IsBodyHtml;

            mySmtpClient = new SmtpClient(Server);
            mySmtpClient.Credentials = CredentialCache.DefaultNetworkCredentials;
            mySmtpClient.Send(htmlMessage);

        }
```

<span data-ttu-id="a725d-128">![Integration Services icono (pequeño)](../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a725d-128">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a725d-129">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="a725d-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a725d-130">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="a725d-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a725d-131">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="a725d-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a725d-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a725d-132">See Also</span></span>
 [<span data-ttu-id="a725d-133">Tarea Enviar correo</span><span class="sxs-lookup"><span data-stu-id="a725d-133">Send Mail Task</span></span>](../control-flow/send-mail-task.md)


