---
title: Editor de la tarea ejecutar SQL (página asignación de parámetros) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.parametermapping.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: 8ebe020a-7921-46b2-8823-398748f379b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfbb4468cb69947dfa54fb519b7698286393d578
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671118"
---
# <a name="execute-sql-task-editor-parameter-mapping-page"></a><span data-ttu-id="4dd79-102">Editor de la tarea Ejecutar SQL (página Asignación de parámetros)</span><span class="sxs-lookup"><span data-stu-id="4dd79-102">Execute SQL Task Editor (Parameter Mapping Page)</span></span>
  <span data-ttu-id="4dd79-103">Use la página **Asignación de parámetros** del cuadro de diálogo **Editor de la tarea Ejecutar SQL** para asignar variables a los parámetros de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="4dd79-103">Use the **Parameter Mapping** page of the **Execute SQL Task Editor** dialog box to map variables to parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="4dd79-104">Para obtener información sobre esta tarea, vea [Tarea Ejecutar SQL](control-flow/execute-sql-task.md) y [Parámetros y códigos de retorno en la tarea Ejecutar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="4dd79-104">To learn about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4dd79-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="4dd79-105">Options</span></span>  
 <span data-ttu-id="4dd79-106">**Nombre de variable**</span><span class="sxs-lookup"><span data-stu-id="4dd79-106">**Variable Name**</span></span>  
 <span data-ttu-id="4dd79-107">Tras hacer clic en **Agregar** para agregar una asignación de parámetros, seleccione en la lista una variable del sistema o definida por el usuario, o haga clic en \<**New variable...**> para agregar una nueva variable mediante el cuadro de diálogo **Agregar variable**.</span><span class="sxs-lookup"><span data-stu-id="4dd79-107">After you have added a parameter mapping by clicking **Add**, select a system or user-defined variable from the list or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="4dd79-108">**Temas relacionados:** [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="4dd79-108">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
 <span data-ttu-id="4dd79-109">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="4dd79-109">**Direction**</span></span>  
 <span data-ttu-id="4dd79-110">Permite seleccionar la dirección del parámetro.</span><span class="sxs-lookup"><span data-stu-id="4dd79-110">Select the direction of the parameter.</span></span> <span data-ttu-id="4dd79-111">Asigne cada variable a un parámetro de entrada o de salida, o bien a un código de retorno.</span><span class="sxs-lookup"><span data-stu-id="4dd79-111">Map each variable to an input parameter, output parameter, or a return code.</span></span>  
  
 <span data-ttu-id="4dd79-112">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="4dd79-112">**Data Type**</span></span>  
 <span data-ttu-id="4dd79-113">Seleccione el tipo de datos del parámetro.</span><span class="sxs-lookup"><span data-stu-id="4dd79-113">Select the data type of the parameter.</span></span> <span data-ttu-id="4dd79-114">La lista de tipos de datos disponibles es específica del proveedor seleccionado en el administrador de conexiones utilizado por la tarea.</span><span class="sxs-lookup"><span data-stu-id="4dd79-114">The list of available data types is specific to the provider selected in the connection manager used by the task.</span></span>  
  
 <span data-ttu-id="4dd79-115">**Nombre de parámetro**</span><span class="sxs-lookup"><span data-stu-id="4dd79-115">**Parameter Name**</span></span>  
 <span data-ttu-id="4dd79-116">Proporcione un nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="4dd79-116">Provide a parameter name.</span></span>  
  
 <span data-ttu-id="4dd79-117">Dependiendo del tipo de administrador de conexiones que utiliza la tarea, se utilizarán números o nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="4dd79-117">Depending on the connection manager type that the task uses, you must use numbers or parameter names.</span></span> <span data-ttu-id="4dd79-118">Algunos tipos de administradores de conexión requieren que el primer carácter del nombre del parámetro sea el signo \@, nombres específicos como \@Param1 o nombres de columnas como nombres de parámetro.</span><span class="sxs-lookup"><span data-stu-id="4dd79-118">Some connection manager types require that the first character of the parameter name is the \@ sign , specific names like \@Param1, or column names as parameter names.</span></span>  
  
 <span data-ttu-id="4dd79-119">**Temas relacionados:** [Parámetros y códigos de retorno en la tarea Ejecutar SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="4dd79-119">**Related Topics:** [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="4dd79-120">**Tamaño del parámetro**</span><span class="sxs-lookup"><span data-stu-id="4dd79-120">**Parameter Size**</span></span>  
 <span data-ttu-id="4dd79-121">Proporcione el tamaño de los parámetros que tienen longitud variable, como cadenas y campos binarios.</span><span class="sxs-lookup"><span data-stu-id="4dd79-121">Provide the size of parameters that have variable length, such as strings and binary fields.</span></span>  
  
 <span data-ttu-id="4dd79-122">Este valor garantiza que el proveedor asigna el espacio suficiente para los valores de parámetro de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="4dd79-122">This setting ensures that the provider allocates sufficient space for variable-length parameter values.</span></span>  
  
 <span data-ttu-id="4dd79-123">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="4dd79-123">**Add**</span></span>  
 <span data-ttu-id="4dd79-124">Haga clic para agregar una asignación de parámetros.</span><span class="sxs-lookup"><span data-stu-id="4dd79-124">Click to add a parameter mapping.</span></span>  
  
 <span data-ttu-id="4dd79-125">**Remove**</span><span class="sxs-lookup"><span data-stu-id="4dd79-125">**Remove**</span></span>  
 <span data-ttu-id="4dd79-126">Seleccione una asignación de parámetros de la lista y después haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="4dd79-126">Select a parameter mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd79-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4dd79-127">See Also</span></span>  
 <span data-ttu-id="4dd79-128">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4dd79-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="4dd79-129">[Editor de la tarea ejecutar SQL &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="4dd79-129">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="4dd79-130">[Editor de la tarea ejecutar SQL &#40;página conjunto de resultados&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span><span class="sxs-lookup"><span data-stu-id="4dd79-130">[Execute SQL Task Editor &#40;Result Set Page&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span></span>  
 [<span data-ttu-id="4dd79-131">Referencia de Transact-SQL &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="4dd79-131">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
