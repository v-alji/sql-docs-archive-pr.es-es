---
title: Administrador de conexiones SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMO
- SMO connection manager
- connection managers [Integration Services], SMO
ms.assetid: d273f1fb-a6a8-4f2f-a5ff-55c2e3de4723
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 988eef214608399bc3ec483d9976c2f5d52acb2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750089"
---
# <a name="smo-connection-manager"></a><span data-ttu-id="4dcb0-102">SMO, administrador de conexiones</span><span class="sxs-lookup"><span data-stu-id="4dcb0-102">SMO Connection Manager</span></span>
  <span data-ttu-id="4dcb0-103">Un administrador de conexiones SMO permite a un paquete conectarse a un servidor de Objeto de administración de SQL (SMO).</span><span class="sxs-lookup"><span data-stu-id="4dcb0-103">An SMO connection manager enables a package to connect to a SQL Management Object (SMO) server.</span></span> <span data-ttu-id="4dcb0-104">Las tareas de transferencia que incluye [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usan un administrador de conexiones SMO.</span><span class="sxs-lookup"><span data-stu-id="4dcb0-104">The transfer tasks that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes use an SMO connection manager.</span></span> <span data-ttu-id="4dcb0-105">Por ejemplo, la tarea Transferir inicios de sesión que transfiere inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa un administrador de conexiones SMO.</span><span class="sxs-lookup"><span data-stu-id="4dcb0-105">For example, the Transfer Logins task that transfers [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins uses an SMO connection manager.</span></span>  
  
 <span data-ttu-id="4dcb0-106">Cuando agrega un administrador de conexiones SMO a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve como una conexión SMO en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la colección `Connections` del paquete.</span><span class="sxs-lookup"><span data-stu-id="4dcb0-106">When you add an SMO connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMO connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="4dcb0-107">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `SMOServer`.</span><span class="sxs-lookup"><span data-stu-id="4dcb0-107">The `ConnectionManagerType` property of the connection manager is set to `SMOServer`.</span></span>  
  
 <span data-ttu-id="4dcb0-108">Puede configurar el administrador de conexiones SMO de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="4dcb0-108">You can configure an SMO connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="4dcb0-109">Especificar el nombre de un servidor en el que está instalado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4dcb0-109">Specify the name of a server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="4dcb0-110">Seleccionar el modo de autenticación para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="4dcb0-110">Select the authentication mode for connecting to the server.</span></span>  
  
## <a name="configuration-of-the-smo-connection-manager"></a><span data-ttu-id="4dcb0-111">Configuración del administrador de conexiones SMO</span><span class="sxs-lookup"><span data-stu-id="4dcb0-111">Configuration of the SMO Connection Manager</span></span>  
 <span data-ttu-id="4dcb0-112">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="4dcb0-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4dcb0-113">Para más información sobre las propiedades que puede configurar en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Editor del administrador de conexiones SMO](../smo-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4dcb0-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMO Connection Manager Editor](../smo-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="4dcb0-114">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="4dcb0-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dcb0-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4dcb0-115">See Also</span></span>  
 [<span data-ttu-id="4dcb0-116">Conexiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4dcb0-116">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
