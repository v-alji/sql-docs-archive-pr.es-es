---
title: Colocación de los datos y los archivos de registro en unidades independientes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 6cbedc27-4d77-44ad-bed2-c23b628475a7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d3f972ea29322a046c09657e2ed2499655c82aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674763"
---
# <a name="place-data-and-log-files-on-separate-drives"></a><span data-ttu-id="2e732-102">Colocar los datos y los archivos de registro en unidades independientes</span><span class="sxs-lookup"><span data-stu-id="2e732-102">Place Data and Log Files on Separate Drives</span></span>
  <span data-ttu-id="2e732-103">Esta regla comprueba si los datos y archivos de registro se colocan en unidades lógicas independientes.</span><span class="sxs-lookup"><span data-stu-id="2e732-103">This rule checks whether data and log files are placed on separate logical drives.</span></span> <span data-ttu-id="2e732-104">Al colocar tanto los archivos de registro como los datos en el mismo dispositivo, se puede ocasionar la contención por ese dispositivo y provocar un rendimiento escaso.</span><span class="sxs-lookup"><span data-stu-id="2e732-104">Placing both data and log files on the same device can cause contention for that device and result in poor performance.</span></span> <span data-ttu-id="2e732-105">Colocar los archivos en unidades de disco independientes permite que la actividad de E/S tenga lugar al mismo tiempo para los archivos de registro y los datos.</span><span class="sxs-lookup"><span data-stu-id="2e732-105">Placing the files on separate drives allows the I/O activity to occur at the same time for both the data and log files.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="2e732-106">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="2e732-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="2e732-107">Al crear una base de datos nueva, especifique unidades independientes para los datos y el registro.</span><span class="sxs-lookup"><span data-stu-id="2e732-107">When you create a new database, specify separate drives for the data and log.</span></span> <span data-ttu-id="2e732-108">Para mover los archivos una vez creada la base de datos, esta debe ponerse sin conexión.</span><span class="sxs-lookup"><span data-stu-id="2e732-108">To move files after the database is created, the database must be taken offline.</span></span> <span data-ttu-id="2e732-109">Mueva los archivos mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2e732-109">Move the files by using one of the following methods:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e732-110">Esta directiva no puede detectar dispositivos físicos independientes mediante puntos de montaje</span><span class="sxs-lookup"><span data-stu-id="2e732-110">This policy cannot detect separate physical devices through mount points</span></span>  
  
-   <span data-ttu-id="2e732-111">Restaure la base de datos a partir de la copia de seguridad utilizando la instrucción RESTORE DATABASE con la opción WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="2e732-111">Restore the database from backup by using the RESTORE DATABASE statement with the WITH MOVE option.</span></span>  
  
-   <span data-ttu-id="2e732-112">Desasocie y, a continuación, asocie la base de datos especificando ubicaciones independientes para los datos y los dispositivos de registro.</span><span class="sxs-lookup"><span data-stu-id="2e732-112">Detach and then attach the database specifying separate locations for the data and log devices.</span></span>  
  
-   <span data-ttu-id="2e732-113">Especifique una ubicación nueva ejecutando la instrucción ALTER DATABASE con la opción MODIFY FILE y reiniciando a continuación la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e732-113">Specify a new location by running the ALTER DATABASE statement with the MODIFY FILE option, and then restarting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="2e732-114">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="2e732-114">For More Information</span></span>  
 [<span data-ttu-id="2e732-115">Mover archivos de base de datos</span><span class="sxs-lookup"><span data-stu-id="2e732-115">Move Database Files</span></span>](../databases/move-database-files.md)  
  
 [<span data-ttu-id="2e732-116">Mover bases de datos de usuario</span><span class="sxs-lookup"><span data-stu-id="2e732-116">Move User Databases</span></span>](../databases/move-user-databases.md)  
  
 [<span data-ttu-id="2e732-117">Adjuntar y separar bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2e732-117">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="2e732-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e732-118">See Also</span></span>  
 [<span data-ttu-id="2e732-119">Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="2e732-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
