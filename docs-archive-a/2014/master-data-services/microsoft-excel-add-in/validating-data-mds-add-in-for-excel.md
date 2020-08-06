---
title: Validar datos (complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 71eda98f-01a4-4fff-8246-be3133782523
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f8e97ff6481996b2e16436e1f78478bd234fe6ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673074"
---
# <a name="validating-data-mds-add-in-for-excel"></a><span data-ttu-id="046c8-102">Validar datos (complemento MDS para Excel)</span><span class="sxs-lookup"><span data-stu-id="046c8-102">Validating Data (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="046c8-103">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], al publicar datos, tienen lugar dos tipos de validación:</span><span class="sxs-lookup"><span data-stu-id="046c8-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], when you publish data, two types of validation take place:</span></span>  
  
-   <span data-ttu-id="046c8-104">Las reglas de negocio definidas se aplican a los datos.</span><span class="sxs-lookup"><span data-stu-id="046c8-104">Any defined business rules are applied to the data.</span></span>  
  
-   <span data-ttu-id="046c8-105">Los datos se comparan con los valores de atributo permitido (por ejemplo, el número de caracteres o el tipo de datos).</span><span class="sxs-lookup"><span data-stu-id="046c8-105">Data is checked against allowed attribute values (for example, number of characters or type of data).</span></span>  
  
 <span data-ttu-id="046c8-106">En cada caso, los datos se publican en el repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="046c8-106">In each case, valid data is published to the MDS repository.</span></span> <span data-ttu-id="046c8-107">Los datos que no son válidos se resaltan y los detalles de error se pueden mostrar en las columnas de estado.</span><span class="sxs-lookup"><span data-stu-id="046c8-107">Data that is not valid is highlighted, and details of the error can be shown in status columns.</span></span>  
  
## <a name="when-validation-occurs"></a><span data-ttu-id="046c8-108">Cuándo se produce la validación</span><span class="sxs-lookup"><span data-stu-id="046c8-108">When Validation Occurs</span></span>  
 <span data-ttu-id="046c8-109">En [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], la validación tiene lugar al publicar datos nuevos o modificados, o cuando las reglas de negocios se aplican manualmente.</span><span class="sxs-lookup"><span data-stu-id="046c8-109">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], validation occurs when you publish new or changed data, or when you manually apply business rules.</span></span>  
  
 <span data-ttu-id="046c8-110">Cuando las reglas de negocios producen un error, los datos siguen publicándose en el repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="046c8-110">When business rules fail, the data is still published to the MDS repository.</span></span> <span data-ttu-id="046c8-111">Cuando se produce un error en la validación de entrada, los datos no se publican en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="046c8-111">When input validation fails, the data is not published to the repository.</span></span>  
  
## <a name="validation-statuses"></a><span data-ttu-id="046c8-112">Estados de validación</span><span class="sxs-lookup"><span data-stu-id="046c8-112">Validation Statuses</span></span>  
 <span data-ttu-id="046c8-113">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], son posibles los siguientes estados de validación.</span><span class="sxs-lookup"><span data-stu-id="046c8-113">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following validation statuses are possible.</span></span>  
  
|<span data-ttu-id="046c8-114">Estado</span><span class="sxs-lookup"><span data-stu-id="046c8-114">Status</span></span>|<span data-ttu-id="046c8-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="046c8-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="046c8-116">Error</span><span class="sxs-lookup"><span data-stu-id="046c8-116">Error</span></span>|<span data-ttu-id="046c8-117">Uno o más valores de la fila no pudieron realizar la validación con las reglas de negocios definidas por un administrador MDS.</span><span class="sxs-lookup"><span data-stu-id="046c8-117">One or more values in the row failed validation against business rules defined by an MDS administrator.</span></span>|  
|<span data-ttu-id="046c8-118">No se validaron</span><span class="sxs-lookup"><span data-stu-id="046c8-118">Not Validated</span></span>|<span data-ttu-id="046c8-119">Los valores de la fila aún no se han validado con las reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="046c8-119">Values in the row have not yet been validated against business rules.</span></span>|  
|<span data-ttu-id="046c8-120">Correcto</span><span class="sxs-lookup"><span data-stu-id="046c8-120">Success</span></span>|<span data-ttu-id="046c8-121">Todos los valores de la fila han pasado la validación según las reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="046c8-121">All values in the row have passed validation against business rules.</span></span>|  
  
