---
title: Usar Correo electrónico de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- e-mail [SMO]
- Database Mail [SMO]
- mail [SMO]
ms.assetid: 7605390f-b485-48cc-8d97-e364a066067b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ceec7417638f53427ed5a62101f2fdb6d7440a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746201"
---
# <a name="using-database-mail"></a><span data-ttu-id="13609-102">Utilizar el correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="13609-102">Using Database Mail</span></span>
  <span data-ttu-id="13609-103">En SMO, el objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> referenciado por la propiedad <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> representa el subsistema del correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="13609-103">In SMO, the Database Mail subsystem is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object that is referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property.</span></span> <span data-ttu-id="13609-104">Mediante el objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> de SMO, puede configurar el subsistema del correo electrónico de base de datos y administrar los perfiles y cuentas de correo.</span><span class="sxs-lookup"><span data-stu-id="13609-104">By using the SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object, you can configure the Database Mail subsystem and manage profiles and mail accounts.</span></span> <span data-ttu-id="13609-105">El objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> de SMO pertenece al objeto `Server`, lo que significa que el ámbito de las cuentas de correo está en el nivel del servidor.</span><span class="sxs-lookup"><span data-stu-id="13609-105">The SMO <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object belongs to the `Server` object, meaning that scope of the mail accounts is at the server level.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="13609-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="13609-106">Examples</span></span>  
 <span data-ttu-id="13609-107">Para utilizar cualquier ejemplo de código que se proporcione, deberá elegir el entorno de programación, la plantilla de programación y el lenguaje de programación con los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="13609-107">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="13609-108">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="13609-108">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
 <span data-ttu-id="13609-109">En el caso de los programas que utilizan [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] correo electrónico de base de datos, debe incluir la `Imports` instrucción para certificar el espacio de nombres mail.</span><span class="sxs-lookup"><span data-stu-id="13609-109">For programs that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Database Mail, you must include the `Imports` statement to qualify the Mail namespace.</span></span> <span data-ttu-id="13609-110">Inserte la instrucción después de las demás instrucciones `Imports`, antes de cualquier declaración de la aplicación, como:</span><span class="sxs-lookup"><span data-stu-id="13609-110">Insert the statement after the other `Imports` statements, before any declarations in the application, such as:</span></span>  
  
 `Imports Microsoft.SqlServer.Management.Smo`  
  
 `Imports Microsoft.SqlServer.Management.Common`  
  
 `Imports Microsoft.SqlServer.Management.Smo.Mail`  
  
## <a name="creating-a-database-mail-account-by-using-visual-basic"></a><span data-ttu-id="13609-111">Crear una cuenta de correo electrónico de base de datos utilizando Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13609-111">Creating a Database Mail Account by Using Visual Basic</span></span>  
 <span data-ttu-id="13609-112">En este ejemplo de código se muestra cómo crear una cuenta de correo electrónico en SMO.</span><span class="sxs-lookup"><span data-stu-id="13609-112">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="13609-113">El Correo electrónico de base de datos está representado por el objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> y está referenciado por la propiedad <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="13609-113">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="13609-114">SMO puede utilizarse para configurar mediante programación el Correo electrónico de base de datos, pero no puede usarse para enviar o administrar el correo electrónico recibido.</span><span class="sxs-lookup"><span data-stu-id="13609-114">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
 <span data-ttu-id="13609-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="13609-115">VB.NET</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMail1](SMO How to#SMO_VBMail1)]  -->  
  
## <a name="creating-a-database-mail-account-by-using-visual-c"></a><span data-ttu-id="13609-116">Crear una cuenta de correo electrónico de base de datos utilizando Visual C#</span><span class="sxs-lookup"><span data-stu-id="13609-116">Creating a Database Mail Account by Using Visual C#</span></span>  
 <span data-ttu-id="13609-117">En este ejemplo de código se muestra cómo crear una cuenta de correo electrónico en SMO.</span><span class="sxs-lookup"><span data-stu-id="13609-117">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="13609-118">El Correo electrónico de base de datos está representado por el objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> y está referenciado por la propiedad <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="13609-118">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="13609-119">SMO puede utilizarse para configurar mediante programación el Correo electrónico de base de datos, pero no puede usarse para enviar o administrar el correo electrónico recibido.</span><span class="sxs-lookup"><span data-stu-id="13609-119">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>  
  
```csharp  
{  
         //Connect to the local, default instance of SQL Server.  
         Server srv = default(Server);   
           srv = new Server();   
           //Define the Database Mail service with a SqlMail object variable   
           //and reference it using the Server Mail property.   
           SqlMail sm;   
           sm = srv.Mail;   
           //Define and create a mail account by supplying the Database Mail  
           //service, name, description, display name, and email address  
           //arguments in the constructor.   
           MailAccount a = default(MailAccount);   
           a = new MailAccount(sm, "AdventureWorks2012 Administrator", "AdventureWorks2012 Automated Mailer", "Mail account for administrative e-mail.", "dba@Adventure-Works.com");   
           a.Create();    
}  
```  
  
## <a name="creating-a-database-mail-account-by-using-powershell"></a><span data-ttu-id="13609-120">Crear una cuenta de correo electrónico de base de datos utilizando PowerShell</span><span class="sxs-lookup"><span data-stu-id="13609-120">Creating a Database Mail Account by Using PowerShell</span></span>  
 <span data-ttu-id="13609-121">En este ejemplo de código se muestra cómo crear una cuenta de correo electrónico en SMO.</span><span class="sxs-lookup"><span data-stu-id="13609-121">This code example shows how to create an e-mail account in SMO.</span></span> <span data-ttu-id="13609-122">El Correo electrónico de base de datos está representado por el objeto <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> y está referenciado por la propiedad <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> del objeto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="13609-122">Database Mail is represented by the <xref:Microsoft.SqlServer.Management.Smo.Mail.SqlMail> object and referenced by the <xref:Microsoft.SqlServer.Management.Smo.Server.Mail%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="13609-123">SMO puede utilizarse para configurar mediante programación el Correo electrónico de base de datos, pero no puede usarse para enviar o administrar el correo electrónico recibido.</span><span class="sxs-lookup"><span data-stu-id="13609-123">SMO can be used to programmatically configure Database Mail, but it cannot be used to send or handle received e-mail.</span></span>
  
```powershell  
#Connect to the local, default instance of SQL Server.  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Define the Database Mail; reference it using the Server Mail property.  
$sm = $srv.Mail  
  
#Define and create a mail account by supplying the Database Mail service,  
#name, description, display name, and email address arguments in the constructor.  
$a = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Mail.MailAccount -ArgumentList $sm, `  
"Adventure Works Administrator", "Adventure Works Automated Mailer",`  
 "Mail account for administrative e-mail.", "dba@Adventure-Works.com"  
$a.Create()  
```  
