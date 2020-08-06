---
title: Extraer datos mediante el origen de XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], XML
- XML source [Integration Services]
ms.assetid: 5d5be54c-2b7e-4957-9193-c5ea5c5d6d15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57758353c476badfba4cb12a1ef6b5101f16735d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751326"
---
# <a name="extract-data-by-using-the-xml-source"></a><span data-ttu-id="78b33-102">Extraer datos mediante el origen de XML</span><span class="sxs-lookup"><span data-stu-id="78b33-102">Extract Data by Using the XML Source</span></span>
  <span data-ttu-id="78b33-103">Para agregar y configurar un origen XML, el paquete ya debe incluir por lo menos una tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="78b33-103">To add and configure an XML source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-xml-source"></a><span data-ttu-id="78b33-104">Para extraer datos mediante un origen XML</span><span class="sxs-lookup"><span data-stu-id="78b33-104">To extract data using an XML source</span></span>  
  
1.  <span data-ttu-id="78b33-105">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="78b33-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="78b33-106">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="78b33-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="78b33-107">Haga clic en la pestaña **Flujo de datos** y, a continuación, desde el **cuadro de herramientas**, arrastre el origen XML a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="78b33-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the XML source to the design surface.</span></span>  
  
4.  <span data-ttu-id="78b33-108">Haga doble clic en el origen XML.</span><span class="sxs-lookup"><span data-stu-id="78b33-108">Double-click the XML source.</span></span>  
  
5.  <span data-ttu-id="78b33-109">En el **Editor de origen de XML**, en la página **Administrador de conexiones** , seleccione un modo de acceso de datos:</span><span class="sxs-lookup"><span data-stu-id="78b33-109">In the **XML Source Editor**, on the **Connection Manager** page, select a data access mode:</span></span>  
  
    -   <span data-ttu-id="78b33-110">Para ir al modo de acceso **Ubicación del archivo XML** , haga clic en **Examinar** y ubique la carpeta que contiene el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="78b33-110">For the **XML file location** access mode, click **Browse** and locate the folder that contains the XML file.</span></span>  
  
    -   <span data-ttu-id="78b33-111">Para ir al modo de acceso **Archivo XML de variable** , seleccione la variable definida por el usuario que contiene la ruta del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="78b33-111">For the **XML file from variable** access mode, select the user-defined variable that contains the path of the XML file.</span></span>  
  
    -   <span data-ttu-id="78b33-112">Para ir al modo de acceso **Datos XML de variable** , seleccione la variable definida por el usuario que contiene los datos XML.</span><span class="sxs-lookup"><span data-stu-id="78b33-112">For the **XML data from variable** access mode, select the user-defined variable that contains the XML data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="78b33-113">Las variables se deben definir en el ámbito de la tarea Flujo de datos que contiene el origen XML, o en el ámbito del paquete. Además, la variable debe tener un tipo de datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="78b33-113">The variables must be defined in the scope of the Data Flow task that contains the XML source, or in the scope of the package; additionally, the variable must have a string data type.</span></span>  
  
6.  <span data-ttu-id="78b33-114">Opcionalmente, seleccione **Utilizar esquema insertado** para indicar que el documento XML incluye información de esquema.</span><span class="sxs-lookup"><span data-stu-id="78b33-114">Optionally, select **Use inline schema** to indicate that the XML document includes schema information.</span></span>  
  
7.  <span data-ttu-id="78b33-115">Para especificar un lenguaje externo de definición de Esquema XML (XSD) para el archivo XML, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="78b33-115">To specify an external XML Schema definition language (XSD) schema for the XML file, do one of the following:</span></span>  
  
    -   <span data-ttu-id="78b33-116">Haga clic en **Examinar** para buscar un archivo XSD existente.</span><span class="sxs-lookup"><span data-stu-id="78b33-116">Click **Browse** to locate an existing XSD file.</span></span>  
  
    -   <span data-ttu-id="78b33-117">Haga clic en **Generar XSD** para crear un XSD a partir del archivo XML.</span><span class="sxs-lookup"><span data-stu-id="78b33-117">Click **Generate XSD** to create an XSD from the XML file.</span></span>  
  
8.  <span data-ttu-id="78b33-118">Para actualizar los nombres de las columnas de salida, haga clic en **Columnas** y modifique los valores en la lista **Columna de salida** .</span><span class="sxs-lookup"><span data-stu-id="78b33-118">To update the names of output columns, click **Columns** and edit the values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="78b33-119">Para configurar la salida de error, haga clic en **Salida de error**.</span><span class="sxs-lookup"><span data-stu-id="78b33-119">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="78b33-120">Para más información, vea [Configurar una salida de error en un componente de flujo de datos](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="78b33-120">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="78b33-121">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="78b33-121">Click **OK**.</span></span>  
  
11. <span data-ttu-id="78b33-122">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="78b33-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b33-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78b33-123">See Also</span></span>  
 <span data-ttu-id="78b33-124">[Origen XML](xml-source.md) </span><span class="sxs-lookup"><span data-stu-id="78b33-124">[XML Source](xml-source.md) </span></span>  
 <span data-ttu-id="78b33-125">[Transformaciones de Integration Services](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="78b33-125">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="78b33-126">[Rutas de Integration Services](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="78b33-126">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="78b33-127">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="78b33-127">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
