---
title: Transformación Auditar | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittrans.f1
helpviewer_keywords:
- environment data in packages [Integration Services]
- Audit transformation
ms.assetid: 8c143682-9c81-4150-83d6-1d9678151d37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e8e302f6dd1dc5666ae65af2eb9705a4922915c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744214"
---
# <a name="audit-transformation"></a><span data-ttu-id="7f85e-102">Auditar, transformación</span><span class="sxs-lookup"><span data-stu-id="7f85e-102">Audit Transformation</span></span>
  <span data-ttu-id="7f85e-103">La transformación Auditar habilita el flujo de datos en un paquete para incluir datos sobre el entorno en el que se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="7f85e-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="7f85e-104">Por ejemplo, el nombre del paquete, el equipo y el operador se pueden agregar al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="7f85e-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="7f85e-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] incluye variables del sistema que proporcionan esta información.</span><span class="sxs-lookup"><span data-stu-id="7f85e-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] includes system variables that provide this information.</span></span>  
  
## <a name="system-variables"></a><span data-ttu-id="7f85e-106">Variables del sistema</span><span class="sxs-lookup"><span data-stu-id="7f85e-106">System Variables</span></span>  
 <span data-ttu-id="7f85e-107">En la tabla siguiente se describen las variables del sistema que la transformación Auditar puede usar.</span><span class="sxs-lookup"><span data-stu-id="7f85e-107">The following table describes the system variables that the Audit transformation can use.</span></span>  
  
|<span data-ttu-id="7f85e-108">Variable del sistema</span><span class="sxs-lookup"><span data-stu-id="7f85e-108">System variable</span></span>|<span data-ttu-id="7f85e-109">Índice</span><span class="sxs-lookup"><span data-stu-id="7f85e-109">Index</span></span>|<span data-ttu-id="7f85e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f85e-110">Description</span></span>|  
|---------------------|-----------|-----------------|  
|`ExecutionInstanceGUID`|<span data-ttu-id="7f85e-111">0</span><span class="sxs-lookup"><span data-stu-id="7f85e-111">0</span></span>|<span data-ttu-id="7f85e-112">El GUID que identifica la instancia de ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="7f85e-112">The GUID that identifies the execution instance of the package.</span></span>|  
|`PackageID`|<span data-ttu-id="7f85e-113">1</span><span class="sxs-lookup"><span data-stu-id="7f85e-113">1</span></span>|<span data-ttu-id="7f85e-114">Identificador único del paquete.</span><span class="sxs-lookup"><span data-stu-id="7f85e-114">The unique identifier of the package.</span></span>|  
|`PackageName`|<span data-ttu-id="7f85e-115">2</span><span class="sxs-lookup"><span data-stu-id="7f85e-115">2</span></span>|<span data-ttu-id="7f85e-116">Nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="7f85e-116">The package name.</span></span>|  
|`VersionID`|<span data-ttu-id="7f85e-117">3</span><span class="sxs-lookup"><span data-stu-id="7f85e-117">3</span></span>|<span data-ttu-id="7f85e-118">La versión del paquete.</span><span class="sxs-lookup"><span data-stu-id="7f85e-118">The version of the package.</span></span>|  
|`ExecutionStartTime`|<span data-ttu-id="7f85e-119">4</span><span class="sxs-lookup"><span data-stu-id="7f85e-119">4</span></span>|<span data-ttu-id="7f85e-120">La hora a la que se inició la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="7f85e-120">The time the package started to run.</span></span>|  
|`MachineName`|<span data-ttu-id="7f85e-121">5</span><span class="sxs-lookup"><span data-stu-id="7f85e-121">5</span></span>|<span data-ttu-id="7f85e-122">El nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="7f85e-122">The computer name.</span></span>|  
|`UserName`|<span data-ttu-id="7f85e-123">6</span><span class="sxs-lookup"><span data-stu-id="7f85e-123">6</span></span>|<span data-ttu-id="7f85e-124">El nombre de inicio de sesión de la persona que inició el paquete.</span><span class="sxs-lookup"><span data-stu-id="7f85e-124">The login name of the person who started the package.</span></span>|  
|`TaskName`|<span data-ttu-id="7f85e-125">7</span><span class="sxs-lookup"><span data-stu-id="7f85e-125">7</span></span>|<span data-ttu-id="7f85e-126">El nombre de la tarea Flujos de datos a la que está asociada la transformación Auditar.</span><span class="sxs-lookup"><span data-stu-id="7f85e-126">The name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="7f85e-127">**TaskId**</span><span class="sxs-lookup"><span data-stu-id="7f85e-127">**TaskId**</span></span>|<span data-ttu-id="7f85e-128">8</span><span class="sxs-lookup"><span data-stu-id="7f85e-128">8</span></span>|<span data-ttu-id="7f85e-129">El identificador único de la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="7f85e-129">The unique identifier of the Data Flow task.</span></span>|  
  
## <a name="configuration-of-the-audit-transformation"></a><span data-ttu-id="7f85e-130">Configuración de la transformación Auditar</span><span class="sxs-lookup"><span data-stu-id="7f85e-130">Configuration of the Audit Transformation</span></span>  
 <span data-ttu-id="7f85e-131">Para configurar la transformación Auditar debe proporcionar el nombre de una nueva columna de salida que se agregará a la salida de transformación y después asignar la variable del sistema a la columna de salida.</span><span class="sxs-lookup"><span data-stu-id="7f85e-131">You configure the Audit transformation by providing the name of a new output column to add to the transformation output, and then mapping the system variable to the output column.</span></span> <span data-ttu-id="7f85e-132">Puede asignar una sola variable del sistema a varias columnas.</span><span class="sxs-lookup"><span data-stu-id="7f85e-132">You can map a single system variable to multiple columns.</span></span>  
  
 <span data-ttu-id="7f85e-133">Esta transformación tiene una entrada y una salida.</span><span class="sxs-lookup"><span data-stu-id="7f85e-133">This transformation has one input and one output.</span></span> <span data-ttu-id="7f85e-134">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="7f85e-134">It does not support an error output.</span></span>  
  
 <span data-ttu-id="7f85e-135">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7f85e-135">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7f85e-136">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Auditar** , vea [Audit Transformation Editor](../../audit-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="7f85e-136">For more information about the properties that you can set in the **Audit Transformation Editor** dialog box, see [Audit Transformation Editor](../../audit-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="7f85e-137">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7f85e-137">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="7f85e-138">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7f85e-138">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7f85e-139">Common Properties</span><span class="sxs-lookup"><span data-stu-id="7f85e-139">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="7f85e-140">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="7f85e-140">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="7f85e-141">Para más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="7f85e-141">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
