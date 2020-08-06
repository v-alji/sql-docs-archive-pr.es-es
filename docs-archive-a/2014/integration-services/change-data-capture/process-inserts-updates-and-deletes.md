---
title: Procesar inserciones, actualizaciones y eliminaciones | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],processing data
ms.assetid: 13a84d21-2623-4efe-b442-4125a7a2d690
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67f016aaf4f7f83c0fa506966c4e78f5b8fadef6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663047"
---
# <a name="process-inserts-updates-and-deletes"></a><span data-ttu-id="f90a9-102">Procesar inserciones, actualizaciones y eliminaciones</span><span class="sxs-lookup"><span data-stu-id="f90a9-102">Process Inserts, Updates, and Deletes</span></span>
  <span data-ttu-id="f90a9-103">En el flujo de datos de un paquete de Integration Services que realiza una carga incremental de datos modificados, la segunda tarea consiste en separar las inserciones, las actualizaciones y las eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="f90a9-103">In the data flow of an Integration Services package that performs an incremental load of change data, the second task is to separate inserts, updates, and deletes.</span></span> <span data-ttu-id="f90a9-104">A continuación, puede utilizar los comandos adecuados para aplicarlos en el destino.</span><span class="sxs-lookup"><span data-stu-id="f90a9-104">Then, you can use appropriate commands to apply them to the destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f90a9-105">La primera tarea para diseñar el flujo de datos de un paquete que realiza una carga incremental de datos modificados consiste en configurar el componente de origen que ejecuta la consulta que recupera dichos datos.</span><span class="sxs-lookup"><span data-stu-id="f90a9-105">The first task in designing the data flow of a package that performs an incremental load of change data is to configure the source component that runs the query that retrieves the change data.</span></span> <span data-ttu-id="f90a9-106">Para obtener más información sobre este componente, vea [Recuperar y describir datos modificados](retrieve-and-understand-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="f90a9-106">For more information about this component, see [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md).</span></span> <span data-ttu-id="f90a9-107">Para obtener una descripción del proceso general de creación de un paquete que realiza una carga incremental de los datos modificados, vea [Captura de datos modificados &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="f90a9-107">For a description of the overall process for creating a package that performs an incremental load of change data, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="associating-friendly-values-to-separate-inserts-updates-and-deletes"></a><span data-ttu-id="f90a9-108">Asociar valores descriptivos para separar las inserciones, las actualizaciones y las eliminaciones</span><span class="sxs-lookup"><span data-stu-id="f90a9-108">Associating Friendly Values to Separate Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="f90a9-109">En la consulta de ejemplo que recupera los datos modificados, la función **cdc.fn_cdc_get_net_changes__<capture_instance>** solo devuelve la columna de metadatos denominada **__$operation**.</span><span class="sxs-lookup"><span data-stu-id="f90a9-109">In the example query that retrieves change data, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns only the column of metadata named **__$operation**.</span></span> <span data-ttu-id="f90a9-110">Esta columna de metadatos contiene un valor ordinal que indica la operación que ha causado el cambio.</span><span class="sxs-lookup"><span data-stu-id="f90a9-110">This metadata column contains an ordinal value that indicates which operation caused the change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f90a9-111">Para obtener más información sobre la consulta que usa llamadas a la función **cdc.fn_cdc_get_net_changes_ <capture_instance>** , vea [Crear la función para recuperar los datos modificados](create-the-function-to-retrieve-the-change-data.md).</span><span class="sxs-lookup"><span data-stu-id="f90a9-111">For more information about the query that uses calls the **cdc.fn_cdc_get_net_changes_<capture_instance>** function, see [Create the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md).</span></span>  
  
 <span data-ttu-id="f90a9-112">Hacer coincidir un valor ordinal con su operación correspondiente no es tan fácil como utilizar una tecla de acceso para la operación.</span><span class="sxs-lookup"><span data-stu-id="f90a9-112">Matching an ordinal value to its corresponding operation is not as easy as using a mnemonic of the operation.</span></span> <span data-ttu-id="f90a9-113">Por ejemplo, 'D' puede representar fácilmente una operación de eliminación e 'I' una operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="f90a9-113">For example, 'D' can easily represent a delete operation and 'I' represent an insert operation.</span></span> <span data-ttu-id="f90a9-114">La consulta de ejemplo que se creó en el tema, [Crear la función para recuperar los datos modificados](create-the-function-to-retrieve-the-change-data.md)realiza esta conversión de un valor ordinal a un valor de cadena descriptivo que se devuelve en una nueva columna.</span><span class="sxs-lookup"><span data-stu-id="f90a9-114">The example query that was created in the topic, [Creating the Function to Retrieve the Change Data](create-the-function-to-retrieve-the-change-data.md), makes this conversion from an ordinal value to a friendly string value that is returned in a new column.</span></span> <span data-ttu-id="f90a9-115">El segmento de código siguiente muestra esta conversión:</span><span class="sxs-lookup"><span data-stu-id="f90a9-115">The following segment of code shows this conversion:</span></span>  
  
```  
select   
    ...  
    case __$operation  
        when 1 then 'D'  
        when 2 then 'I'  
        when 4 then 'U'  
        else null  
     end as CDC_OPERATION  
```  
  
