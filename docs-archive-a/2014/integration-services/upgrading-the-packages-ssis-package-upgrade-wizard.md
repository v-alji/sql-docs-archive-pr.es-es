---
title: Actualizar los paquetes (Asistente para actualización del paquete SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.upgradingpackage.f1
ms.assetid: cdb842e3-2e59-4ede-b127-be4fde46875c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d13228dabc1566b592733da4afd8ebde3671ee0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669734"
---
# <a name="upgrading-the-packages-ssis-package-upgrade-wizard"></a><span data-ttu-id="12065-102">Actualizar los paquetes (Asistente para actualización del paquete SSIS)</span><span class="sxs-lookup"><span data-stu-id="12065-102">Upgrading the Packages (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="12065-103">Utilice la página **Actualizando los paquetes** para ver e interrumpir el progreso de la actualización de paquetes.</span><span class="sxs-lookup"><span data-stu-id="12065-103">Use the **Upgrading the Packages** page to view the progress of package upgrade and to interrupt the upgrade process.</span></span> <span data-ttu-id="12065-104">El Asistente para actualización del paquete [!INCLUDE[ssIS](../includes/ssis-md.md)] actualiza los paquetes seleccionados uno a uno.</span><span class="sxs-lookup"><span data-stu-id="12065-104">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard upgrades the selected packages one by one.</span></span>  
  
 <span data-ttu-id="12065-105">**Para ver los paquetes actualizados que se guardaron en una base de datos de SQL Server o en el almacén de paquetes**</span><span class="sxs-lookup"><span data-stu-id="12065-105">**To view upgraded packages that were saved to a SQL Server database or to the package store**</span></span>  
  
-   <span data-ttu-id="12065-106">En [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], en el Explorador de objetos, conéctese a la instancia local de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]y, a continuación, expanda el nodo **Paquetes almacenados** para ver los paquetes que se actualizaron.</span><span class="sxs-lookup"><span data-stu-id="12065-106">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], in Object Explorer, connect to the local instance of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], and then expand the **Stored Packages** node to see the packages that were upgraded.</span></span>  
  
 <span data-ttu-id="12065-107">**Para ver los paquetes que se actualizaron a partir herramientas de datos de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="12065-107">**To view upgraded packages that were upgraded from SQL Server Data Tools**</span></span>  
  
-   <span data-ttu-id="12065-108">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en el Explorador de soluciones, abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] y, a continuación, expanda el nodo **Paquetes SSIS** para ver los paquetes actualizados.</span><span class="sxs-lookup"><span data-stu-id="12065-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, and then expand the **SSIS Packages** node to see the upgraded packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="12065-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="12065-109">Options</span></span>  
 <span data-ttu-id="12065-110">**Panel de mensajes**</span><span class="sxs-lookup"><span data-stu-id="12065-110">**Message pane**</span></span>  
 <span data-ttu-id="12065-111">Muestra mensajes de progreso e información de resumen durante el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="12065-111">Displays progress messages and summary information during the upgrade process.</span></span>  
  
 <span data-ttu-id="12065-112">**Acción**</span><span class="sxs-lookup"><span data-stu-id="12065-112">**Action**</span></span>  
 <span data-ttu-id="12065-113">Vea las acciones de la actualización.</span><span class="sxs-lookup"><span data-stu-id="12065-113">View the actions in the upgrade.</span></span>  
  
 <span data-ttu-id="12065-114">**Estado**</span><span class="sxs-lookup"><span data-stu-id="12065-114">**Status**</span></span>  
 <span data-ttu-id="12065-115">Vea el resultado de cada acción.</span><span class="sxs-lookup"><span data-stu-id="12065-115">View the result of each action.</span></span>  
  
 <span data-ttu-id="12065-116">**Message**</span><span class="sxs-lookup"><span data-stu-id="12065-116">**Message**</span></span>  
 <span data-ttu-id="12065-117">Vea los mensajes de error generados por cada acción.</span><span class="sxs-lookup"><span data-stu-id="12065-117">View the error messages that each action generates.</span></span>  
  
 <span data-ttu-id="12065-118">**Detención**</span><span class="sxs-lookup"><span data-stu-id="12065-118">**Stop**</span></span>  
 <span data-ttu-id="12065-119">Detenga la actualización del paquete.</span><span class="sxs-lookup"><span data-stu-id="12065-119">Stop the package upgrade.</span></span>  
  
 <span data-ttu-id="12065-120">**Report**</span><span class="sxs-lookup"><span data-stu-id="12065-120">**Report**</span></span>  
 <span data-ttu-id="12065-121">Seleccione lo que desea hacer con el informe que contiene los resultados de la actualización del paquete:</span><span class="sxs-lookup"><span data-stu-id="12065-121">Select what you want to do with the report that contains the results of the package upgrade:</span></span>  
  
-   <span data-ttu-id="12065-122">Ver el informe en línea.</span><span class="sxs-lookup"><span data-stu-id="12065-122">View the report online.</span></span>  
  
-   <span data-ttu-id="12065-123">Guardar el informe en un archivo.</span><span class="sxs-lookup"><span data-stu-id="12065-123">Save the report to a file.</span></span>  
  
-   <span data-ttu-id="12065-124">Copiar el informe en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="12065-124">Copy the report to the Clipboard</span></span>  
  
-   <span data-ttu-id="12065-125">Enviar el informe como un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="12065-125">Send the report as an e-mail message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12065-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12065-126">See Also</span></span>  
 [<span data-ttu-id="12065-127">Actualizar paquetes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="12065-127">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
