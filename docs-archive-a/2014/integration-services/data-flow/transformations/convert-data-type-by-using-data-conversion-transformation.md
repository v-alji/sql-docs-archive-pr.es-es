---
title: Convertir datos en un tipo de datos diferente mediante la transformación conversión de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: 4aabbe4f-7666-4672-865a-9627bd25fbfd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 878741717c36c18e9a069c62e86be0148272239f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674235"
---
# <a name="convert-data-to-a-different-data-type-by-using-the-data-conversion-transformation"></a><span data-ttu-id="b71f8-102">Convertir datos en un tipo de datos diferente mediante la transformación Conversión de datos</span><span class="sxs-lookup"><span data-stu-id="b71f8-102">Convert Data to a Different Data Type by Using the Data Conversion Transformation</span></span>
  <span data-ttu-id="b71f8-103">Para agregar y configurar una transformación Conversión de datos, el paquete ya debe incluir por lo menos una tarea Flujo de datos y un origen.</span><span class="sxs-lookup"><span data-stu-id="b71f8-103">To add and configure a Data Conversion transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-convert-data-to-a-different-data-type"></a><span data-ttu-id="b71f8-104">Para convertir datos en un tipo de datos diferente</span><span class="sxs-lookup"><span data-stu-id="b71f8-104">To convert data to a different data type</span></span>  
  
1.  <span data-ttu-id="b71f8-105">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="b71f8-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b71f8-106">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="b71f8-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b71f8-107">Haga clic en la pestaña **Flujo de datos** , y luego, desde el **cuadro de herramientas**, arrastre la transformación Conversión de datos a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="b71f8-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Data Conversion transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="b71f8-108">Conecte la transformación Conversión de datos al flujo de datos arrastrando el conector desde el origen o la transformación anterior a la transformación Conversión de datos.</span><span class="sxs-lookup"><span data-stu-id="b71f8-108">Connect the Data Conversion transformation to the data flow by dragging a connector from the source or the previous transformation to the Data Conversion transformation.</span></span>  
  
5.  <span data-ttu-id="b71f8-109">Haga doble clic en la transformación Conversión de datos.</span><span class="sxs-lookup"><span data-stu-id="b71f8-109">Double-click the Data Conversion transformation.</span></span>  
  
6.  <span data-ttu-id="b71f8-110">En el cuadro de diálogo **Editor de transformación Conversión de datos** , en la tabla **Columnas de entrada disponibles** , active la casilla que aparece junto a las columnas cuyo tipo de datos quiere convertir.</span><span class="sxs-lookup"><span data-stu-id="b71f8-110">In the **Data ConversionTransformation Editor** dialog box, in the **Available Input Columns** table, select the check box next to the columns whose data type you want to convert.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b71f8-111">Puede aplicar varias conversiones de datos a una columna de entrada.</span><span class="sxs-lookup"><span data-stu-id="b71f8-111">You can apply multiple data conversions to an input column.</span></span>  
  
7.  <span data-ttu-id="b71f8-112">Opcionalmente, modifique los valores predeterminados en la columna **Alias de salida** .</span><span class="sxs-lookup"><span data-stu-id="b71f8-112">Optionally, modify the default values in the **Output Alias** column.</span></span>  
  
8.  <span data-ttu-id="b71f8-113">En la lista **Tipo de datos** , seleccione el nuevo tipo de datos para la columna.</span><span class="sxs-lookup"><span data-stu-id="b71f8-113">In the **Data Type** list, select the new data type for the column.</span></span> <span data-ttu-id="b71f8-114">El tipo de datos predeterminado es el tipo de datos de la columna de entrada.</span><span class="sxs-lookup"><span data-stu-id="b71f8-114">The default data type is the data type of the input column.</span></span>  
  
9. <span data-ttu-id="b71f8-115">Opcionalmente, según el tipo de datos seleccionado, actualice los valores en las columnas **Longitud**, **Precisión**, **Escala**, y **Página de códigos** .</span><span class="sxs-lookup"><span data-stu-id="b71f8-115">Optionally, depending on the selected data type, update the values in the **Length**, the **Precision**, the **Scale**, and the **Code Page** columns.</span></span>  
  
10. <span data-ttu-id="b71f8-116">Para configurar la salida de error, haga clic en **Configurar la salida de errores**.</span><span class="sxs-lookup"><span data-stu-id="b71f8-116">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="b71f8-117">Para más información, vea [Configurar una salida de error en un componente de flujo de datos](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="b71f8-117">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="b71f8-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="b71f8-118">Click **OK**.</span></span>  
  
12. <span data-ttu-id="b71f8-119">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="b71f8-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b71f8-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b71f8-120">See Also</span></span>  
 <span data-ttu-id="b71f8-121">[Data Conversion Transformation](data-conversion-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="b71f8-121">[Data Conversion Transformation](data-conversion-transformation.md) </span></span>  
 <span data-ttu-id="b71f8-122">[Transformaciones de Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="b71f8-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="b71f8-123">[Rutas de Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="b71f8-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="b71f8-124">[Tipos de datos de Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="b71f8-124">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 [<span data-ttu-id="b71f8-125">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="b71f8-125">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