## <a name="input-statuses"></a><span data-ttu-id="046c8-122">Estados de entrada</span><span class="sxs-lookup"><span data-stu-id="046c8-122">Input Statuses</span></span>  
 <span data-ttu-id="046c8-123">En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], son posibles los siguientes estados de entrada.</span><span class="sxs-lookup"><span data-stu-id="046c8-123">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], the following input statuses are possible</span></span>  
  
|<span data-ttu-id="046c8-124">Estado</span><span class="sxs-lookup"><span data-stu-id="046c8-124">Status</span></span>|<span data-ttu-id="046c8-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="046c8-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="046c8-126">Error</span><span class="sxs-lookup"><span data-stu-id="046c8-126">Error</span></span>|<span data-ttu-id="046c8-127">Uno o más valores de la fila no cumplen los requisitos del sistema como la longitud o el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="046c8-127">One or more values in the row don't meet system requirements like length or data type.</span></span> <span data-ttu-id="046c8-128">El valor no se actualiza en el repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="046c8-128">The value is not updated in the MDS repository.</span></span>|  
|<span data-ttu-id="046c8-129">Nueva fila</span><span class="sxs-lookup"><span data-stu-id="046c8-129">New Row</span></span>|<span data-ttu-id="046c8-130">Los valores de la fila aún no se han publicado en el repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="046c8-130">The values in the row have not yet been published to the MDS repository.</span></span>|  
|<span data-ttu-id="046c8-131">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="046c8-131">Read Only</span></span>|<span data-ttu-id="046c8-132">El usuario que ha iniciado sesión tiene permisos de solo lectura en uno o varios valores de fila y los valores no pueden actualizarse.</span><span class="sxs-lookup"><span data-stu-id="046c8-132">The logged in user has Read-only permissions to one or more values in the row and the value(s) cannot be updated.</span></span>|  
|<span data-ttu-id="046c8-133">Sin cambios</span><span class="sxs-lookup"><span data-stu-id="046c8-133">Unchanged</span></span>|<span data-ttu-id="046c8-134">No se ha cambiado ningún valor de la fila en la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="046c8-134">No values in the row have been changed in the worksheet.</span></span> <span data-ttu-id="046c8-135">Esto no significa que los valores del repositorio no hayan cambiado; para obtener los datos más recientes de la hoja, en el grupo **Conectar y cargar** , haga clic en **Cargar o actualizar**.</span><span class="sxs-lookup"><span data-stu-id="046c8-135">This does not mean the values in the repository have not changed; to get the latest data in the sheet, in the **Connect and Load** group, click **Load or Refresh**.</span></span><br /><br /> <span data-ttu-id="046c8-136">Esta es la configuración predeterminada de cada fila.</span><span class="sxs-lookup"><span data-stu-id="046c8-136">This is the default setting for each row.</span></span>|  
  
## <a name="related-tasks"></a><span data-ttu-id="046c8-137">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="046c8-137">Related Tasks</span></span>  
  
|<span data-ttu-id="046c8-138">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="046c8-138">Task Description</span></span>|<span data-ttu-id="046c8-139">Tema</span><span class="sxs-lookup"><span data-stu-id="046c8-139">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="046c8-140">Determine qué valores no pasan las reglas de negocios definidas.</span><span class="sxs-lookup"><span data-stu-id="046c8-140">Determine which values do not pass the defined business rules.</span></span>|[<span data-ttu-id="046c8-141">Aplicar reglas de negocios &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="046c8-141">Apply Business Rules &#40;MDS Add-in for Excel&#41;</span></span>](apply-business-rules-mds-add-in-for-excel.md)|  
|<span data-ttu-id="046c8-142">Para ayudar a corregir los errores de validación, vea todas las transacciones que han tenido lugar para un miembro.</span><span class="sxs-lookup"><span data-stu-id="046c8-142">To help correct validation errors, view all transactions that have taken place for a member.</span></span>|[<span data-ttu-id="046c8-143">Ver todas las anotaciones o transacciones de un miembro &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="046c8-143">View All Annotations or Transactions for a Member &#40;MDS Add-in for Excel&#41;</span></span>](view-all-annotations-or-transactions-for-a-member-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="046c8-144">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="046c8-144">Related Content</span></span>  
  
-   [<span data-ttu-id="046c8-145">Complemento MDS para Excel de &#40;de datos de publicación&#41;</span><span class="sxs-lookup"><span data-stu-id="046c8-145">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
