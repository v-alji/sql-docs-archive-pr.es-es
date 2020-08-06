---
title: Administrador de conexiones con SQL Server Compact Edition | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Compact, connection manager
- connections [Integration Services], SQL Server Compact
- connection managers [Integration Services], SQL Server Compact
ms.assetid: ba627d4d-41f4-49fc-a921-f534cde67770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d4feb001cc7c0fd0bd8b6e60d5ab22b33ad2eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750085"
---
# <a name="sql-server-compact-edition-connection-manager"></a><span data-ttu-id="99835-102">Administrador de conexiones con SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="99835-102">SQL Server Compact Edition Connection Manager</span></span>
  <span data-ttu-id="99835-103">Un administrador de conexiones con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact habilita un paquete para establecer conexión con una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="99835-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager enables a package to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="99835-104">El destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] incluye usa este administrador de conexiones para cargar datos en una tabla de una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="99835-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager to load data into a table in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99835-105">En un equipo de 64 bits, necesita ejecutar paquetes que se conecten a los orígenes de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact en modo de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="99835-105">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="99835-106">El proveedor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact que usa [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] para establecer conexión con orígenes de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact solo está disponible en una versión de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="99835-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
## <a name="configuration-the-sql-server-compact-edition-connection-manager"></a><span data-ttu-id="99835-107">Configuración del administrador de conexiones con SQL Server Compact Edition</span><span class="sxs-lookup"><span data-stu-id="99835-107">Configuration the SQL Server Compact Edition Connection Manager</span></span>  
 <span data-ttu-id="99835-108">Cuando se agrega un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Administrador de conexiones de Compact a un paquete, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea un administrador de conexiones que se resuelve en una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conexión de Compact en tiempo de ejecución, establece las propiedades del administrador de conexiones y agrega el administrador de conexiones a la `Connections` colección del paquete.</span><span class="sxs-lookup"><span data-stu-id="99835-108">When you add a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="99835-109">La propiedad `ConnectionManagerType` del administrador de conexiones se establece en `SQLMOBILE`.</span><span class="sxs-lookup"><span data-stu-id="99835-109">The `ConnectionManagerType` property of the connection manager is set to `SQLMOBILE`.</span></span>  
  
 <span data-ttu-id="99835-110">Puede configurar el administrador de conexiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="99835-110">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="99835-111">Proporcionar una cadena de conexión que especifica la ubicación de la base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="99835-111">Provide a connection string that specifies the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
-   <span data-ttu-id="99835-112">Proporcionar una contraseña para una base de datos protegida por contraseña.</span><span class="sxs-lookup"><span data-stu-id="99835-112">Provide a password for a password-protected database.</span></span>  
  
-   <span data-ttu-id="99835-113">Especificar el servidor en el que se va a almacenar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="99835-113">Specify the server on which the database is stored.</span></span>  
  
-   <span data-ttu-id="99835-114">Indicar si la conexión creada desde el administrador de conexiones se conserva en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="99835-114">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="99835-115">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="99835-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="99835-116">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="99835-116">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="99835-117">Editor del administrador de conexiones con SQL Server Compact Edition &#40;página Conexión&#41;</span><span class="sxs-lookup"><span data-stu-id="99835-117">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
-   [<span data-ttu-id="99835-118">Editor del administrador de conexiones con SQL Server Compact Edition &#40;página Todo&#41;</span><span class="sxs-lookup"><span data-stu-id="99835-118">SQL Server Compact Edition Connection Manager Editor &#40;All Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-all-page.md)  
  
 <span data-ttu-id="99835-119">Para obtener información sobre la configuración de un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="99835-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
