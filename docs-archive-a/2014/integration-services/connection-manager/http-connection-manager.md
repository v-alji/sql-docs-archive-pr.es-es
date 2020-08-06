---
title: Administrador de conexiones HTTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- HTTP connection manager
- Web site connections [Integration Services]
- connection managers [Integration Services], HTTP
- Web server connections [Integration Services]
- connections [Integration Services], HTTP
ms.assetid: 26b2b3e1-d02c-46ca-8d31-7aef2bbc3c53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10c9f0778faa25aff8db4ad54ecaa8d3ccc5b359
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749396"
---
# <a name="http-connection-manager"></a><span data-ttu-id="218a3-102">HTTP, administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="218a3-102">HTTP Connection Manager</span></span>
  <span data-ttu-id="218a3-103">Una conexión HTTP habilita a un paquete para obtener acceso a un servidor web mediante HTTP para enviar o recibir archivos.</span><span class="sxs-lookup"><span data-stu-id="218a3-103">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="218a3-104">La tarea Servicio web que incluye [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa este administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="218a3-104">The Web Service task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="218a3-105">Cuando agrega un administrador de conexiones HTTP a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve como una conexión HTTP en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la colección `Connections` del paquete.</span><span class="sxs-lookup"><span data-stu-id="218a3-105">When you add an HTTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an HTTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="218a3-106">La `ConnectionManagerType` propiedad del administrador de conexiones se establece en`HTTP.`</span><span class="sxs-lookup"><span data-stu-id="218a3-106">The `ConnectionManagerType` property of the connection manager is set to `HTTP.`</span></span>  
  
 <span data-ttu-id="218a3-107">Puede configurar el administrador de conexiones HTTP de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="218a3-107">You can configure the HTTP connection manager the following ways:</span></span>  
  
-   <span data-ttu-id="218a3-108">Utilizar credenciales.</span><span class="sxs-lookup"><span data-stu-id="218a3-108">Use credentials.</span></span> <span data-ttu-id="218a3-109">Si el administrador de conexiones usa credenciales, sus propiedades incluyen el nombre de usuario, contraseña y dominio.</span><span class="sxs-lookup"><span data-stu-id="218a3-109">If the connection manager uses credentials, its properties include the user name, password, and domain.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="218a3-110">El administrador de conexiones HTTP solo es compatible con la autenticación anónima y la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="218a3-110">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="218a3-111">No es compatible con la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="218a3-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="218a3-112">Utilizar un certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="218a3-112">Use a client certificate.</span></span> <span data-ttu-id="218a3-113">Si el administrador de conexiones usa un certificado de cliente, sus propiedades incluyen el nombre de certificado.</span><span class="sxs-lookup"><span data-stu-id="218a3-113">If the connection manager uses a client certificate, its properties include the certificate name.</span></span>  
  
-   <span data-ttu-id="218a3-114">Proporcionar un tiempo de espera para conectarse al servidor y un tamaño de fragmento para escribir datos.</span><span class="sxs-lookup"><span data-stu-id="218a3-114">Provide a time-out for connecting to the server and a chunk size for writing data.</span></span>  
  
-   <span data-ttu-id="218a3-115">Utilizar un servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="218a3-115">Use a proxy server.</span></span> <span data-ttu-id="218a3-116">El servidor proxy también se puede configurar para usar credenciales y para omitir el servidor proxy y usar direcciones locales en su lugar.</span><span class="sxs-lookup"><span data-stu-id="218a3-116">The proxy server can also be configured to use credentials and to bypass the proxy server and use local addresses instead.</span></span>  
  
## <a name="configuration-of-the-http-connection-manager"></a><span data-ttu-id="218a3-117">Configuración del administrador de conexiones HTTP</span><span class="sxs-lookup"><span data-stu-id="218a3-117">Configuration of the HTTP Connection Manager</span></span>  
 <span data-ttu-id="218a3-118">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="218a3-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="218a3-119">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="218a3-119">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="218a3-120">Editor del administrador de conexiones HTTP &#40;página Servidor&#41;</span><span class="sxs-lookup"><span data-stu-id="218a3-120">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../http-connection-manager-editor-server-page.md)  
  
-   [<span data-ttu-id="218a3-121">Editor del administrador de conexiones HTTP &#40;página Proxy&#41;</span><span class="sxs-lookup"><span data-stu-id="218a3-121">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../http-connection-manager-editor-proxy-page.md)  
  
 <span data-ttu-id="218a3-122">Para más información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="218a3-122">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="218a3-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="218a3-123">See Also</span></span>  
 <span data-ttu-id="218a3-124">[Tarea servicio Web](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="218a3-124">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="218a3-125">Conexiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="218a3-125">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
