---
title: Editor de bucles foreach (página asignaciones de variables) | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.foreachloopcontainer.mapping.f1
ms.assetid: aa847b87-f391-48a5-9849-eeda2d6b00b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd37c8c6c00f18d8b5493a058239cc880ecc1f5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752277"
---
# <a name="foreach-loop-editor-variable-mappings-page"></a><span data-ttu-id="21540-102">Editor de bucles Foreach (página Asignaciones de variables)</span><span class="sxs-lookup"><span data-stu-id="21540-102">Foreach Loop Editor (Variable Mappings Page)</span></span>
  <span data-ttu-id="21540-103">Use la página **Asignaciones de variables** del cuadro de diálogo **Editor de bucles Foreach** para asignar variables al valor de la colección.</span><span class="sxs-lookup"><span data-stu-id="21540-103">Use the **Variables Mappings** page of the **Foreach Loop Editor** dialog box to map variables to the collection value.</span></span> <span data-ttu-id="21540-104">El valor de la variable se actualiza con los valores de la colección en cada iteración del bucle.</span><span class="sxs-lookup"><span data-stu-id="21540-104">The value of the variable is updated with the collection values on each iteration of the loop.</span></span>  
  
 <span data-ttu-id="21540-105">Para obtener más información acerca de cómo utilizar el contenedor de bucles Foreach en un paquete de Integration Services, vea [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span><span class="sxs-lookup"><span data-stu-id="21540-105">To learn about how to use the Foreach Loop container in an Integration Services package,  see [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span></span> <span data-ttu-id="21540-106">Para saber cómo se configura, vea [Configurar un contenedor de bucles Foreach](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="21540-106">To learn about how to configure it, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="21540-107">El tutorial de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], llamado Tutorial para crear un paquete ETL sencillo, incluye una lección que le enseña a agregar y configurar un bucle Foreach.</span><span class="sxs-lookup"><span data-stu-id="21540-107">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial, Creating a Simple ETL Package Tutorial, includes a lesson that teaches you to add and configure a Foreach Loop.</span></span>  
  
## <a name="options"></a><span data-ttu-id="21540-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="21540-108">Options</span></span>  
 <span data-ttu-id="21540-109">**Variable**</span><span class="sxs-lookup"><span data-stu-id="21540-109">**Variable**</span></span>  
 <span data-ttu-id="21540-110">Seleccione una variable existente o haga clic en \<**New variable...**> para crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="21540-110">Select an existing variable, or click \<**New variable...**> to create a new variable.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21540-111">Una vez asignada una variable, se agregará automáticamente una nueva fila a la lista **Variable**.</span><span class="sxs-lookup"><span data-stu-id="21540-111">After you map a variable, a new row is automatically added to the **Variable** list.</span></span>  
  
 <span data-ttu-id="21540-112">**Temas relacionados**: [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="21540-112">**Related Topics**: [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="21540-113">**Index**</span><span class="sxs-lookup"><span data-stu-id="21540-113">**Index**</span></span>  
 <span data-ttu-id="21540-114">Si utiliza el enumerador de elementos para Foreach, especifique el índice de la columna en el valor de la colección para asignarlo a la variable.</span><span class="sxs-lookup"><span data-stu-id="21540-114">If using the Foreach Item enumerator, specify the index of the column in the collection value to map to the variable.</span></span> <span data-ttu-id="21540-115">Si utiliza otros tipos de enumeradores, el índice será de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="21540-115">For other enumerator types, the index is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="21540-116">El índice se basa en 0.</span><span class="sxs-lookup"><span data-stu-id="21540-116">The index is 0-based.</span></span>  
  
 <span data-ttu-id="21540-117">**Temas relacionados**: crear [bucles entre archivos y tablas de Excel mediante un contenedor de bucles foreach](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span><span class="sxs-lookup"><span data-stu-id="21540-117">**Related Topics**: [Loop through Excel Files and Tables by Using a Foreach Loop Container](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span></span>  
  
 <span data-ttu-id="21540-118">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="21540-118">**Delete**</span></span>  
 <span data-ttu-id="21540-119">Seleccione una variable y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="21540-119">Select a variable, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21540-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21540-120">See Also</span></span>  
 <span data-ttu-id="21540-121">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="21540-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="21540-122">[Editor de bucles foreach &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="21540-122">[Foreach Loop Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="21540-123">[Página colección de &#40;del editor de bucles foreach&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span><span class="sxs-lookup"><span data-stu-id="21540-123">[Foreach Loop Editor &#40;Collection Page&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span></span>  
 <span data-ttu-id="21540-124">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="21540-124">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="21540-125">Contenedor de bucles For</span><span class="sxs-lookup"><span data-stu-id="21540-125">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
