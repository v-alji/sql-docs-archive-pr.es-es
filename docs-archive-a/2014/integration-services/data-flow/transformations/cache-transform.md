---
title: Transformación de caché | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.cachetrans.f1
helpviewer_keywords:
- Cache transform
ms.assetid: a5683fc8-9c32-4634-819e-e9815627e4f1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34be3252a3caf344c95e13ae45cc485a8c4ffdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674241"
---
# <a name="cache-transform"></a><span data-ttu-id="6ef24-102">Transformación de caché</span><span class="sxs-lookup"><span data-stu-id="6ef24-102">Cache Transform</span></span>
  <span data-ttu-id="6ef24-103">La transformación de caché genera un conjunto de datos de referencia para la transformación de búsqueda escribiendo datos de un origen de datos conectado del flujo de datos en un Administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="6ef24-103">The Cache Transform transformation generates a reference dataset for the Lookup Transformation by writing data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="6ef24-104">La transformación Búsqueda realiza búsquedas mediante la combinación de datos de las columnas de entrada procedentes de un origen de datos conectado con columnas de la base de datos de referencia.</span><span class="sxs-lookup"><span data-stu-id="6ef24-104">The Lookup transformation performs lookups by joining data in input columns from a connected data source with columns in the reference database.</span></span>  
  
 <span data-ttu-id="6ef24-105">Puede usar el Administrador de conexiones de caché si desea configurar la transformación Búsqueda para que se ejecute en modo de caché completa.</span><span class="sxs-lookup"><span data-stu-id="6ef24-105">You can use the Cache connection manager when you want to configure the Lookup Transformation to run in the full cache mode.</span></span> <span data-ttu-id="6ef24-106">En este modo, el conjunto de datos de referencia se carga en la memoria caché antes de que se ejecute la transformación Búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6ef24-106">In this mode, the reference dataset is loaded into cache before the Lookup Transformation runs.</span></span>  
  
 <span data-ttu-id="6ef24-107">Para obtener instrucciones sobre cómo configurar la transformación Búsqueda en modo de caché completa con el Administrador de conexiones de caché y la transformación de caché, vea [Implementar una transformación de búsqueda en el modo de caché completa mediante el Administrador de conexiones de caché](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6ef24-107">For instructions on how to configure the Lookup transformation in full cache mode with the Cache connection manager and Cache Transform transformation, see [Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager](../../connection-manager/lookup-transformation-full-cache-mode-ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="6ef24-108">Para obtener más información acerca del almacenamiento en memoria caché del conjunto de datos de referencia, vea [Lookup Transformation](lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="6ef24-108">For more information on caching the reference dataset, see [Lookup Transformation](lookup-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6ef24-109">La transformación de caché solo escribe filas únicas en el administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="6ef24-109">The Cache Transform writes only unique rows to the Cache connection manager.</span></span>  
  
 <span data-ttu-id="6ef24-110">En un paquete único, solo una transformación de caché puede escribir datos en el mismo administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="6ef24-110">In a single package, only one Cache Transform can write data to the same Cache connection manager.</span></span> <span data-ttu-id="6ef24-111">Si el paquete contiene varias transformaciones de caché, la primera transformación de caché a la que se llama cuando se ejecuta el paquete escribe los datos en el administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="6ef24-111">If the package contains multiple Cache Transforms, the first Cache Transform that is called when the package runs, writes the data to the connection manager.</span></span> <span data-ttu-id="6ef24-112">Las operaciones de escritura de las transformaciones de caché posteriores producirán errores.</span><span class="sxs-lookup"><span data-stu-id="6ef24-112">The write operations of subsequent Cache Transforms fail.</span></span>  
  
 <span data-ttu-id="6ef24-113">Para obtener más información, consulte [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) y [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6ef24-113">For more information, see [Cache Connection Manager](../../connection-manager/cache-connection-manager.md) and [Cache Connection Manager Editor](../../cache-connection-manager-editor.md).</span></span>  
  
## <a name="configuration-of-the-cache-transform"></a><span data-ttu-id="6ef24-114">Configuración de la transformación de caché</span><span class="sxs-lookup"><span data-stu-id="6ef24-114">Configuration of the Cache Transform</span></span>  
 <span data-ttu-id="6ef24-115">Puede configurar el administrador de conexiones de caché para guardar los datos en un archivo caché (.caw).</span><span class="sxs-lookup"><span data-stu-id="6ef24-115">You can configure the Cache connection manager to save the data to a cache file (.caw).</span></span>  
  
 <span data-ttu-id="6ef24-116">Puede configurar la transformación de caché de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="6ef24-116">You can configure the Cache Transform in the following ways:</span></span>  
  
-   <span data-ttu-id="6ef24-117">Especificar el administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="6ef24-117">Specify the Cache connection manager.</span></span>  
  
-   <span data-ttu-id="6ef24-118">Asignar columnas de entrada de la transformación de caché a columnas de destino del administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="6ef24-118">Map the input columns in the Cache Transform to destination columns in the Cache connection manager.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ef24-119">Cada columna de entrada debe estar asignada a una columna de destino y los tipos de datos de columna deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="6ef24-119">Each input column must be mapped to a destination column, and the column data types must match.</span></span> <span data-ttu-id="6ef24-120">De lo contrario, el Diseñador [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="6ef24-120">Otherwise, [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer displays an error message.</span></span>  
  
     <span data-ttu-id="6ef24-121">Puede utilizar el **Editor del administrador de conexiones de caché** para modificar tipos de datos y nombres de columna, y otras propiedades de columna.</span><span class="sxs-lookup"><span data-stu-id="6ef24-121">You can use the **Cache Connection Manager Editor** to modify column data types, names, and other column properties.</span></span>  
  
 <span data-ttu-id="6ef24-122">Puede establecer propiedades a través del Diseñador [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ef24-122">You can set properties through [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Designer.</span></span> <span data-ttu-id="6ef24-123">Para obtener más información acerca de las propiedades que se pueden establecer en el cuadro de diálogo **Editor avanzado** , vea [Transformation Custom Properties](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="6ef24-123">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="6ef24-124">Para más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="6ef24-124">For more information about how to set properties, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef24-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6ef24-125">See Also</span></span>  
 <span data-ttu-id="6ef24-126">[Transformaciones de Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="6ef24-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 [<span data-ttu-id="6ef24-127">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="6ef24-127">Data Flow</span></span>](../data-flow.md)  
  
  
