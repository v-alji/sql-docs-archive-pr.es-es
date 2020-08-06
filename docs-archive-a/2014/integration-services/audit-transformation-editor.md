---
title: Editor de transformación auditar | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.audittransformation.f1
helpviewer_keywords:
- Audit Transformation Editor
ms.assetid: 32786a34-5870-4fde-83c7-ec74d62404b8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: af6490643a0bef60cca961dc9a0564c5f6b46484
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749410"
---
# <a name="audit-transformation-editor"></a><span data-ttu-id="a961f-102">Editor de transformación Auditar</span><span class="sxs-lookup"><span data-stu-id="a961f-102">Audit Transformation Editor</span></span>
  <span data-ttu-id="a961f-103">La transformación Auditar habilita el flujo de datos en un paquete para incluir datos sobre el entorno en el que se ejecuta el paquete.</span><span class="sxs-lookup"><span data-stu-id="a961f-103">The Audit transformation enables the data flow in a package to include data about the environment in which the package runs.</span></span> <span data-ttu-id="a961f-104">Por ejemplo, el nombre del paquete, el equipo y el operador se pueden agregar al flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="a961f-104">For example, the name of the package, computer, and operator can be added to the data flow.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="a961f-105">incluye variables del sistema que proporcionan esta información.</span><span class="sxs-lookup"><span data-stu-id="a961f-105">includes system variables that provide this information.</span></span>  
  
 <span data-ttu-id="a961f-106">Para obtener más información acerca de la transformación Auditar, vea [Audit Transformation](data-flow/transformations/audit-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a961f-106">To learn more about the Audit transformation, see [Audit Transformation](data-flow/transformations/audit-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a961f-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="a961f-107">Options</span></span>  
 <span data-ttu-id="a961f-108">**Nombre de la columna de salida**</span><span class="sxs-lookup"><span data-stu-id="a961f-108">**Output column name**</span></span>  
 <span data-ttu-id="a961f-109">Proporciona el nombre de una nueva columna de salida que contendrá la información de auditoría.</span><span class="sxs-lookup"><span data-stu-id="a961f-109">Provide the name for a new output column that will contain the audit information.</span></span>  
  
 <span data-ttu-id="a961f-110">**Tipo de auditoría**</span><span class="sxs-lookup"><span data-stu-id="a961f-110">**Audit type**</span></span>  
 <span data-ttu-id="a961f-111">Seleccione una variable del sistema disponible para suministrar la información de auditoría.</span><span class="sxs-lookup"><span data-stu-id="a961f-111">Select an available system variable to supply the audit information.</span></span>  
  
|<span data-ttu-id="a961f-112">Value</span><span class="sxs-lookup"><span data-stu-id="a961f-112">Value</span></span>|<span data-ttu-id="a961f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a961f-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a961f-114">**GUID de instancia de ejecución**</span><span class="sxs-lookup"><span data-stu-id="a961f-114">**Execution instance GUID**</span></span>|<span data-ttu-id="a961f-115">Inserte el GUID que identifica exclusivamente la instancia de ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="a961f-115">Insert the GUID that uniquely identifies the execution instance of the package.</span></span>|  
|<span data-ttu-id="a961f-116">**Id. de paquete**</span><span class="sxs-lookup"><span data-stu-id="a961f-116">**Package ID**</span></span>|<span data-ttu-id="a961f-117">Inserte el GUID que identifica exclusivamente el paquete.</span><span class="sxs-lookup"><span data-stu-id="a961f-117">Insert the GUID that uniquely identifies the package.</span></span>|  
|<span data-ttu-id="a961f-118">**Nombre del paquete**</span><span class="sxs-lookup"><span data-stu-id="a961f-118">**Package name**</span></span>|<span data-ttu-id="a961f-119">Inserte el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="a961f-119">Insert the package name.</span></span>|  
|<span data-ttu-id="a961f-120">**Id. de la versión**</span><span class="sxs-lookup"><span data-stu-id="a961f-120">**Version ID**</span></span>|<span data-ttu-id="a961f-121">Inserte el GUID que identifica exclusivamente la versión del paquete.</span><span class="sxs-lookup"><span data-stu-id="a961f-121">Insert the GUID that uniquely identifies the version of the package.</span></span>|  
|<span data-ttu-id="a961f-122">**Hora de inicio de ejecución**</span><span class="sxs-lookup"><span data-stu-id="a961f-122">**Execution start time**</span></span>|<span data-ttu-id="a961f-123">Inserte la hora en la que se iniciará la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="a961f-123">Insert the time at which package execution started.</span></span>|  
|<span data-ttu-id="a961f-124">**Nombre de la máquina**</span><span class="sxs-lookup"><span data-stu-id="a961f-124">**Machine name**</span></span>|<span data-ttu-id="a961f-125">Inserte el nombre del equipo en el que se inició el paquete.</span><span class="sxs-lookup"><span data-stu-id="a961f-125">Insert the name of the computer on which the package was launched.</span></span>|  
|<span data-ttu-id="a961f-126">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="a961f-126">**User name**</span></span>|<span data-ttu-id="a961f-127">Inserte el nombre de inicio de sesión del usuario que inició el paquete.</span><span class="sxs-lookup"><span data-stu-id="a961f-127">Insert the login name of the user who launched the package.</span></span>|  
|<span data-ttu-id="a961f-128">**Nombre de tarea**</span><span class="sxs-lookup"><span data-stu-id="a961f-128">**Task name**</span></span>|<span data-ttu-id="a961f-129">Inserte el nombre de la tarea Flujo de datos con la que está asociada la transformación Auditar.</span><span class="sxs-lookup"><span data-stu-id="a961f-129">Insert the name of the Data Flow task with which the Audit transformation is associated.</span></span>|  
|<span data-ttu-id="a961f-130">**Identificador de tarea**</span><span class="sxs-lookup"><span data-stu-id="a961f-130">**Task ID**</span></span>|<span data-ttu-id="a961f-131">Inserte el GUID que identifica exclusivamente la tarea Flujo de datos con la que está asociada la transformación Auditar.</span><span class="sxs-lookup"><span data-stu-id="a961f-131">Insert the GUID that uniquely identifies the Data Flow task with which the Audit transformation is associated.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a961f-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a961f-132">See Also</span></span>  
 [<span data-ttu-id="a961f-133">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="a961f-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
