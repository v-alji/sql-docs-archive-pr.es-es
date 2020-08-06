---
title: Parámetros de Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, parameters
ms.assetid: b1bb3ea3-8097-4e76-b9c2-78a0f46a23bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 76a5ebe7018fdc58f02a4d2454d40f172c752c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749625"
---
# <a name="integration-services-parameters"></a><span data-ttu-id="9eccd-102">Parámetros de Integration Services</span><span class="sxs-lookup"><span data-stu-id="9eccd-102">Integration Services Parameters</span></span>
  <span data-ttu-id="9eccd-103">Para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , puede decidir analizar [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] paquetes en el equipo o [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] empaquetar archivos en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="9eccd-103">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you can decide to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer, or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package files in the file system.</span></span> <span data-ttu-id="9eccd-104">Si analiza los archivos en el sistema de archivos, proporcione una ruta de acceso a la carpeta que contiene los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9eccd-104">If you analyze files in the file system, provide a path to the folder that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9eccd-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="9eccd-105">Options</span></span>  
 <span data-ttu-id="9eccd-106">**Analizar paquetes SSIS en el equipo**</span><span class="sxs-lookup"><span data-stu-id="9eccd-106">**Analyze SSIS packages on Computer**</span></span>  
 <span data-ttu-id="9eccd-107">Seleccione esta opción para analizar los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9eccd-107">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer.</span></span> <span data-ttu-id="9eccd-108">Esta opción está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9eccd-108">By default, this option is selected.</span></span>  
  
 <span data-ttu-id="9eccd-109">**Analizar archivos de paquete SSIS**</span><span class="sxs-lookup"><span data-stu-id="9eccd-109">**Analyze SSIS package files**</span></span>  
 <span data-ttu-id="9eccd-110">Seleccione esta opción para analizar los paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="9eccd-110">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages in the file system.</span></span>  
  
 <span data-ttu-id="9eccd-111">**Ruta de acceso a los paquetes de SSIS**</span><span class="sxs-lookup"><span data-stu-id="9eccd-111">**Path to SSIS packages**</span></span>  
 <span data-ttu-id="9eccd-112">Busque una ruta de acceso UNC o local que contenga sus paquetes de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9eccd-112">Locate a UNC or local path that holds your [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="9eccd-113">No es necesario que incluya nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="9eccd-113">You do not have to include file names.</span></span> <span data-ttu-id="9eccd-114">Si no se puede tener acceso a la ruta de acceso especificada, no puede hacer clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9eccd-114">If the path you have entered cannot be accessed, you cannot click **Next**.</span></span> <span data-ttu-id="9eccd-115">De forma predeterminada, la ruta de acceso está en blanco.</span><span class="sxs-lookup"><span data-stu-id="9eccd-115">By default, the path is blank.</span></span> <span data-ttu-id="9eccd-116">Este campo solo está habilitado cuando se selecciona **analizar archivos de paquete SSIS**.</span><span class="sxs-lookup"><span data-stu-id="9eccd-116">This field is enabled only when you select **Analyze SSIS package files**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eccd-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9eccd-117">See Also</span></span>  
 <span data-ttu-id="9eccd-118">[Trabajar con el asesor de actualizaciones](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="9eccd-118">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="9eccd-119">Referencia de la interfaz de usuario del Asesor de actualizaciones</span><span class="sxs-lookup"><span data-stu-id="9eccd-119">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
