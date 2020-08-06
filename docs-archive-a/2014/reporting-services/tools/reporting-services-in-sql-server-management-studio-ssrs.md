---
title: Reporting Services en SQL Server Management Studio (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], how-to topics
ms.assetid: 60685458-9108-47bf-820a-5e7db454d408
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3f4083d8b288c8816925723f4cfaef4342dd0298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747960"
---
# <a name="reporting-services-in-sql-server-management-studio-ssrs"></a><span data-ttu-id="a38f2-102">Reporting Services en SQL Server Management Studio (SSRS)</span><span class="sxs-lookup"><span data-stu-id="a38f2-102">Reporting Services in SQL Server Management Studio (SSRS)</span></span>
  <span data-ttu-id="a38f2-103">Los administradores del servidor de informes pueden usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para:</span><span class="sxs-lookup"><span data-stu-id="a38f2-103">Report server administrators can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to:</span></span>  
  
-   <span data-ttu-id="a38f2-104">Habilitar características, establecer valores predeterminados y administrar trabajos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a38f2-104">Enable features, set server defaults, and manage running jobs.</span></span>  
  
-   <span data-ttu-id="a38f2-105">Ver y crear informes personalizados.</span><span class="sxs-lookup"><span data-stu-id="a38f2-105">View and create custom reports.</span></span> <span data-ttu-id="a38f2-106">En el Explorador de objetos, muchos nodos muestran un conjunto de informes estándar que se instalan con [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a38f2-106">In Object Explorer, many nodes display a set of standard reports that are installed with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="a38f2-107">Debe contar con los siguientes permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="a38f2-107">You must have administrator permissions.</span></span> <span data-ttu-id="a38f2-108">El esquema de un informe personalizado debe coincidir con el esquema de los informes instalados.</span><span class="sxs-lookup"><span data-stu-id="a38f2-108">The schema of a custom report must match the schema of the installed reports.</span></span> <span data-ttu-id="a38f2-109">Para más información, vea [Informes personalizados en Management Studio](../../ssms/object/custom-reports-in-management-studio.md) y [Buscar la versión del esquema de definición de informe &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a38f2-109">For more information, see [Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) and [Find the Report Definition Schema Version &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span></span>  
  
 <span data-ttu-id="a38f2-110">Los autores de informes pueden usar [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para:</span><span class="sxs-lookup"><span data-stu-id="a38f2-110">Report authors can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="a38f2-111">Visualizar datos espaciales de un conjunto de resultados de la consulta para un informe de mapa.</span><span class="sxs-lookup"><span data-stu-id="a38f2-111">Visualize spatial data from a query result set for a map report.</span></span> <span data-ttu-id="a38f2-112">Después de ejecutar la consulta, use la pestaña **Resultados espaciales** en el panel de conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="a38f2-112">After you run the query, use the **Spatial results** tab in the result set pane.</span></span> <span data-ttu-id="a38f2-113">Para más información, consulte [View Spatial Data in Object Explorer](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="a38f2-113">For more information, see [View Spatial Data in Object Explorer](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span></span>  
  
 <span data-ttu-id="a38f2-114">Esta sección contiene instrucciones paso a paso para realizar varias tareas relacionadas con los informes que usan [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a38f2-114">This section contains step-by-step instructions for performing various reporting tasks using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="a38f2-115">La creación y administración de las programaciones compartidas también se pueden llevar a cabo con el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="a38f2-115">Creating and managing shared schedules can also be performed using Report Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a38f2-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a38f2-116">In This Section</span></span>  
  
-   [<span data-ttu-id="a38f2-117">Conectar con un servidor de informes en Management Studio</span><span class="sxs-lookup"><span data-stu-id="a38f2-117">Connect to a Report Server in Management Studio</span></span>](connect-to-a-report-server-in-management-studio.md)  
  
-   [<span data-ttu-id="a38f2-118">Establecer las propiedades del servidor de informes &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a38f2-118">Set Report Server Properties &#40;Management Studio&#41;</span></span>](set-report-server-properties-management-studio.md)  
  
-   [<span data-ttu-id="a38f2-119">Crear, eliminar o modificar un rol &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a38f2-119">Create, Delete, or Modify a Role &#40;Management Studio&#41;</span></span>](../security/role-definitions-create-delete-or-modify.md)  
  
-   [<span data-ttu-id="a38f2-120">Eliminar un elemento &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a38f2-120">Delete an Item &#40;Management Studio&#41;</span></span>](delete-an-item-management-studio.md)  
  
-   [<span data-ttu-id="a38f2-121">Cancelar trabajos del servidor de informes &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a38f2-121">Cancel Report Server Jobs &#40;Management Studio&#41;</span></span>](cancel-report-server-jobs-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="a38f2-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a38f2-122">See Also</span></span>  
 <span data-ttu-id="a38f2-123">[Servidor de informes en Management Studio ayuda de F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="a38f2-123">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="a38f2-124">Introducción a SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a38f2-124">Introducing SQL Server Management Studio</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
