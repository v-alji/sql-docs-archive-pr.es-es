---
title: Permisos necesarios de conexión con SQL Server para el Diseñador CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 80334de2-17c1-43c9-951e-21a9f864e9cb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0815a5d8f1cb66dee0d290a45166ebb395c8efa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663045"
---
# <a name="sql-server-connection-required-permissions-for-the-cdc-designer"></a><span data-ttu-id="0c86d-102">Permisos necesarios de conexión con SQL Server para el Diseñador CDC</span><span class="sxs-lookup"><span data-stu-id="0c86d-102">SQL Server Connection Required Permissions for the CDC Designer</span></span>
  <span data-ttu-id="0c86d-103">La Consola del diseñador CDC necesita información de conexión a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para realizar sus tareas.</span><span class="sxs-lookup"><span data-stu-id="0c86d-103">The CDC Designer Console requires connection information to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to perform its tasks.</span></span> <span data-ttu-id="0c86d-104">En este tema se describe la información que se puede proporcionar en el cuadro de diálogo **Conectar con SQL Server** para configurar la conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c86d-104">This topic describes the information that can be provided in the **Connect to SQL Server** dialog box for setting up the connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0c86d-105">El cuadro de diálogo **Conectar con SQL Server** se abre cuando es necesario, como cuando la información de conexión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no está disponible o si existe la información pero la conexión no tiene los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="0c86d-105">The **Connect to SQL Server** dialog box opens when necessary, such as when the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection information is not available or when the information exists but the connection does not have the required permissions.</span></span>  
  
 <span data-ttu-id="0c86d-106">En la tabla siguiente se describen las diversas tareas en las que se necesita una conexión con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y los permisos que necesita el inicio de sesión o el usuario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c86d-106">The following table describes the various tasks where a connection to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is required and the required permissions from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login/user.</span></span>  
  
|<span data-ttu-id="0c86d-107">Tarea</span><span class="sxs-lookup"><span data-stu-id="0c86d-107">Task</span></span>|<span data-ttu-id="0c86d-108">Permisos mínimos</span><span class="sxs-lookup"><span data-stu-id="0c86d-108">Minimum Permissions</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="0c86d-109">Ver la lista de servicios e instancias CDC usando la instancia asociada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c86d-109">View the list of CDC Services and Instances using the associated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>|<span data-ttu-id="0c86d-110">`db_datareader` en MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="0c86d-110">`db_datareader` role on MSXDBCDC</span></span>|  
|<span data-ttu-id="0c86d-111">Iniciar y detener instancias CDC</span><span class="sxs-lookup"><span data-stu-id="0c86d-111">Start/Stop CDC Instance(s)</span></span>|<span data-ttu-id="0c86d-112">`db_datareader` y `db_datawriter` en MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="0c86d-112">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span>|  
|<span data-ttu-id="0c86d-113">Ver el estado de la instancia CDC.</span><span class="sxs-lookup"><span data-stu-id="0c86d-113">View the CDC Instance status.</span></span>|<span data-ttu-id="0c86d-114">`db_owner` en la base de datos de la instancia CDC</span><span class="sxs-lookup"><span data-stu-id="0c86d-114">`db_owner` role on the CDC Instance database</span></span>|  
|<span data-ttu-id="0c86d-115">Crear una nueva base de datos de instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="0c86d-115">Create a new Oracle CDC Instance database.</span></span>|<span data-ttu-id="0c86d-116">`dbcreator` Rol fijo de servidor</span><span class="sxs-lookup"><span data-stu-id="0c86d-116">`dbcreator` fixed-server role</span></span>|  
|<span data-ttu-id="0c86d-117">Crear una nueva instancia CDC de Oracle.</span><span class="sxs-lookup"><span data-stu-id="0c86d-117">Create a new Oracle CDC Instance.</span></span>|<span data-ttu-id="0c86d-118">`db_datareader` en MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="0c86d-118">`db_datareader` role on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="0c86d-119">`db_owner` en la base de datos CDC creada.</span><span class="sxs-lookup"><span data-stu-id="0c86d-119">`db_owner` role on the CDC database that was created.</span></span>|  
|<span data-ttu-id="0c86d-120">Obtener scripts de implementación.</span><span class="sxs-lookup"><span data-stu-id="0c86d-120">Get deployment scripts.</span></span>|<span data-ttu-id="0c86d-121">`db_datareader` y `db_datawriter` en MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="0c86d-121">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="0c86d-122">`db_owner` en la base de datos CDC relacionada</span><span class="sxs-lookup"><span data-stu-id="0c86d-122">`db_owner` role on the relatedCDC database</span></span>|  
|<span data-ttu-id="0c86d-123">Cambiar la configuración y agregar o quitar instancias de captura.</span><span class="sxs-lookup"><span data-stu-id="0c86d-123">Change configuration and add/remove capture instances.</span></span>|<span data-ttu-id="0c86d-124">`db_datareader` y `db_datawriter` en MSXDBCDC</span><span class="sxs-lookup"><span data-stu-id="0c86d-124">`db_datareader` and `db_datawriter` roles on MSXDBCDC</span></span><br /><br /> <span data-ttu-id="0c86d-125">`db_owner` en la base de datos CDC relacionada</span><span class="sxs-lookup"><span data-stu-id="0c86d-125">`db_owner` role on the related CDC database</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c86d-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c86d-126">See Also</span></span>  
 <span data-ttu-id="0c86d-127">[Obtener acceso a la Consola del diseñador CDC](access-the-cdc-designer-console.md) </span><span class="sxs-lookup"><span data-stu-id="0c86d-127">[Access the CDC Designer Console](access-the-cdc-designer-console.md) </span></span>  
 [<span data-ttu-id="0c86d-128">Conexión de SQL Server para la creación de instancias</span><span class="sxs-lookup"><span data-stu-id="0c86d-128">SQL Server Connection for Instance Creation</span></span>](sql-server-connection-for-instance-creation.md)  
  
  
