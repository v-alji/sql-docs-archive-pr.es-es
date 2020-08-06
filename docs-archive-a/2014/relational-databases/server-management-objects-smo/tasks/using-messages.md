---
title: Usar mensajes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- messages [SMO]
ms.assetid: 4037a866-4826-4c1f-890c-e7e3658adf13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53b2e0fa4be2dfd53cdd8f4f0cacb7ae0bd79edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676432"
---
# <a name="using-messages"></a><span data-ttu-id="221ff-102">Usar mensajes</span><span class="sxs-lookup"><span data-stu-id="221ff-102">Using Messages</span></span>
  <span data-ttu-id="221ff-103">En SMO, el objeto <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> que pertenece al objeto `Server` representa los mensajes del sistema.</span><span class="sxs-lookup"><span data-stu-id="221ff-103">In SMO, system messages are represented by the <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> object that belongs to the `Server` object.</span></span> <span data-ttu-id="221ff-104">Dado que los mensajes del sistema no se pueden modificar, las propiedades del objeto `SystemMessage` son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="221ff-104">Because the system messages cannot be modified, `SystemMessage` object properties are read-only.</span></span>  
  
 <span data-ttu-id="221ff-105">El objeto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection> representa los mensajes definidos por el usuario mediante programación en SMO.</span><span class="sxs-lookup"><span data-stu-id="221ff-105">User-defined messages are represented programmatically in SMO by the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection> object.</span></span> <span data-ttu-id="221ff-106">Los mensajes definidos por el usuario existentes se pueden detectar realizando una iteración en la colección.</span><span class="sxs-lookup"><span data-stu-id="221ff-106">Existing user-defined messages can be discovered by iterating through the collection.</span></span> <span data-ttu-id="221ff-107">Los nuevos mensajes definidos por el usuario se pueden crear creando instancias de un nuevo objeto `UserDefinedMessage` y estableciendo las propiedades adecuadas.</span><span class="sxs-lookup"><span data-stu-id="221ff-107">New user-defined messages can be created by instantiating a new `UserDefinedMessage` object and setting the appropriate properties.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="221ff-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="221ff-108">Examples</span></span>  
 <span data-ttu-id="221ff-109">Para los siguientes ejemplos de código, deberá seleccionar el entorno de programación, la plantilla de programación y el lenguaje de programación en los que crear su aplicación.</span><span class="sxs-lookup"><span data-stu-id="221ff-109">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="221ff-110">Para obtener más información, vea [crear un proyecto de Visual Basic SMO en Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) y [crear un proyecto de Visual C&#35; SMO en Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="221ff-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="finding-a-particular-system-message-in-visual-basic"></a><span data-ttu-id="221ff-111">Buscar un mensaje del sistema determinado en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="221ff-111">Finding a Particular System Message in Visual Basic</span></span>  
 <span data-ttu-id="221ff-112">En el ejemplo de código se muestra cómo identificar un mensaje del sistema por número de identificador y cómo mostrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="221ff-112">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMessages1](SMO How to#SMO_VBMessages1)]  -->  
  
## <a name="finding-a-particular-system-message-in-visual-c"></a><span data-ttu-id="221ff-113">Buscar un mensaje del sistema determinado en Visual C#</span><span class="sxs-lookup"><span data-stu-id="221ff-113">Finding a Particular System Message in Visual C#</span></span>  
 <span data-ttu-id="221ff-114">En el ejemplo de código se muestra cómo identificar un mensaje del sistema por número de identificador y cómo mostrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="221ff-114">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Reference an existing system message using the   
            //ItemByIdAndLanguage method.   
            SystemMessage msg = default(SystemMessage);  
            msg = srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
        }  
```  
  
## <a name="finding-a-particular-system-message-in-powershell"></a><span data-ttu-id="221ff-115">Buscar un mensaje del sistema determinado en PowerShell</span><span class="sxs-lookup"><span data-stu-id="221ff-115">Finding a Particular System Message in PowerShell</span></span>  
 <span data-ttu-id="221ff-116">En el ejemplo de código se muestra cómo identificar un mensaje del sistema por número de identificador y cómo mostrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="221ff-116">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get the message 14126 in US English and display it  
$msg = $srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english")  
$msg.ID.ToString() + " "+ $msg.Text  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-basic"></a><span data-ttu-id="221ff-117">Agregar un nuevo mensaje definido por el usuario en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="221ff-117">Adding a New User-Defined Message in Visual Basic</span></span>  
 <span data-ttu-id="221ff-118">En el ejemplo de código se muestra cómo crear un mensaje definido por el usuario con un identificador mayor que 50000.</span><span class="sxs-lookup"><span data-stu-id="221ff-118">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```vb
Dim mysrv As Server  
mysrv = New Server  
Dim udm As UserDefinedMessage  
udm = New UserDefinedMessage(mysrv, 50003, "us_english", 16, "Test message")  
udm.Create()  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-c"></a><span data-ttu-id="221ff-119">Agregar un nuevo mensaje definido por el usuario en Visual C#</span><span class="sxs-lookup"><span data-stu-id="221ff-119">Adding a New User-Defined Message in Visual C#</span></span>  
 <span data-ttu-id="221ff-120">En el ejemplo de código se muestra cómo crear un mensaje definido por el usuario con un identificador mayor que 50000.</span><span class="sxs-lookup"><span data-stu-id="221ff-120">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```csharp
{
            Server mysrv = new Server();  
  
            UserDefinedMessage udm = new UserDefinedMessage(mysrv, 50030, "us_english",16, "Test message");  
            udm.Create();  
             UserDefinedMessage  msg = mysrv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
  
        }  
```  
  
## <a name="adding-a-new-user-defined-message-in-powershell"></a><span data-ttu-id="221ff-121">Agregar un nuevo mensaje definido por el usuario en PowerShell</span><span class="sxs-lookup"><span data-stu-id="221ff-121">Adding a New User-Defined Message in PowerShell</span></span>
 <span data-ttu-id="221ff-122">En el ejemplo de código se muestra cómo crear un mensaje definido por el usuario con un identificador mayor que 50000.</span><span class="sxs-lookup"><span data-stu-id="221ff-122">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a new message
$udm = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedMessage -ArgumentList `  
$srv, 50030, "us_english", 16, "Test message"  
$udm.Create()  
$msg = $srv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
$msg  
```  
