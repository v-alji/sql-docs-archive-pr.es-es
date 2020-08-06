---
title: Novedades de la instalación de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- installing SQL Server, what's new
- SQL Server, what's new
- SQL Server, installing
ms.assetid: c8642a96-3a09-4ec7-a9c3-c539147e6330
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d34085e320cd8ca0b82d382d6d49eaa303086114
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672383"
---
# <a name="what39s-new-in-sql-server-installation"></a><span data-ttu-id="808c0-102">Novedades de la instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="808c0-102">What&#39;s New in SQL Server Installation</span></span>
  <span data-ttu-id="808c0-103">Windows Vista no es un sistema operativo admitido para [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="808c0-103">Windows Vista is not a supported operating system for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="808c0-104">Service Pack 1 permanece como requisito mínimo para los sistemas operativos de [!INCLUDE[win7](../../includes/win7-md.md)] y [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="808c0-104">Service Pack 1 remains as the minimum requirement for [!INCLUDE[win7](../../includes/win7-md.md)] and [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] operating systems.</span></span> <span data-ttu-id="808c0-105">Para obtener más información sobre los requisitos del sistema operativo, vea [requisitos de hardware y software para instalar SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="808c0-105">For more information on operating system requirements, see [Hardware and Software Requirements for Installing SQL Server 2014](hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="808c0-106">La instalación de [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] le solicitará que especifique el directorio para guardar el paquete extraído.</span><span class="sxs-lookup"><span data-stu-id="808c0-106">Installation of [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] will prompt you to specify the directory to save the extracted package.</span></span> <span data-ttu-id="808c0-107">Si no se escribe ninguna ubicación, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] de forma predeterminada será la unidad de sistema del equipo.</span><span class="sxs-lookup"><span data-stu-id="808c0-107">If no location is entered, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] will default to the computer's system drive.</span></span> <span data-ttu-id="808c0-108">Los archivos extraídos se conservarán una vez completada la instalación de [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="808c0-108">The extracted files will remain after [!INCLUDE[ssExpCurrent](../../includes/ssexpcurrent-md.md)] installation is complete.</span></span>  
  
 <span data-ttu-id="808c0-109">En [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], SysPrep se admite para todas las instalaciones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="808c0-109">In [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], SysPrep is supported for all installations of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="808c0-110">SysPrep ahora admite instalaciones de clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="808c0-110">SysPrep now supports failover cluster installations.</span></span> <span data-ttu-id="808c0-111">Para obtener más información, consulte [consideraciones para instalar SQL Server con Sysprep](../../database-engine/install-windows/considerations-for-installing-sql-server-using-sysprep.md) e [instalar SQL Server 2014 con Sysprep](../../database-engine/install-windows/install-sql-server-using-sysprep.md).</span><span class="sxs-lookup"><span data-stu-id="808c0-111">For more information, see [Considerations for Installing SQL Server Using SysPrep](../../database-engine/install-windows/considerations-for-installing-sql-server-using-sysprep.md) and [Install SQL Server 2014 Using SysPrep](../../database-engine/install-windows/install-sql-server-using-sysprep.md).</span></span>  
  
 <span data-ttu-id="808c0-112">Es posible actualizar desde [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], pero no se admite la instalación en paralelo.</span><span class="sxs-lookup"><span data-stu-id="808c0-112">Upgrade from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] is supported, but side-by-side is not supported.</span></span> <span data-ttu-id="808c0-113">Para más información sobre la compatibilidad con [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] en [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], vea [Actualizaciones de ediciones y versiones admitidas](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span><span class="sxs-lookup"><span data-stu-id="808c0-113">For more information about [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] support in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], see [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md).</span></span>  
  
 <span data-ttu-id="808c0-114">A partir de [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], el motor de base de datos de la edición Standard tiene una capacidad de memoria de 128 GB.</span><span class="sxs-lookup"><span data-stu-id="808c0-114">Beginning in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)], the database engine in the Standard edition has a memory capacity of 128 GB.</span></span> <span data-ttu-id="808c0-115">En [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , el motor de base de datos de la edición Standard tenía una capacidad de memoria de 64 GB.</span><span class="sxs-lookup"><span data-stu-id="808c0-115">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the database engine in the Standard edition had a memory capacity of 64 GB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="808c0-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="808c0-116">See Also</span></span>  
 <span data-ttu-id="808c0-117">[Novedades de SQL Server 2014](../what-s-new-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="808c0-117">[What's New in SQL Server 2014](../what-s-new-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="808c0-118">[Especificaciones del producto para SQL Server 2014](../../../2014/getting-started/sql-server-2014-product-specifications.md) </span><span class="sxs-lookup"><span data-stu-id="808c0-118">[Product Specifications for SQL Server 2014](../../../2014/getting-started/sql-server-2014-product-specifications.md) </span></span>  
 <span data-ttu-id="808c0-119">[Planear una instalación de SQL Server](../../../2014/sql-server/install/planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="808c0-119">[Planning a SQL Server Installation](../../../2014/sql-server/install/planning-a-sql-server-installation.md) </span></span>  
 [<span data-ttu-id="808c0-120">Requisitos de hardware y software para instalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="808c0-120">Hardware and Software Requirements for Installing SQL Server 2014</span></span>](hardware-and-software-requirements-for-installing-sql-server.md)  
  
  
