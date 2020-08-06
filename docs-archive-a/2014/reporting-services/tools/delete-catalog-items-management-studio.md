---
title: Eliminar elementos del catálogo (Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.deleteitems.f1
ms.assetid: b0599e01-6dc3-4484-80d4-022a412e0ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d2a1824f2611165c9ae891fcb702418244f3621e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671929"
---
# <a name="delete-catalog-items-management-studio"></a><span data-ttu-id="4b76f-102">Eliminar elementos del catálogo (Management Studio)</span><span class="sxs-lookup"><span data-stu-id="4b76f-102">Delete Catalog Items (Management Studio)</span></span>
  <span data-ttu-id="4b76f-103">Utilice esta página para eliminar programaciones compartidas y definiciones de roles.</span><span class="sxs-lookup"><span data-stu-id="4b76f-103">Use this page to delete shared schedules and role definitions.</span></span>  
  
 <span data-ttu-id="4b76f-104">Si elimina una programación compartida usada por varios informes y suscripciones, el servidor de informes creará calendarios individuales para cada informe y suscripción que haya usado anteriormente la programación compartida.</span><span class="sxs-lookup"><span data-stu-id="4b76f-104">If you delete a shared schedule that is used by multiple reports and subscriptions, the report server will create individual schedules for each report and subscription that previously used the shared schedule.</span></span> <span data-ttu-id="4b76f-105">Cada nueva programación individual contendrá la fecha, la hora y el patrón de periodicidad que se especificó en la programación compartida.</span><span class="sxs-lookup"><span data-stu-id="4b76f-105">Each new individual schedule will contain the date, time, and recurrence pattern that was specified in the shared schedule.</span></span> <span data-ttu-id="4b76f-106">Tenga en cuenta que [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no proporciona la administración central de las programaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="4b76f-106">Note that [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not provide central management of individual schedules.</span></span> <span data-ttu-id="4b76f-107">Si elimina una programación compartida, tendrá que mantener ahora la información de programación para cada elemento individual.</span><span class="sxs-lookup"><span data-stu-id="4b76f-107">If you delete a shared schedule, you will now need to maintain the schedule information for each individual item.</span></span> <span data-ttu-id="4b76f-108">Antes de eliminar una programación compartida, use la [página Informes](schedule-properties-reports-page.md) para determinar qué informes usan actualmente la programación compartida.</span><span class="sxs-lookup"><span data-stu-id="4b76f-108">Before deleting a shared schedule, use the [Reports page](schedule-properties-reports-page.md) to determine which reports are currently using the shared schedule.</span></span>  
  
 <span data-ttu-id="4b76f-109">Para las definiciones de roles, solo se pueden eliminar las que no se usan en una asignación de roles activamente.</span><span class="sxs-lookup"><span data-stu-id="4b76f-109">For role definitions, you can only delete those that are not actively used in a role assignment.</span></span> <span data-ttu-id="4b76f-110">Si intenta eliminar un rol que se encuentra actualmente en uso, el servidor de informes no eliminará el rol y verá un mensaje de error para dicho efecto.</span><span class="sxs-lookup"><span data-stu-id="4b76f-110">If you try to delete a role that is currently in use, the report server will not delete the role and you will see an error message to that effect.</span></span> <span data-ttu-id="4b76f-111">Si esta página contiene una definición de roles única que no se encuentra actualmente en uso, se eliminará al hacer clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b76f-111">If this page contains a single role definition that is not currently in use, it will be deleted when you click **OK**.</span></span> <span data-ttu-id="4b76f-112">Si esta página contiene varios roles, no puede seleccionar qué roles desea mantener o quitar.</span><span class="sxs-lookup"><span data-stu-id="4b76f-112">If this page contains multiple roles, you cannot select which roles to keep or remove.</span></span> <span data-ttu-id="4b76f-113">Se eliminarán todas las definiciones de roles no usadas al hacer clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b76f-113">All unused role definitions will be deleted when you click **OK**.</span></span>  
  
 <span data-ttu-id="4b76f-114">No puede deshacer una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="4b76f-114">You cannot undo a delete operation.</span></span> <span data-ttu-id="4b76f-115">Si desea recuperar un elemento eliminado, debe volver a crearlo o restaurar una copia de seguridad de la base de datos de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="4b76f-115">If you want to recover an item that you deleted, you must either recreate it or restore a backup copy of the report server database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4b76f-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="4b76f-116">Options</span></span>  
 <span data-ttu-id="4b76f-117">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="4b76f-117">**Name**</span></span>  
 <span data-ttu-id="4b76f-118">Especifica el nombre del elemento que va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="4b76f-118">Specifies the name of the item you are deleting.</span></span>  
  
 <span data-ttu-id="4b76f-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4b76f-119">**Type**</span></span>  
 <span data-ttu-id="4b76f-120">Muestra el tipo de elemento que va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="4b76f-120">Shows the type of item you are deleting.</span></span>  
  
 <span data-ttu-id="4b76f-121">**Propietario**</span><span class="sxs-lookup"><span data-stu-id="4b76f-121">**Owner**</span></span>  
 <span data-ttu-id="4b76f-122">Muestra el nombre del propietario.</span><span class="sxs-lookup"><span data-stu-id="4b76f-122">Shows the name of the owner.</span></span> <span data-ttu-id="4b76f-123">En la mayoría de los casos, es Sistema.</span><span class="sxs-lookup"><span data-stu-id="4b76f-123">In most cases, this is System.</span></span>  
  
 <span data-ttu-id="4b76f-124">**Estado**</span><span class="sxs-lookup"><span data-stu-id="4b76f-124">**Status**</span></span>  
 <span data-ttu-id="4b76f-125">Muestra información de progreso de una operación de eliminación.</span><span class="sxs-lookup"><span data-stu-id="4b76f-125">Shows progress information for a delete operation.</span></span>  
  
 <span data-ttu-id="4b76f-126">**Error**</span><span class="sxs-lookup"><span data-stu-id="4b76f-126">**Error**</span></span>  
 <span data-ttu-id="4b76f-127">Muestra un código de error si se produce un error al eliminar un elemento.</span><span class="sxs-lookup"><span data-stu-id="4b76f-127">Displays an error code if an error occurs while deleting an item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b76f-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b76f-128">See Also</span></span>  
 <span data-ttu-id="4b76f-129">[Eliminar un elemento &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="4b76f-129">[Delete an Item &#40;Management Studio&#41;](delete-an-item-management-studio.md) </span></span>  
 <span data-ttu-id="4b76f-130">[Servidor de informes en Management Studio ayuda F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="4b76f-130">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="4b76f-131">Creación, modificación y eliminación de programaciones</span><span class="sxs-lookup"><span data-stu-id="4b76f-131">Create, Modify, and Delete Schedules</span></span>](../subscriptions/create-modify-and-delete-schedules.md)  
  
  
