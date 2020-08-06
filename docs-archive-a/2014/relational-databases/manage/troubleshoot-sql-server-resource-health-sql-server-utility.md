---
title: Solucionar problemas de estado de recursos de SQL Server (Utilidad de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 614f07b5-f221-4013-9f8d-22964cf42270
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 182225dd618dd1e9e058c549bdc07818813ba764
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669679"
---
# <a name="troubleshoot-sql-server-resource-health-sql-server-utility"></a><span data-ttu-id="cc116-102">Solucionar problemas de estado de recursos de SQL Server (Utilidad de SQL Server).</span><span class="sxs-lookup"><span data-stu-id="cc116-102">Troubleshoot SQL Server Resource Health (SQL Server Utility)</span></span>
  <span data-ttu-id="cc116-103">La solución de los problemas de mantenimiento de recursos identificados por un UCP de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podría incluir reducir la utilización de la CPU en un equipo o en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o mitigar la sobreutilización de la CPU para una aplicación de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="cc116-103">Troubleshooting resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP might include mitigating overutilized CPU on a computer or on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or mitigating overutilized CPU for a data-tier application.</span></span> <span data-ttu-id="cc116-104">Otros problemas podrían consistir en solucionar el uso excesivo de espacio de archivo para archivos de base de datos o el uso excesivo de espacio en disco asignado en un volumen de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="cc116-104">Other issues might include resolving overutilized file space for database files or resolving overutilization of allocated disk space on a storage volume.</span></span>  
  
 <span data-ttu-id="cc116-105">Tenga en cuenta que si una base de datos se encuentra en estado de "emergencia", el estado de mantenimiento mostrará el espacio de archivo de registro excesivo sobreutilizado.</span><span class="sxs-lookup"><span data-stu-id="cc116-105">Note that if a database is in "emergency" state, the health state will display overutilized log file space.</span></span>  
  
 <span data-ttu-id="cc116-106">Para obtener más información sobre errores de recopilación de datos que generan iconos de estado deshabilitados en la vista de lista de instancias administradas en un UCP, vea [Características y tareas de la utilidad de SQL Server](../../database-engine/troubleshoot-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="cc116-106">For more information about failed data collection resulting in gray status icons in the managed instance list view on a UCP, see [Troubleshoot the SQL Server Utility](../../database-engine/troubleshoot-the-sql-server-utility.md).</span></span> <span data-ttu-id="cc116-107">Para obtener más información para empezar a trabajar con la Utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vea [Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="cc116-107">For more information about getting started with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="cc116-108">Para obtener más información sobre cómo mitigar problemas concretos de mantenimiento de recursos identificados por un UCP de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="cc116-108">For more information about mitigating specific resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP, see the following topics:</span></span>  
  
-   [<span data-ttu-id="cc116-109">Identificar la versión y edición de SQL Server</span><span class="sxs-lookup"><span data-stu-id="cc116-109">How to identify your SQL Server version and edition</span></span>](https://go.microsoft.com/fwlink/?LinkID=178504)  
  
-   [<span data-ttu-id="cc116-110">Solucionar problemas de rendimiento en SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="cc116-110">Troubleshooting Performance Problems in SQL Server 2008</span></span>](https://go.microsoft.com/fwlink/?LinkId=151354)  
  
  
