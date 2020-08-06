---
title: Transformación Anulación de dinamización | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unpivottrans.f1
helpviewer_keywords:
- Unpivot transformation
- more normalized data set [Integration Services]
- normalized data [Integration Services]
- datasets [Integration Services], normalized data
ms.assetid: f635c64b-a9c5-4f11-9c40-9cd9d5298c5d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e605dc4827a885b5dc65fbb680cce8a434b89fd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676076"
---
# <a name="unpivot-transformation"></a><span data-ttu-id="d39ae-102">Anulación de dinamización, transformación</span><span class="sxs-lookup"><span data-stu-id="d39ae-102">Unpivot Transformation</span></span>
  <span data-ttu-id="d39ae-103">La transformación Anulación de dinamización transforma un conjunto de datos sin normalizar en una versión más normalizada ampliando los valores de varias columnas de un solo registro en varios registros con los mismos valores en una sola columna.</span><span class="sxs-lookup"><span data-stu-id="d39ae-103">The Unpivot transformation makes an unnormalized dataset into a more normalized version by expanding values from multiple columns in a single record into multiple records with the same values in a single column.</span></span> <span data-ttu-id="d39ae-104">Por ejemplo, un conjunto de datos que enumera nombres de clientes tiene una fila para cada cliente, con los productos y la cantidad comprada en columnas dentro de la fila.</span><span class="sxs-lookup"><span data-stu-id="d39ae-104">For example, a dataset that lists customer names has one row for each customer, with the products and the quantity purchased shown in columns in the row.</span></span> <span data-ttu-id="d39ae-105">Después de que la transformación Anulación de dinamización normaliza el conjunto de datos, el conjunto de datos contiene una fila diferente para cada producto que compró el cliente.</span><span class="sxs-lookup"><span data-stu-id="d39ae-105">After the Unpivot transformation normalizes the data set, the data set contains a different row for each product that the customer purchased.</span></span>  
  
 <span data-ttu-id="d39ae-106">El diagrama siguiente muestra un conjunto de datos antes de que se anule la dinamización de los datos en la columna Product.</span><span class="sxs-lookup"><span data-stu-id="d39ae-106">The following diagram shows a data set before the data is unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="d39ae-107">![Conjunto de datos después de que se anule la dinamización](../../media/mw-dts-18.gif "Conjunto de datos después de que se anule la dinamización")</span><span class="sxs-lookup"><span data-stu-id="d39ae-107">![Dataset after it is unpivoted](../../media/mw-dts-18.gif "Dataset after it is unpivoted")</span></span>  
  
 <span data-ttu-id="d39ae-108">El diagrama siguiente muestra un conjunto de datos después de que se haya anulado la dinamización de los datos en la columna Product.</span><span class="sxs-lookup"><span data-stu-id="d39ae-108">The following diagram shows a data set after it has been unpivoted on the Product column.</span></span>  
  
 <span data-ttu-id="d39ae-109">![Conjunto de datos antes de que se anule la dinamización](../../media/mw-dts-17.gif "Conjunto de datos antes de que se anule la dinamización")</span><span class="sxs-lookup"><span data-stu-id="d39ae-109">![Dataset before it is unpivoted](../../media/mw-dts-17.gif "Dataset before it is unpivoted")</span></span>  
  
 <span data-ttu-id="d39ae-110">En algunas circunstancias, los resultados de anulación de dinamización pueden contener filas con valores no esperados.</span><span class="sxs-lookup"><span data-stu-id="d39ae-110">Under some circumstances, the unpivot results may contain rows with unexpected values.</span></span> <span data-ttu-id="d39ae-111">Por ejemplo, si los datos de muestra del diagrama en los que se va a anular la dinamización tuvieran valores NULL en todas las columnas Qty para Fred, el resultado incluiría solamente una fila para Fred, no cinco.</span><span class="sxs-lookup"><span data-stu-id="d39ae-111">For example, if the sample data to unpivot shown in the diagram had null values in all the Qty columns for Fred, then the output would include only one row for Fred, not five.</span></span> <span data-ttu-id="d39ae-112">La columna Qty contendría NULL o cero, dependiendo del tipo de datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="d39ae-112">The Qty column would contain either null or zero, depending on the column data type.</span></span>  
  
## <a name="configuration-of-the-unpivot-transformation"></a><span data-ttu-id="d39ae-113">Configuración de la transformación Anulación de dinamización</span><span class="sxs-lookup"><span data-stu-id="d39ae-113">Configuration of the Unpivot Transformation</span></span>  
 <span data-ttu-id="d39ae-114">La transformación Anulación de dinamización incluye la propiedad personalizada `PivotKeyValue`.</span><span class="sxs-lookup"><span data-stu-id="d39ae-114">The Unpivot transformation includes the `PivotKeyValue` custom property.</span></span> <span data-ttu-id="d39ae-115">Esta propiedad se puede actualizar a través de una expresión de propiedad, al cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="d39ae-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="d39ae-116">Para más información, vea [Expresiones de Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md), [Usar expresiones de propiedad en paquetes](../../expressions/use-property-expressions-in-packages.md) y [Propiedades personalizadas de transformación](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d39ae-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md), and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="d39ae-117">Esta transformación tiene una entrada y una salida.</span><span class="sxs-lookup"><span data-stu-id="d39ae-117">This transformation has one input and one output.</span></span> <span data-ttu-id="d39ae-118">No tiene ninguna salida de error.</span><span class="sxs-lookup"><span data-stu-id="d39ae-118">It has no error output.</span></span>  
  
 <span data-ttu-id="d39ae-119">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="d39ae-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="d39ae-120">Para obtener más información sobre las propiedades que se pueden configurar en el cuadro de diálogo **Editor de transformación Anulación de dinamización** , haga clic en uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="d39ae-120">For more information about the properties that you can set in the **Unpivot Transformation Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d39ae-121">Editor de transformación Anulación de dinamización</span><span class="sxs-lookup"><span data-stu-id="d39ae-121">Unpivot Transformation Editor</span></span>](../../unpivot-transformation-editor.md)  
  
 <span data-ttu-id="d39ae-122">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d39ae-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d39ae-123">Common Properties</span><span class="sxs-lookup"><span data-stu-id="d39ae-123">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="d39ae-124">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="d39ae-124">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="d39ae-125">Para más información sobre cómo establecer las propiedades, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="d39ae-125">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
  
