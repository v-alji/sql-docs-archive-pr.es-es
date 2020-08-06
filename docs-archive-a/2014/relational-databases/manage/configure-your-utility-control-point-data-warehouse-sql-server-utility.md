---
title: Configurar el almacenamiento de datos del punto de control de la utilidad (utilidad de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: c2c6f050-8cdb-4b8e-ad38-4aae0a949847
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 60b9623b468f2763cf619c325412373e3603f3a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669685"
---
# <a name="configure-your-utility-control-point-data-warehouse-sql-server-utility"></a><span data-ttu-id="3dedc-102">Configurar el almacenamiento de datos del punto de control de la utilidad (utilidad de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3dedc-102">Configure Your Utility Control Point Data Warehouse (SQL Server Utility)</span></span>
  <span data-ttu-id="3dedc-103">Los datos que recopilan las instancias administradas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se almacenan en el almacén de administración de datos de la utilidad (UMDW); el nombre del archivo de este almacén es sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="3dedc-103">Data collected by managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are stored in the utility management data warehouse (UMDW); the UMDW file name is sysutility_mdw.</span></span>  
  
 <span data-ttu-id="3dedc-104">Puede configurar el período para la retención de datos en el almacén de administración de datos de utilidad.</span><span class="sxs-lookup"><span data-stu-id="3dedc-104">You can configure the UMDW data retention period.</span></span> <span data-ttu-id="3dedc-105">Para obtener más información, vea [Administración de la utilidad &#40;Utilidad de SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="3dedc-105">For more information, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="3dedc-106">Los siguientes valores de configuración no se pueden establecer en esta versión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3dedc-106">The following configuration settings are not configurable in this release of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="3dedc-107">Nombre de UMDW: Sysutility_mdw.</span><span class="sxs-lookup"><span data-stu-id="3dedc-107">UMDW name: Sysutility_mdw.</span></span>  
  
-   <span data-ttu-id="3dedc-108">Frecuencia de la carga del conjunto de recopilación: cada 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="3dedc-108">Collection set upload frequency: Every 15 minutes.</span></span>  
  
 <span data-ttu-id="3dedc-109">El directorio de UMDW se puede configurar: \<System drive>:\Archivos de programa\Microsoft SQL Server\MSSQL10_50.<Nombre_de_UCP>\MSSQL\Data\\, donde \<System drive> normalmente es la unidad C:\.</span><span class="sxs-lookup"><span data-stu-id="3dedc-109">The UMDW directory is configurable: \<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<UCP_Name>\MSSQL\Data\\, where \<System drive> is normally the C:\ drive.</span></span> <span data-ttu-id="3dedc-110">El archivo de registro, Sysutility_mdw_\<GUID>_LOG, se encuentra en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="3dedc-110">The log file, Sysutility_mdw_\<GUID>_LOG, is located in the same directory.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3dedc-111">La ubicación del archivo del almacén de administración de datos de utilidad se puede cambiar mediante detach/attach o ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="3dedc-111">The UMDW (sysutility_mdw) file location can be changed using detach/attach or ALTER DATABASE.</span></span> <span data-ttu-id="3dedc-112">Recomendamos el uso de ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="3dedc-112">We recommend the use of ALTER DATABASE.</span></span> <span data-ttu-id="3dedc-113">Para obtener más información, vea [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3dedc-113">For more information see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dedc-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3dedc-114">See Also</span></span>  
 [<span data-ttu-id="3dedc-115">Características y tareas de la utilidad de SQL Server</span><span class="sxs-lookup"><span data-stu-id="3dedc-115">SQL Server Utility Features and Tasks</span></span>](sql-server-utility-features-and-tasks.md)  
  
  
