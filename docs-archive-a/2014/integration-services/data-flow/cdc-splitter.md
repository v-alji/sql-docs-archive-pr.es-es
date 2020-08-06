---
title: Divisor CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsplitter.f1
ms.assetid: 167bc5c6-fa36-439d-987c-b20acd1a77e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45dd16602625b28d2ca7e16f2fa6b0d62294fe81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674240"
---
# <a name="cdc-splitter"></a><span data-ttu-id="19823-102">Divisor CDC</span><span class="sxs-lookup"><span data-stu-id="19823-102">CDC Splitter</span></span>
  <span data-ttu-id="19823-103">El divisor CDC divide un único flujo de filas de un flujo de datos de origen de CDC en varios flujos de datos para las operaciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="19823-103">The CDC splitter splits a single flow of change rows from a CDC source data flow into different data flows for Insert, Update and Delete operations.</span></span> <span data-ttu-id="19823-104">El flujo de datos se divide según la columna obligatoria `__$operation` y sus valores estándar en las tablas de cambios de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19823-104">The data flow is split based on the required column `__$operation` and its standard values in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables.</span></span>  
  
|<span data-ttu-id="19823-105">Valor de la operación</span><span class="sxs-lookup"><span data-stu-id="19823-105">Value of Operation</span></span>|<span data-ttu-id="19823-106">Output</span><span class="sxs-lookup"><span data-stu-id="19823-106">Output</span></span>|<span data-ttu-id="19823-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="19823-107">Description</span></span>|  
|------------------------|------------|-----------------|  
|<span data-ttu-id="19823-108">1</span><span class="sxs-lookup"><span data-stu-id="19823-108">1</span></span>|<span data-ttu-id="19823-109">Eliminar</span><span class="sxs-lookup"><span data-stu-id="19823-109">Delete</span></span>|<span data-ttu-id="19823-110">Fila eliminada</span><span class="sxs-lookup"><span data-stu-id="19823-110">Deleted Row</span></span>|  
|<span data-ttu-id="19823-111">2</span><span class="sxs-lookup"><span data-stu-id="19823-111">2</span></span>|<span data-ttu-id="19823-112">Insertar</span><span class="sxs-lookup"><span data-stu-id="19823-112">Insert</span></span>|<span data-ttu-id="19823-113">Fila insertada (no está disponible cuando se usa el modo CDC **Neto con combinación** )</span><span class="sxs-lookup"><span data-stu-id="19823-113">Inserted row (not available when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="19823-114">3</span><span class="sxs-lookup"><span data-stu-id="19823-114">3</span></span>|<span data-ttu-id="19823-115">Actualizar</span><span class="sxs-lookup"><span data-stu-id="19823-115">Update</span></span>|<span data-ttu-id="19823-116">Fila antes de la actualización (disponible solo cuando se usa el modo CDC **Todo con los valores antiguos** )</span><span class="sxs-lookup"><span data-stu-id="19823-116">Before-update row (available only when using **All with Old Values** CDC mode)</span></span>|  
|<span data-ttu-id="19823-117">4</span><span class="sxs-lookup"><span data-stu-id="19823-117">4</span></span>|<span data-ttu-id="19823-118">Actualizar</span><span class="sxs-lookup"><span data-stu-id="19823-118">Update</span></span>|<span data-ttu-id="19823-119">Fila después de la actualización (sigue a la de antes de la actualización)</span><span class="sxs-lookup"><span data-stu-id="19823-119">After-update row (follows the Before-update)</span></span>|  
|<span data-ttu-id="19823-120">5</span><span class="sxs-lookup"><span data-stu-id="19823-120">5</span></span>|<span data-ttu-id="19823-121">Actualizar</span><span class="sxs-lookup"><span data-stu-id="19823-121">Update</span></span>|<span data-ttu-id="19823-122">Fila de mezcla (solo disponible cuando se usa el modo CDC **Neto con combinación** )</span><span class="sxs-lookup"><span data-stu-id="19823-122">Merge row (available only when using **Net with Merge** CDC mode)</span></span>|  
|<span data-ttu-id="19823-123">Otros</span><span class="sxs-lookup"><span data-stu-id="19823-123">Other</span></span>|<span data-ttu-id="19823-124">Error</span><span class="sxs-lookup"><span data-stu-id="19823-124">Error</span></span>||  
  
 <span data-ttu-id="19823-125">Puede usar el divisor para conectarse a los resultados predefinidos de INSERT, UPDATE, DELETE y UPDATE para un procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="19823-125">You can use the splitter to connect to pre-defined INSERT, DELETE, and UPDATE outputs for further processing.</span></span>  
  
 <span data-ttu-id="19823-126">La transformación divisor CDC tiene una entrada normal y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="19823-126">The CDC Splitter transformation has one regular input and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="19823-127">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="19823-127">Error Handling</span></span>  
 <span data-ttu-id="19823-128">La transformación divisor CDC tiene una salida de error.</span><span class="sxs-lookup"><span data-stu-id="19823-128">The CDC Splitter transformation has an error output.</span></span> <span data-ttu-id="19823-129">Las filas de entrada con un valor no válido de la columna $operation se consideran erróneas y se administran según la propiedad **ErrorRowDisposition** de la entrada.</span><span class="sxs-lookup"><span data-stu-id="19823-129">Input rows with an invalid value of the $operation column are considered erroneous and are handled according to the **ErrorRowDisposition** property of the input.</span></span>  
  
 <span data-ttu-id="19823-130">La salida de error del componente incluye las columnas de salida siguientes:</span><span class="sxs-lookup"><span data-stu-id="19823-130">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="19823-131">**Código de error**: se establece en 1.</span><span class="sxs-lookup"><span data-stu-id="19823-131">**Error Code**: Set to 1.</span></span>  
  
-   <span data-ttu-id="19823-132">**Columna de error**: columna de origen que produce el error (para los errores de conversión).</span><span class="sxs-lookup"><span data-stu-id="19823-132">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="19823-133">**Columnas de fila de error**: las columnas de entrada de la fila que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="19823-133">**Error Row Columns**: The input columns of the row that caused the error.</span></span>  
  
## <a name="configuring-the-cdc-splitter"></a><span data-ttu-id="19823-134">Configuración del divisor CDC</span><span class="sxs-lookup"><span data-stu-id="19823-134">Configuring the CDC Splitter</span></span>  
 <span data-ttu-id="19823-135">No hay propiedades configurables del divisor CDC.</span><span class="sxs-lookup"><span data-stu-id="19823-135">There are no configurable properties for the CDC splitter.</span></span>  
  
 <span data-ttu-id="19823-136">Para obtener más información sobre cómo usar el divisor CDC, vea Componentes CDC para Microsoft SQL Server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="19823-136">For more information about using the CDC splitter, see CDC Components for Microsoft SQL Server Integration Services.</span></span>  
  
 <span data-ttu-id="19823-137">El cuadro de diálogo **Editor avanzado** contiene las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="19823-137">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="19823-138">Para abrir el cuadro de diálogo **Editor avanzado** :</span><span class="sxs-lookup"><span data-stu-id="19823-138">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="19823-139">En la pantalla **Flujo de datos** del proyecto de [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , haga clic con el botón secundario en el divisor CDC y seleccione **Mostrar editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="19823-139">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC splitter and select **Show Advanced Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19823-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="19823-140">See Also</span></span>  
 [<span data-ttu-id="19823-141">Dirigir el flujo CDC según el tipo de cambio</span><span class="sxs-lookup"><span data-stu-id="19823-141">Direct the CDC Stream According to the Type of Change</span></span>](direct-the-cdc-stream-according-to-the-type-of-change.md)  
  
  