## <a name="configuring-a-conditional-split-transformation-to-direct-inserts-updates-and-deletes"></a><span data-ttu-id="f90a9-116">Configurar una transformación División condicional para dirigir las inserciones, las actualizaciones y las eliminaciones</span><span class="sxs-lookup"><span data-stu-id="f90a9-116">Configuring a Conditional Split Transformation to Direct Inserts, Updates, and Deletes</span></span>  
 <span data-ttu-id="f90a9-117">La transformación División condicional es idónea para dirigir filas de datos modificados a una de las tres salidas.</span><span class="sxs-lookup"><span data-stu-id="f90a9-117">To direct rows of change data to one of three outputs, the Conditional Split transformation is ideal.</span></span> <span data-ttu-id="f90a9-118">La transformación comprueba el valor de la columna **CDC_OPERATION** en cada fila y determina si el cambio fue una inserción, una actualización o una eliminación.</span><span class="sxs-lookup"><span data-stu-id="f90a9-118">The transformation just checks the value of the **CDC_OPERATION** column in each row and determines whether that change was an insert, update, or delete.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f90a9-119">La columna CDC_OPERATION contiene un valor de cadena descriptivo derivado del valor numérico de la columna **__$operation** .</span><span class="sxs-lookup"><span data-stu-id="f90a9-119">The CDC_OPERATION column contains a friendly string value derived from the numeric value in the **__$operation** column.</span></span>  
  
#### <a name="to-split-inserts-updates-and-deletes-for-processing-by-using-a-conditional-split-transformation"></a><span data-ttu-id="f90a9-120">Para dividir las inserciones, las actualizaciones y las eliminaciones para su procesamiento mediante una transformación División condicional</span><span class="sxs-lookup"><span data-stu-id="f90a9-120">To split inserts, updates, and deletes for processing by using a Conditional Split transformation</span></span>  
  
1.  <span data-ttu-id="f90a9-121">En la pestaña **Flujo de datos** , agregue una transformación División condicional.</span><span class="sxs-lookup"><span data-stu-id="f90a9-121">On the **Data Flow** tab, add a Conditional Split transformation.</span></span>  
  
2.  <span data-ttu-id="f90a9-122">Conecte la salida del origen de OLE DB a la transformación División condicional.</span><span class="sxs-lookup"><span data-stu-id="f90a9-122">Connect the output of the OLE DB source to the Conditional Split transformation.</span></span>  
  
3.  <span data-ttu-id="f90a9-123">En el **Editor de transformación División condicional**, en el panel inferior del editor, escriba las tres líneas siguientes para designar las tres salidas.</span><span class="sxs-lookup"><span data-stu-id="f90a9-123">In the **Conditional Split Transformation Editor**, in the lower pane of the editor, enter the following three lines to designate the three outputs</span></span>  
  
    1.  <span data-ttu-id="f90a9-124">Para las inserciones, escriba una línea con la condición `CDC_OPERATION == "I"` que dirija las filas insertadas a la salida.</span><span class="sxs-lookup"><span data-stu-id="f90a9-124">Enter a line with the condition `CDC_OPERATION == "I"` to direct inserted rows to the output for inserts.</span></span>  
  
    2.  <span data-ttu-id="f90a9-125">Para las actualizaciones, escriba una línea con la condición `CDC_OPERATION == "U"` que dirija las filas actualizadas a la salida.</span><span class="sxs-lookup"><span data-stu-id="f90a9-125">Enter a line with the condition `CDC_OPERATION == "U"` to direct updated rows to the output for updates.</span></span>  
  
    3.  <span data-ttu-id="f90a9-126">Para las eliminaciones, escriba una línea con la condición `CDC_OPERATION == "D"` que dirija las filas eliminadas a la salida.</span><span class="sxs-lookup"><span data-stu-id="f90a9-126">Enter a line with the condition `CDC_OPERATION == "D"` to direct deleted rows to the output for deletes.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f90a9-127">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="f90a9-127">Next Step</span></span>  
 <span data-ttu-id="f90a9-128">Una vez divididas las filas para su procesamiento, el paso siguiente consiste en aplicar los cambios en el destino.</span><span class="sxs-lookup"><span data-stu-id="f90a9-128">After you split the rows for processing, the next step is to apply the changes to the destination.</span></span>  
  
 <span data-ttu-id="f90a9-129">**Tema siguiente:** [Aplicar los cambios al destino](apply-the-changes-to-the-destination.md)</span><span class="sxs-lookup"><span data-stu-id="f90a9-129">**Next topic:** [Apply the Changes to the Destination](apply-the-changes-to-the-destination.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f90a9-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f90a9-130">See Also</span></span>  
 <span data-ttu-id="f90a9-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="f90a9-131">[Conditional Split Transformation](../data-flow/transformations/conditional-split-transformation.md) </span></span>  
 [<span data-ttu-id="f90a9-132">División de un conjunto de datos con la transformación División condicional</span><span class="sxs-lookup"><span data-stu-id="f90a9-132">Split a Dataset by Using the Conditional Split Transformation</span></span>](../data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
