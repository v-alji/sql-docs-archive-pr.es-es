---
title: Página validación (asistentes para grupos de disponibilidad AlwaysOn) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.newagwizard.validation.f1
- sql12.swb.addreplicawizard.validation.f1
- sql12.swb.adddatabasewizard.validation.f1
helpviewer_keywords:
- ', listeners'
ms.assetid: c8971556-240c-491a-bc86-9cc72f71a3dd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f2010074a357932f8af7358a05ee6ed16f5c0881
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663128"
---
# <a name="validation-page-alwayson-availability-group-wizards"></a><span data-ttu-id="9b534-102">Página Validación (asistentes para grupos de disponibilidad AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="9b534-102">Validation Page (AlwaysOn Availability Group Wizards)</span></span>
  <span data-ttu-id="9b534-103">En este tema de Ayuda se describen las opciones de la página **Validación** .</span><span class="sxs-lookup"><span data-stu-id="9b534-103">This help topic describes the options of the **Validation** page.</span></span> <span data-ttu-id="9b534-104">Esta tema se aplica a [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)]y [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b534-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)], [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)], and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="9b534-105">Utilice esta página para validar que el entorno admite todas las opciones de configuración realizada en las páginas anteriores del asistente.</span><span class="sxs-lookup"><span data-stu-id="9b534-105">Use this page to validate that your environment supports all the configuration choices you made on previous pages of the wizard.</span></span>  
  
##  <a name="validation-page-options"></a><a name="PageOptions"></a><span data-ttu-id="9b534-106">Opciones de la página validación</span><span class="sxs-lookup"><span data-stu-id="9b534-106">Validation Page Options</span></span>  
 <span data-ttu-id="9b534-107">**Resultados de la validación de grupos de disponibilidad.**</span><span class="sxs-lookup"><span data-stu-id="9b534-107">**Results of availability group validation.**</span></span>  
 <span data-ttu-id="9b534-108">Esta cuadrícula muestra los resultados de cada paso de la validación completado.</span><span class="sxs-lookup"><span data-stu-id="9b534-108">This grid displays the results of each completed validation step.</span></span> <span data-ttu-id="9b534-109">Las columnas de la cuadrícula son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b534-109">The grid columns are as follows:</span></span>  
  
 <span data-ttu-id="9b534-110">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="9b534-110">**Name**</span></span>  
 <span data-ttu-id="9b534-111">Muestra una frase que describe un paso concreto.</span><span class="sxs-lookup"><span data-stu-id="9b534-111">Displays a phrase that describes a specific step.</span></span>  
  
 <span data-ttu-id="9b534-112">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="9b534-112">**Result**</span></span>  
 <span data-ttu-id="9b534-113">Muestra uno de los siguientes texto de hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="9b534-113">Displays one of the following hyperlink texts.</span></span> <span data-ttu-id="9b534-114">Para obtener más información sobre el resultado del paso de la validación determinado, haga clic en el hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="9b534-114">For more information about the result of given validation step, click the hyperlink.</span></span>  
  
|<span data-ttu-id="9b534-115">Resultado</span><span class="sxs-lookup"><span data-stu-id="9b534-115">Result</span></span>|<span data-ttu-id="9b534-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b534-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="9b534-117">**Error**</span><span class="sxs-lookup"><span data-stu-id="9b534-117">**Error**</span></span>|<span data-ttu-id="9b534-118">Indica que se produjo un error en el paso de la validación.</span><span class="sxs-lookup"><span data-stu-id="9b534-118">Indicates that the validation step failed.</span></span> <span data-ttu-id="9b534-119">Haga clic en el vínculo para ver el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="9b534-119">Click the link to view the error message.</span></span>|  
|<span data-ttu-id="9b534-120">**Omitido**</span><span class="sxs-lookup"><span data-stu-id="9b534-120">**Skipped**</span></span>|<span data-ttu-id="9b534-121">Indica que el paso de la validación se omite porque no lo requieren las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="9b534-121">Indicates that the validation step was skipped because it is not required by your selections.</span></span> <span data-ttu-id="9b534-122">Haga clic en el vínculo para ver el motivo por el que un paso se ha omitido.</span><span class="sxs-lookup"><span data-stu-id="9b534-122">Click the link to view the reason that a step was skipped.</span></span>|  
|<span data-ttu-id="9b534-123">**Success**</span><span class="sxs-lookup"><span data-stu-id="9b534-123">**Success**</span></span>|<span data-ttu-id="9b534-124">Indica que el paso de la validación se completó correctamente</span><span class="sxs-lookup"><span data-stu-id="9b534-124">Indicates that the validation step completed successfully</span></span>|  
|<span data-ttu-id="9b534-125">**Advertencia**</span><span class="sxs-lookup"><span data-stu-id="9b534-125">**Warning**</span></span>|<span data-ttu-id="9b534-126">Indica un problema potencial con la configuración del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="9b534-126">Indicates a potential issue with the availability group configuration.</span></span>  <span data-ttu-id="9b534-127">Haga clic en el vínculo para ver el mensaje de advertencia.</span><span class="sxs-lookup"><span data-stu-id="9b534-127">Click the link to view the warning message.</span></span>|  
  
 <span data-ttu-id="9b534-128">**Volver a ejecutar la validación**</span><span class="sxs-lookup"><span data-stu-id="9b534-128">**Re-run Validation**</span></span>  
 <span data-ttu-id="9b534-129">Haga clic para repetir los pasos de la validación si realiza un cambio fuera del asistente en respuesta a un error de validación.</span><span class="sxs-lookup"><span data-stu-id="9b534-129">Click to repeat the validation steps if you make a change outside of the wizard in response to a validation error.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="9b534-130">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="9b534-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="9b534-131">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9b534-131">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="9b534-132">Usar el Asistente para agregar una réplica al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9b534-132">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="9b534-133">Usar el Asistente para agregar una base de datos al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9b534-133">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="9b534-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b534-134">See Also</span></span>  
 [<span data-ttu-id="9b534-135">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9b534-135">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
