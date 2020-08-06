---
title: Transformación Copiar columna | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copycolumntrans.f1
helpviewer_keywords:
- columns [Integration Services], copying
- copying columns
- Copy Column transformation
ms.assetid: 1c72a313-9026-46bc-a57f-c6b3f47346f8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fd2745070a92ab71e89f3bfa9edd8673b676632b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674233"
---
# <a name="copy-column-transformation"></a><span data-ttu-id="7c844-102">Copiar columna, transformación</span><span class="sxs-lookup"><span data-stu-id="7c844-102">Copy Column Transformation</span></span>
  <span data-ttu-id="7c844-103">La transformación Copiar columna crea columnas nuevas copiando columnas de entrada y agregando las columnas nuevas a la salida de transformación.</span><span class="sxs-lookup"><span data-stu-id="7c844-103">The Copy Column transformation creates new columns by copying input columns and adding the new columns to the transformation output.</span></span> <span data-ttu-id="7c844-104">En una fase posterior del flujo de datos se pueden aplicar distintas transformaciones a las copias de columnas.</span><span class="sxs-lookup"><span data-stu-id="7c844-104">Later in the data flow, different transformations can be applied to the column copies.</span></span> <span data-ttu-id="7c844-105">Por ejemplo, puede usar la transformación Copiar columna para crear una copia de una columna y después convertir los datos copiados a mayúsculas mediante la transformación Mapa de caracteres, o aplicar agregaciones a la nueva columna mediante la transformación Agregado.</span><span class="sxs-lookup"><span data-stu-id="7c844-105">For example, you can use the Copy Column transformation to create a copy of a column and then convert the copied data to uppercase characters by using the Character Map transformation, or apply aggregations to the new column by using the Aggregate transformation.</span></span>  
  
## <a name="configuration-of-the-copy-column-transformation"></a><span data-ttu-id="7c844-106">Configuración de la transformación Copiar columna</span><span class="sxs-lookup"><span data-stu-id="7c844-106">Configuration of the Copy Column Transformation</span></span>  
 <span data-ttu-id="7c844-107">Puede configurar la transformación Copiar columna especificando las columnas de entrada que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="7c844-107">You configure the Copy Column transformation by specifying the input columns to copy.</span></span> <span data-ttu-id="7c844-108">Puede crear varias copias de una columna o crear copias de varias columnas en una operación.</span><span class="sxs-lookup"><span data-stu-id="7c844-108">You can create multiple copies of a column, or create copies of multiple columns in one operation.</span></span>  
  
 <span data-ttu-id="7c844-109">Esta transformación tiene una entrada y una salida.</span><span class="sxs-lookup"><span data-stu-id="7c844-109">This transformation has one input and one output.</span></span> <span data-ttu-id="7c844-110">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="7c844-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="7c844-111">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7c844-111">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="7c844-112">Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Copiar columna** , vea [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="7c844-112">For more information about the properties that you can set in the **Copy Column Transformation Editor** dialog box, see [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="7c844-113">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7c844-113">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="7c844-114">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7c844-114">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="7c844-115">Common Properties</span><span class="sxs-lookup"><span data-stu-id="7c844-115">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="7c844-116">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="7c844-116">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="7c844-117">Para más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="7c844-117">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c844-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c844-118">See Also</span></span>  
 <span data-ttu-id="7c844-119">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="7c844-119">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="7c844-120">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="7c844-120">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
