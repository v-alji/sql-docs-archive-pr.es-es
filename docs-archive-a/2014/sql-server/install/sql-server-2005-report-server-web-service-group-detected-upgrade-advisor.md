---
title: SQL Server el grupo de servicios web del servidor de informes 2005 detectado (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- deployment [Reporting Services]
ms.assetid: 699d24eb-7756-4b41-9294-ef1a94b2f267
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 70be2b9c4e7abd55daaa752830a73cbe6e222659
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751693"
---
# <a name="sql-server-2005-report-server-web-service-group-detected-upgrade-advisor"></a><span data-ttu-id="b5101-102">Se ha detectado el grupo de servicio web del servidor de informes de SQL Server 2005 (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="b5101-102">SQL Server 2005 Report Server Web Service group detected (Upgrade Advisor)</span></span>
  <span data-ttu-id="b5101-103">El asesor de actualizaciones ha detectado que la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instancia está asociada a un [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] grupo de servicios web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b5101-103">Upgrade Advisor detected that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is associated with a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span>  
  
||  
|-|  
|<span data-ttu-id="b5101-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="b5101-104">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="b5101-105">Componente</span><span class="sxs-lookup"><span data-stu-id="b5101-105">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b5101-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5101-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="b5101-107">no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] utiliza el [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Grupo de servicios web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b5101-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not use the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="b5101-108">Al actualizar de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], este grupo de servicio se elimina y las listas de control de acceso (ACL) personalizadas para este grupo o los usuarios que pertenecen al grupo no se conservan durante la actualización.</span><span class="sxs-lookup"><span data-stu-id="b5101-108">When you upgrade from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], this service group is deleted and custom Access Control Lists (ACLs) for this group or users who belong to the group are not retained during the upgrade.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b5101-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="b5101-109">Corrective Action</span></span>  
 <span data-ttu-id="b5101-110">Antes de ejecutar la actualización, realice una copia de seguridad de las ACL o usuarios personalizados que pertenecen al grupo de servicio web del servidor de informes de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5101-110">Before you upgrade, back up any custom ACLs or users who belong to the [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Report Server Web service group.</span></span> <span data-ttu-id="b5101-111">Para ello, puede usar la herramienta de línea de comandos **Icacls.exe** en [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2 y versiones posteriores, o la herramienta de línea de comandos Cacls.exe en los sistemas operativos Windows anteriores a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span><span class="sxs-lookup"><span data-stu-id="b5101-111">To do this, you can use the **Icacls.exe** command-line tool in [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2 and later or the Cacls.exe command-line tool in Windows operating systems prior to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] SP2.</span></span> <span data-ttu-id="b5101-112">Para obtener más información sobre la sintaxis de estas herramientas, vea la documentación del producto de Windows.</span><span class="sxs-lookup"><span data-stu-id="b5101-112">For more information about the syntax for these tools, see the Windows product documentation.</span></span> <span data-ttu-id="b5101-113">Una vez completado correctamente el programa de instalación, aplique las ACL o los usuarios personalizados al grupo de Windows Servidor de informes de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] para la instancia del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="b5101-113">After setup successfully completes, apply the custom ACLs or users to the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group for your report server instance.</span></span> <span data-ttu-id="b5101-114">El [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] grupo de Windows del servidor de informes adopta la forma de SQLServerReportServerUser $ \<*computer_name*> $ \<*instance_name*> .</span><span class="sxs-lookup"><span data-stu-id="b5101-114">The [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Server Windows group takes the form of SQLServerReportServerUser$\<*computer_name*>$\<*instance_name*>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5101-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5101-115">See Also</span></span>  
 [<span data-ttu-id="b5101-116">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="b5101-116">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
