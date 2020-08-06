---
title: El directorio virtual tiene un método de autenticación no compatible (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- virtual directories [Reporting Services]
ms.assetid: 216eca6f-9a66-42e1-aa54-dcf99cec9f7d
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 67b1c027b8ed020f65fdea7c093f6d5454f02c5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672401"
---
# <a name="virtual-directory-has-unsupported-authentication-method-upgrade-advisor"></a><span data-ttu-id="a3888-102">El directorio virtual tiene un método de autenticación no admitido (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="a3888-102">Virtual directory has unsupported authentication method (Upgrade Advisor)</span></span>
  <span data-ttu-id="a3888-103">El Asesor de actualizaciones ha detectado un método de autenticación no compatible en el directorio virtual del Administrador de informes o del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a3888-103">Upgrade Advisor detected an unsupported authentication method on the Report Manager or report server virtual directory.</span></span> <span data-ttu-id="a3888-104">Entre los métodos de autenticación no admitidos por la actualización se incluyen: Anónimo, Implícito y .NET Passport.</span><span class="sxs-lookup"><span data-stu-id="a3888-104">Authentication methods that are not supported by upgrade include Anonymous, Digest, and .NET Passport.</span></span>  
  
||  
|-|  
|<span data-ttu-id="a3888-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Modo nativo.</span><span class="sxs-lookup"><span data-stu-id="a3888-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode.</span></span>|  
  
## <a name="component"></a><span data-ttu-id="a3888-106">Componente</span><span class="sxs-lookup"><span data-stu-id="a3888-106">Component</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a3888-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3888-107">Description</span></span>  
 <span data-ttu-id="a3888-108">El programa de instalación no puede actualizar una instalación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que usa uno de los métodos de autenticación siguientes</span><span class="sxs-lookup"><span data-stu-id="a3888-108">Setup cannot upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that uses one of the following authentication methods</span></span>  
  
-   <span data-ttu-id="a3888-109">Anónimo</span><span class="sxs-lookup"><span data-stu-id="a3888-109">Anonymous</span></span>  
  
-   <span data-ttu-id="a3888-110">Digest</span><span class="sxs-lookup"><span data-stu-id="a3888-110">Digest</span></span>  
  
-   <span data-ttu-id="a3888-111">.NET Passport</span><span class="sxs-lookup"><span data-stu-id="a3888-111">.NET Passport</span></span>  
  
 <span data-ttu-id="a3888-112">Para continuar, puede modificar el método de autenticación especificado para los directorios virtuales de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en Internet Information Services (IIS) o puede migrar su instalación.</span><span class="sxs-lookup"><span data-stu-id="a3888-112">To continue, you can either modify the Authentication method that is specified for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories in Internet Information Services (IIS), or you can migrate your installation.</span></span> <span data-ttu-id="a3888-113">Para obtener más información sobre la migración de una instalación, vea los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3888-113">For more information about migrating your installation, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a3888-114">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="a3888-114">Corrective Action</span></span>  
 <span data-ttu-id="a3888-115">Para continuar con la actualización, modifique el método de autenticación en IIS para los directorios virtuales ReportServer y Reports.</span><span class="sxs-lookup"><span data-stu-id="a3888-115">To continue with upgrade, modify the Authentication method in IIS for the ReportServer and Reports virtual directories.</span></span> <span data-ttu-id="a3888-116">Para obtener más información sobre cómo modificar los métodos de autenticación en IIS, vea la documentación de IIS.</span><span class="sxs-lookup"><span data-stu-id="a3888-116">For more information about modifying Authentication methods in IIS, see the IIS documentation.</span></span> <span data-ttu-id="a3888-117">Después de modificar el método de autenticación para los directorios virtuales de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vuelva a ejecutar el Asesor de actualizaciones para confirmar que no hay problemas de actualización.</span><span class="sxs-lookup"><span data-stu-id="a3888-117">After you modify the Authentication method for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] virtual directories, re-run Upgrade Advisor to confirm that there are no other upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3888-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3888-118">See Also</span></span>  
 [<span data-ttu-id="a3888-119">Reporting Services problemas de actualización &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="a3888-119">Reporting Services Upgrade Issues &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/reporting-services-upgrade-issues-upgrade-advisor.md)  
  
  
