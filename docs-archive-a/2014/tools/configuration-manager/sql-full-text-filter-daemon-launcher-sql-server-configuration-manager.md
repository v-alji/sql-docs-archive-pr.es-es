---
title: Selector de demonio de filtro de texto completo de SQL (Administrador de configuración de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d0dc03db-5f76-4558-b041-1ac7b9b5bb16
author: stevestein
ms.author: sstein
ms.openlocfilehash: 45194c893db048151cdb03d33f1419ef42246d69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662451"
---
# <a name="sql-full-text-filter-daemon-launcher-sql-server-configuration-manager"></a><span data-ttu-id="7548b-102">Selector de demonio de filtro de texto completo de SQL (Administrador de configuración de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7548b-102">SQL Full-text Filter Daemon Launcher (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="7548b-103">A partir de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza el servicio del iniciador del demonio de filtro de la búsqueda de texto completo (iniciador de FDHOST) para iniciar el proceso de host de demonio de filtro, que administra las operaciones de filtrado y separación de palabras de la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="7548b-103">Beginning in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], the SQL Full-text Filter Daemon Launcher (FDHOST Launcher) service is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] full-text search to start the filter daemon host process, which handles full-text search filtering and word breaking.</span></span> <span data-ttu-id="7548b-104">Este servicio debe estar ejecutándose para poder utilizar la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="7548b-104">This service must be running to use full-text search.</span></span> <span data-ttu-id="7548b-105">El servicio del iniciador de FDHOST reconoce las instancias y está asociado a una instancia concreta de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7548b-105">The FDHOST Launcher service is an instance-aware service that is associated with a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7548b-106">El servicio del iniciador de FDHOST propaga la información de la cuenta de servicio a cada proceso de host de demonio de filtro iniciado.</span><span class="sxs-lookup"><span data-stu-id="7548b-106">The FDHOST Launcher service propagates the service account information to each filter daemon host process started.</span></span> <span data-ttu-id="7548b-107">Para obtener información sobre los procesos de host de demonio de filtro, vea "Arquitectura de la búsqueda de texto completo" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7548b-107">For information about the filter daemon host processes, see "Full-Text Search Architecture" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
  
