---
title: Almacenamiento de la administración basada en directivas | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, storage
ms.assetid: d0cbf214-fc2e-4917-8d31-1d71c9ffa61d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0e775d038c5bb4f7a467f2691e374296f1389d84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745714"
---
# <a name="policy-based-management-storage"></a><span data-ttu-id="3934d-102">Almacenamiento de la administración basada en directivas</span><span class="sxs-lookup"><span data-stu-id="3934d-102">Policy-Based Management Storage</span></span>
  <span data-ttu-id="3934d-103">Las directivas se almacenan en la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="3934d-103">Policies are stored in the msdb database.</span></span> <span data-ttu-id="3934d-104">Después de cambiar una directiva o condición, se debería hacer una copia de seguridad de la base de datos msdb.</span><span class="sxs-lookup"><span data-stu-id="3934d-104">After a policy or condition is changed, msdb should be backed up.</span></span> <span data-ttu-id="3934d-105">Para obtener más información, vea [Realizar copias de seguridad y restaurar bases de datos del sistema &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3934d-105">For more information, see [Back Up and Restore of System Databases &#40;SQL Server&#41;](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md).</span></span>  
  
## <a name="storing-policies"></a><span data-ttu-id="3934d-106">Almacenar directivas</span><span class="sxs-lookup"><span data-stu-id="3934d-106">Storing Policies</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="3934d-107">incluye directivas que se pueden utilizar para supervisar una sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3934d-107">includes policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3934d-108">De forma predeterminada, estas directivas no se instalan en el [!INCLUDE[ssDE](../../includes/ssde-md.md)] ; sin embargo, se pueden importar desde la ubicación de instalación predeterminada c:\Archivos de programa (x86) \MICROSOFT SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span><span class="sxs-lookup"><span data-stu-id="3934d-108">By default, these policies are not installed on the [!INCLUDE[ssDE](../../includes/ssde-md.md)]; however, they can be imported from the default installation location of C:\Program Files (x86)\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
 <span data-ttu-id="3934d-109">Puede crear directamente las directivas usando el menú **Archivo/Nuevo** y guardándolas después en un archivo.</span><span class="sxs-lookup"><span data-stu-id="3934d-109">You can directly create policies by using the **File/New** menu, and then saving them to a file.</span></span> <span data-ttu-id="3934d-110">Esto le permite crear directivas cuando no esté conectado a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3934d-110">This enables you to create policies when you are not connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="3934d-111">El historial de las directivas evaluadas en la instancia actual de [!INCLUDE[ssDE](../../includes/ssde-md.md)] se mantiene en las tablas del sistema de msdb.</span><span class="sxs-lookup"><span data-stu-id="3934d-111">Policy history for policies evaluated in the current instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is maintained in msdb system tables.</span></span> <span data-ttu-id="3934d-112">El historial de las directivas aplicadas a otras instancias de [!INCLUDE[ssDE](../../includes/ssde-md.md)] o a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no se conserva.</span><span class="sxs-lookup"><span data-stu-id="3934d-112">Policy history for policies applied to other instances of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] or applied to [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] is not retained.</span></span>  
  
  
