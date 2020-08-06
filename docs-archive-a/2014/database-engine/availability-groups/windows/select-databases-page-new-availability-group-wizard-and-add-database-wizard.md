---
title: Página seleccionar bases de datos (Asistente para nuevo grupo de disponibilidad-Asistente para agregar bases de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.adddatabasewizard.selectdatabases.f1
- sql12.swb.newagwizard.selectdatabases.f1
ms.assetid: 929c5e15-d087-438d-b1f2-aa97c5f8bff8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c626b8f0953f18a6dd4661124a09b7f542caeb82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749488"
---
# <a name="select-databases-page-new-availability-group-wizard-add-database-wizard"></a><span data-ttu-id="4a5cb-102">Página seleccionar bases de datos (Asistente para nuevo grupo de disponibilidad-Asistente para agregar bases de datos)</span><span class="sxs-lookup"><span data-stu-id="4a5cb-102">Select Databases Page (New Availability Group Wizard-Add Database Wizard)</span></span>
  <span data-ttu-id="4a5cb-103"> En este tema de Ayuda se describen las opciones de la página **Especificar bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-103">This help topic describes the options of the **Specify Databases** page.</span></span> <span data-ttu-id="4a5cb-104">Esta tema se aplica a [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] y [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4a5cb-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="select-databases-options"></a><a name="PageOptions"></a> <span data-ttu-id="4a5cb-105">Seleccionar opciones de las bases de datos</span><span class="sxs-lookup"><span data-stu-id="4a5cb-105">Select Databases Options</span></span>  
 <span data-ttu-id="4a5cb-106">La cuadrícula **Usar bases de datos en esta instancia de SQL Server** muestra cada base de datos de usuario local.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-106">The **User databases on this instance of SQL Server** grid lists every local user database.</span></span> <span data-ttu-id="4a5cb-107">Estas son sus columnas:</span><span class="sxs-lookup"><span data-stu-id="4a5cb-107">The columns are as follows:</span></span>  
  
 <span data-ttu-id="4a5cb-108">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="4a5cb-108">**Name**</span></span>  
 <span data-ttu-id="4a5cb-109">Muestra el nombre de una base de datos de usuario local.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-109">Displays the name of a local user database.</span></span>  
  
 <span data-ttu-id="4a5cb-110">**Tamaño**</span><span class="sxs-lookup"><span data-stu-id="4a5cb-110">**Size**</span></span>  
 <span data-ttu-id="4a5cb-111">Muestra el tamaño de la base de datos, si el tamaño está disponible para el asistente.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-111">Displays the database size, if the size is available to the wizard.</span></span>  
  
 <span data-ttu-id="4a5cb-112">**Estado**</span><span class="sxs-lookup"><span data-stu-id="4a5cb-112">**Status**</span></span>  
 <span data-ttu-id="4a5cb-113">Muestra un hipervínculo cuyo texto indica si una determinada base de datos cumple los requisitos previos para ser agregada a un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-113">Displays a hyperlink whose text that indicates whether a given database meets the prerequisites for being added to an availability group.</span></span> <span data-ttu-id="4a5cb-114">Si el estado es “**Cumple los requisitos previos**”, puede agregar la base de datos al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-114">If the status is "**Meets prerequisites**" you can add the database to the availability group.</span></span> <span data-ttu-id="4a5cb-115">Si una base de datos no cumple todos los requisitos previos, el hipervínculo **Estado** proporciona una breve explicación de por qué la base de datos no es apta.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-115">If a database does not meet all of the prerequisites, the **Status** hyperlink provides a brief explanation of why the database is ineligible.</span></span> <span data-ttu-id="4a5cb-116">Haga clic en el vínculo para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-116">For more information, click the hyperlink.</span></span>  
  
 <span data-ttu-id="4a5cb-117">Puede dejar el asistente en la página **Seleccionar base de datos** mientras realiza acciones en una base de datos para que se cumpla un requisito previo.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-117">You can leave the wizard on the **Select Database** page while you take action on a database to meet a prerequisite.</span></span> <span data-ttu-id="4a5cb-118">Cuando vuelva a la página **Seleccionar bases de datos** , haga clic en **Actualizar** para actualizar la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-118">When you return to the **Select Databases** page, click **Refresh** to update the grid.</span></span>  
  
 <span data-ttu-id="4a5cb-119">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="4a5cb-119">**Refresh**</span></span>  
 <span data-ttu-id="4a5cb-120">Haga clic para actualizar la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-120">Click to refresh the grid.</span></span> <span data-ttu-id="4a5cb-121">Esto es útil después de realizar acciones en una base de datos para que se cumpla un requisito previo.</span><span class="sxs-lookup"><span data-stu-id="4a5cb-121">This is useful after you take action on a database to meet a prerequisite.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4a5cb-122">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4a5cb-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4a5cb-123">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4a5cb-123">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="4a5cb-124">Usar el Asistente para agregar una base de datos al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="4a5cb-124">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a5cb-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4a5cb-125">See Also</span></span>  
 <span data-ttu-id="4a5cb-126">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4a5cb-126">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="4a5cb-127">Requisitos previos, restricciones y recomendaciones para el SQL Server de &#40;de Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="4a5cb-127">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
  
  
