---
title: Administrador de conexiones WMI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], WMI
- connection managers [Integration Services], WMI
- WMI connection manager [Integration Services]
ms.assetid: fbfa4ba7-3d0d-4d6b-94ad-50741a88d03d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f15aefb0ed112f1d5b7bb05421750b6689a11339
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673857"
---
# <a name="wmi-connection-manager"></a><span data-ttu-id="bf938-102">Administrador de conexiones WMI</span><span class="sxs-lookup"><span data-stu-id="bf938-102">WMI Connection Manager</span></span>
  <span data-ttu-id="bf938-103">Un administrador de conexiones WMI habilita un paquete para que use Instrumental de administración de Windows (WMI) para administrar información en un entorno de empresa.</span><span class="sxs-lookup"><span data-stu-id="bf938-103">A WMI connection manager enables a package to use Windows Management Instrumentation (WMI) to manage information in an enterprise environment.</span></span> <span data-ttu-id="bf938-104">La tarea Servicio web que incluye [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] usa un administrador de conexiones WMI.</span><span class="sxs-lookup"><span data-stu-id="bf938-104">The Web Service task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses a WMI connection manager.</span></span>  
  
 <span data-ttu-id="bf938-105">Cuando se agrega un administrador de conexiones WMI a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve en una conexión WMI en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la `Connections` colección del paquete.</span><span class="sxs-lookup"><span data-stu-id="bf938-105">When you add a WMI connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a WMI connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="bf938-106">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `WMI`.</span><span class="sxs-lookup"><span data-stu-id="bf938-106">The `ConnectionManagerType` property of the connection manager is set to `WMI`.</span></span>  
  
## <a name="configuration-of-the-wmi-connection-manager"></a><span data-ttu-id="bf938-107">Configuración del administrador de conexiones WMI</span><span class="sxs-lookup"><span data-stu-id="bf938-107">Configuration of the WMI Connection Manager</span></span>  
 <span data-ttu-id="bf938-108">Puede configurar el administrador de conexiones WMI de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="bf938-108">You can configure a WMI connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="bf938-109">Especificar el nombre de un servidor.</span><span class="sxs-lookup"><span data-stu-id="bf938-109">Specify the name of a server.</span></span>  
  
-   <span data-ttu-id="bf938-110">Especificar un espacio de nombre en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bf938-110">Specify a namespace on the server.</span></span>  
  
-   <span data-ttu-id="bf938-111">Seleccionar el modo de autenticación para conectarse al servidor.</span><span class="sxs-lookup"><span data-stu-id="bf938-111">Select the authentication mode for connecting to the server.</span></span>  
  
 <span data-ttu-id="bf938-112">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="bf938-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="bf938-113">Para obtener información sobre las propiedades que se pueden configurar en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vea [Editor del administrador de conexiones WMI](../wmi-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="bf938-113">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [WMI Connection Manager Editor](../wmi-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="bf938-114">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="bf938-114">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf938-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf938-115">See Also</span></span>  
 <span data-ttu-id="bf938-116">[Tarea servicio Web](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="bf938-116">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="bf938-117">Conexiones de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="bf938-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
