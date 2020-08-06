---
title: Consideraciones para ejecutar conjuntos de recopilación de la utilidad y que no sean de la utilidad en la misma instancia de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ca7ee9b3-ef9a-4ba4-83d0-9ee9f80dab27
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67df2d65cc9da4026377e77c152c0d78f3749932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674106"
---
# <a name="considerations-for-running-utility-and-non-utility-collection-sets-on-the-same-instance-of-sql-server"></a><span data-ttu-id="4b02f-102">Consideraciones para ejecutar conjuntos de recopilación de la utilidad y que no sean de la utilidad en la misma instancia de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b02f-102">Considerations for Running Utility and non-Utility Collection Sets on the Same Instance of SQL Server</span></span>
  <span data-ttu-id="4b02f-103">El conjunto de recopilación de la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se admite en paralelo con conjuntos de recopilación que no sean de la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b02f-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection set is supported side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="4b02f-104">Es decir, otros conjuntos de recopilación pueden supervisar una instancia administrada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mientras pertenezca a una utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b02f-104">That is, a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be monitored by other collection sets while it is a member of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="4b02f-105">Sin embargo, debe deshabilitar la funcionalidad de recopilación de datos de la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mientras la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se esté inscribiendo en la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b02f-105">However, you must disable non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection functionality while the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is being enrolled into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
 <span data-ttu-id="4b02f-106">Una vez se haya inscrito la instancia con el UCP, puede reiniciar los conjuntos de recopilación de la utilidad que no sea de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b02f-106">After the instance is enrolled with the UCP, you can restart non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets.</span></span> <span data-ttu-id="4b02f-107">Sin embargo, debe tener en cuenta que todos los conjuntos de recopilación en la instancia administrada cargarán sus datos en el almacén de administración de datos de la utilidad (UMDW); el nombre del archivo de datos de la utilidad es sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="4b02f-107">Note, however, that all collection sets on the managed instance will upload their data to the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="4b02f-108">Para ejecutar los conjuntos de recopilación de la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en paralelo con conjuntos de recopilación que no sean de la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , tenga en cuenta los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="4b02f-108">To run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets side-by-side with non- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility collection sets, consider the following points:</span></span>  
  
-   <span data-ttu-id="4b02f-109">Se admiten conjuntos de recopilación en paralelo.</span><span class="sxs-lookup"><span data-stu-id="4b02f-109">Side-by-side collection sets are supported.</span></span>  
  
-   <span data-ttu-id="4b02f-110">Debe deshabilitar los recopiladores de datos existentes mientras inscriba instancias en la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b02f-110">You must disable existing data collectors while enrolling instances into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
-   <span data-ttu-id="4b02f-111">Para pasar los requisitos de validación, debe ejecutar los siguientes procedimientos almacenados en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de crear un UCP, y en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antes de inscribirla en la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4b02f-111">To pass validation requirements, you must run the following stored procedures on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you create a UCP, and on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before you enroll it into the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility:</span></span>  
  
    ```  
    exec msdb.dbo.sp_syscollector_set_warehouse_database_name NULL  
    exec msdb.dbo.sp_syscollector_set_warehouse_instance_name NULL  
    ```  
  
     <span data-ttu-id="4b02f-112">Si no ejecuta estos procedimientos almacenados antes de iniciar el Asistente para crear UCP y el Asistente para agregar instancia administrada, se producirá un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="4b02f-112">If you do not run these stored procedures before you launch the Create UCP Wizard or Add Managed Instance Wizard, the operation will fail.</span></span>  
  
-   <span data-ttu-id="4b02f-113">Debe utilizar el almacén de administración de datos de la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (sysutility_mdw) para todos los conjuntos de recopilación en una instancia administrada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b02f-113">You must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility UMDW (sysutility_mdw) for all collection sets on a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b02f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b02f-114">See Also</span></span>  
 <span data-ttu-id="4b02f-115">[Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="4b02f-115">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="4b02f-116">Configurar el almacenamiento de datos del punto de control de la utilidad &#40;Utilidad de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4b02f-116">Configure Your Utility Control Point Data Warehouse &#40;SQL Server Utility&#41;</span></span>](configure-your-utility-control-point-data-warehouse-sql-server-utility.md)  
  
  
