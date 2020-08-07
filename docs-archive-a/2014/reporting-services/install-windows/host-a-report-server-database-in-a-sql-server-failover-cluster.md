---
title: Hospedar una base de datos del servidor de informes en un clúster de conmutación por error de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 7bd5f019-2857-452f-a023-cc3b9e93aec4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 921ce03fd08e7820266b828d5848f64db1e257ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746175"
---
# <a name="host-a-report-server-database-in-a-sql-server-failover-cluster"></a><span data-ttu-id="5c7b8-102">Hospedar una base de datos del servidor de informes en un clúster de conmutación por error de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c7b8-102">Host a Report Server Database in a SQL Server Failover Cluster</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5c7b8-103">admite el uso de clústeres de conmutación por error para que se puedan utilizar varios discos para una o más instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c7b8-103">provides failover clustering support so that you can use multiple disks for one or more [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances.</span></span> <span data-ttu-id="5c7b8-104">El uso de clústeres de conmutación por error solamente se admite para la base de datos del servidor de informes; no se puede ejecutar el servicio del servidor de informes como parte de un clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="5c7b8-104">Failover clustering is supported only for the report server database; you cannot run the Report Server service as part of a failover cluster.</span></span>  
  
 <span data-ttu-id="5c7b8-105">Para hospedar una base de datos del servidor de informes en un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , el clúster debe estar previamente instalado y configurado.</span><span class="sxs-lookup"><span data-stu-id="5c7b8-105">To host a report server database on a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, the cluster must already be installed and configured.</span></span> <span data-ttu-id="5c7b8-106">A continuación, puede seleccionar el clúster de conmutación por error como nombre del servidor al crear la base de datos del servidor de informes en la página Instalación de base de datos de la herramienta de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c7b8-106">You can then select the failover cluster as the server name when you create the report server database in the Database Setup page of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span>  
  
 <span data-ttu-id="5c7b8-107">Aunque el servicio del servidor de informes no puede participar en un clúster de conmutación por error, se puede instalar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en un equipo que tenga instalado un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c7b8-107">Although the Report Server service cannot participate in a failover cluster, you can install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] on a computer that has a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster installed.</span></span> <span data-ttu-id="5c7b8-108">El servidor de informes se ejecuta de manera independiente del clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="5c7b8-108">The report server runs independently of the failover cluster.</span></span> <span data-ttu-id="5c7b8-109">Si se instala un servidor de informes en un equipo que forma parte de una instancia de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no es obligatorio utilizar el clúster de conmutación por error para la base de datos del servidor de informes; para hospedarla, se puede utilizar otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c7b8-109">If you install a report server on a computer that is part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover instance, you are not required to use the failover cluster for the report server database; you can use a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to host the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c7b8-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c7b8-110">See Also</span></span>  
 <span data-ttu-id="5c7b8-111">[Base de datos del servidor de informes &#40;Modo nativo de SSRS&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="5c7b8-111">[Report Server Database &#40;SSRS Native Mode&#41;](../report-server/report-server-database-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="5c7b8-112">Crear una base de datos del servidor de informes &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5c7b8-112">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
  
  
