---
title: Transformación Recuento de filas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rowcounttrans.f1
helpviewer_keywords:
- updating variables
- Row Count transformation
- number of rows
- variables [Integration Services], updating
- counting rows
ms.assetid: b68293b9-a68c-40be-9d81-77342da1be29
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b0940d608aeaa96b7ec43fa4486944ce0f887e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752310"
---
# <a name="row-count-transformation"></a><span data-ttu-id="90702-102">Recuento de filas, transformación</span><span class="sxs-lookup"><span data-stu-id="90702-102">Row Count Transformation</span></span>
  <span data-ttu-id="90702-103">La transformación Recuento de filas cuenta las filas a medida que pasan por un flujo de datos y almacena el recuento final en una variable.</span><span class="sxs-lookup"><span data-stu-id="90702-103">The Row Count transformation counts rows as they pass through a data flow and stores the final count in a variable.</span></span>  
  
 <span data-ttu-id="90702-104">Un paquete [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] puede usar recuentos de filas para actualizar las variables utilizadas en scripts, expresiones y expresiones de propiedades.</span><span class="sxs-lookup"><span data-stu-id="90702-104">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] package can use row counts to update the variables used in scripts, expressions, and property expressions.</span></span> <span data-ttu-id="90702-105">(Por ejemplo, la variable que almacena el número de filas puede actualizar el texto de un mensaje de correo electrónico para incluir el número de filas). La variable que se va a utilizar en la transformación Recuento de filas debe existir ya y debe estar dentro del ámbito de la tarea Flujo de datos a la que pertenece el flujo de datos con la transformación Recuento de filas.</span><span class="sxs-lookup"><span data-stu-id="90702-105">(For example, the variable that stores the row count can update the message text in an e-mail message to include the number of rows.) The variable that the Row Count transformation uses must already exist, and it must be in the scope of the Data Flow task to which the data flow with the Row Count transformation belongs.</span></span>  
  
 <span data-ttu-id="90702-106">La transformación almacena el valor del recuento de filas en la variable únicamente después de que la última fila ya ha pasado a través de ella.</span><span class="sxs-lookup"><span data-stu-id="90702-106">The transformation stores the row count value in the variable only after the last row has passed through the transformation.</span></span> <span data-ttu-id="90702-107">Por lo tanto, el valor de la variable no está actualizado en el momento en que el valor actualizado se va a usar en el flujo de datos que contiene la transformación Recuento de filas.</span><span class="sxs-lookup"><span data-stu-id="90702-107">Therefore, the value of the variable is not updated in time to use the updated value in the data flow that contains the Row Count transformation.</span></span> <span data-ttu-id="90702-108">Puede usar la variable actualizada en un flujo de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="90702-108">You can use the updated variable in a separate data flow.</span></span>  
  
 <span data-ttu-id="90702-109">Esta transformación tiene una entrada y una salida.</span><span class="sxs-lookup"><span data-stu-id="90702-109">This transformation has one input and one output.</span></span> <span data-ttu-id="90702-110">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="90702-110">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-row-count-transformation"></a><span data-ttu-id="90702-111">Configuración de la transformación Recuento de filas</span><span class="sxs-lookup"><span data-stu-id="90702-111">Configuration of the Row Count Transformation</span></span>  
 <span data-ttu-id="90702-112">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="90702-112">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="90702-113">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="90702-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="90702-114">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="90702-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="90702-115">Common Properties</span><span class="sxs-lookup"><span data-stu-id="90702-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="90702-116">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="90702-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="90702-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="90702-117">Related Tasks</span></span>  
 <span data-ttu-id="90702-118">Para obtener más información sobre cómo establecer las propiedades de este componente, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="90702-118">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90702-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="90702-119">See Also</span></span>  
 <span data-ttu-id="90702-120">[Variables de Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="90702-120">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="90702-121">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="90702-121">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="90702-122">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="90702-122">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
