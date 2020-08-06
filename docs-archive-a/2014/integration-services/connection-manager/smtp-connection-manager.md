---
title: Administrador de conexiones SMTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMTP
- SMTP connection manager [Integration Services]
- connection managers [Integration Services], SMTP
ms.assetid: 3795d442-714b-4bbb-9acd-75bf277a468a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f3c090ab672790901baae01ae86f8d22e008b4ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750086"
---
# <a name="smtp-connection-manager"></a><span data-ttu-id="5fdb6-102">Administrador de conexiones SMTP</span><span class="sxs-lookup"><span data-stu-id="5fdb6-102">SMTP Connection Manager</span></span>
  <span data-ttu-id="5fdb6-103">Un administrador de conexiones SMTP permite a un paquete conectarse a un servidor de Protocolo simple de transferencia de correo (SMTP).</span><span class="sxs-lookup"><span data-stu-id="5fdb6-103">An SMTP connection manager enables a package to connect to a Simple Mail Transfer Protocol (SMTP) server.</span></span> <span data-ttu-id="5fdb6-104">La tarea Enviar correo que incluye [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa un administrador de conexiones SMTP.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-104">The Send Mail task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an SMTP connection manager.</span></span>  
  
 <span data-ttu-id="5fdb6-105">Si utiliza Microsoft Exchange como servidor SMTP, es posible que necesite configurar el administrador de conexiones SMTP para que utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-105">When using Microsoft Exchange as the SMTP server, you may need to configure the SMTP connection manager to use Windows Authentication.</span></span> <span data-ttu-id="5fdb6-106">Es posible que los servidores Exchange estén configurados para no permitir conexiones SMTP no autenticadas.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-106">Exchange servers may be configured to not allow unauthenticated SMTP connections.</span></span>  
  
## <a name="configuration-the-smtp-connection-manager"></a><span data-ttu-id="5fdb6-107">Configuración del administrador de conexiones SMTP</span><span class="sxs-lookup"><span data-stu-id="5fdb6-107">Configuration the SMTP Connection Manager</span></span>  
 <span data-ttu-id="5fdb6-108">Cuando agrega un administrador de conexiones SMTP a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve como una conexión SMTP en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la colección `Connections` del paquete.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-108">When you add an SMTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="5fdb6-109">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `SMTP`.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-109">The `ConnectionManagerType` property of the connection manager is set to `SMTP`.</span></span>  
  
 <span data-ttu-id="5fdb6-110">Puede configurar el administrador de conexiones SMTP de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="5fdb6-110">You can configure an SMTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="5fdb6-111">Proporcionar una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-111">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="5fdb6-112">Especificar el nombre de un servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-112">Specify the name of an SMTP server.</span></span>  
  
-   <span data-ttu-id="5fdb6-113">Especificar el método de autenticación que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-113">Specify the authentication method to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5fdb6-114">El administrador de conexiones SMTP solo es compatible con la autenticación anónima y la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-114">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="5fdb6-115">No admite la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-115">It does not support basic authentication.</span></span>  
  
-   <span data-ttu-id="5fdb6-116">Especificar si la comunicación se cifrará mediante SSL (Capa de sockets seguros) al enviar mensajes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-116">Specify whether to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
 <span data-ttu-id="5fdb6-117">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="5fdb6-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="5fdb6-118">Para obtener más información sobre las propiedades que puede configurar en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Editor del administrador de conexiones SMTP](../smtp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="5fdb6-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMTP Connection Manager Editor](../smtp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="5fdb6-119">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="5fdb6-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
