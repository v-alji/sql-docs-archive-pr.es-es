---
title: Administrador de conexiones de caché | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Cache connection manager
ms.assetid: bdc92038-3720-4795-8a5c-79b963f2c952
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b8a7cc8bbe9e93c385fca6257e0be2e79bd3148a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673210"
---
# <a name="cache-connection-manager"></a><span data-ttu-id="f3a6e-102">Administrador de conexiones de caché</span><span class="sxs-lookup"><span data-stu-id="f3a6e-102">Cache Connection Manager</span></span>
  <span data-ttu-id="f3a6e-103">El administrador de conexiones de caché lee datos a partir de la transformación de caché o de un archivo caché (.caw) y puede guardar los datos en un archivo caché.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-103">The Cache connection manager reads data from the Cache transform or from a cache file (.caw), and can save the data to a cache file.</span></span> <span data-ttu-id="f3a6e-104">Si configura el administrador de conexiones de caché para que utilice un archivo caché, los datos siempre se almacenan en memoria.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-104">Whether you configure the Cache connection manager to use a cache file, the data is always stored in memory.</span></span>  
  
 <span data-ttu-id="f3a6e-105">La transformación de caché escribe los datos procedentes de un origen de datos conectado del flujo de datos en un administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-105">The Cache Transform transformation writes data from a connected data source in the data flow to a Cache connection manager.</span></span> <span data-ttu-id="f3a6e-106">La transformación Búsqueda de un paquete realiza búsquedas en los datos.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-106">The Lookup transformation in a package performs lookups on the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3a6e-107">El administrador de conexiones de caché no admite los tipos de datos de objetos binarios grandes (BLOB) DT_TEXT, DT_NTEXT y DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-107">The Cache connection manager does not support the Binary Large Object (BLOB) data types DT_TEXT, DT_NTEXT, and DT_IMAGE.</span></span> <span data-ttu-id="f3a6e-108">Si el conjunto de datos de referencia contiene un tipo de datos BLOB, se producirá un error en el componente al ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-108">If the reference dataset contains a BLOB data type, the component will fail when you run the package.</span></span> <span data-ttu-id="f3a6e-109">Puede utilizar el **Editor del administrador de conexiones de caché** para modificar los tipos de datos de columna.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-109">You can use the **Cache Connection Manager Editor** to modify column data types.</span></span> <span data-ttu-id="f3a6e-110">Para obtener más información, vea [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f3a6e-110">For more information, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3a6e-111">El nivel de protección del paquete no se aplica al archivo caché.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-111">The protection level of the package does not apply to the cache file.</span></span> <span data-ttu-id="f3a6e-112">Si el archivo caché contiene información confidencial, utilice una lista de control de acceso (ACL) para restringir el acceso a la ubicación o carpeta en la que almacena el archivo.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-112">If the cache file contains sensitive information, use an access control list (ACL) to restrict access to the location or folder in which you store the file.</span></span> <span data-ttu-id="f3a6e-113">Solo debería permitir el acceso a ciertas cuentas.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-113">You should enable access only to certain accounts.</span></span> <span data-ttu-id="f3a6e-114">Para más información, vea [Acceso a los archivos usados por los paquetes](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f3a6e-114">For more information, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
## <a name="configuration-of-the-cache-connection-manager"></a><span data-ttu-id="f3a6e-115">Configuración del administrador de conexiones de caché</span><span class="sxs-lookup"><span data-stu-id="f3a6e-115">Configuration of the Cache Connection Manager</span></span>  
 <span data-ttu-id="f3a6e-116">Puede configurar el administrador de conexiones de caché de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="f3a6e-116">You can configure the Cache connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="f3a6e-117">Indicar si se ha de utilizar un archivo caché.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-117">Indicate whether to use a cache file.</span></span>  
  
     <span data-ttu-id="f3a6e-118">Si configura el administrador de conexiones de caché para utilizar un archivo caché, el administrador de conexiones realizará una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="f3a6e-118">If you configure the cache connection manager to use a cache file, the connection manager will do one of the following actions:</span></span>  
  
    -   <span data-ttu-id="f3a6e-119">Guardar los datos en el archivo cuando se haya configurado una transformación de caché para escribir los datos procedentes de un origen de datos del flujo de datos en el administrador de conexiones de caché.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-119">Save data to the file when a Cache Transform transformation is configured to write data from a data source in the data flow to the Cache connection manager.</span></span>  
  
    -   <span data-ttu-id="f3a6e-120">Leer los datos desde el archivo caché.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-120">Read data from the cache file.</span></span>  
  
     <span data-ttu-id="f3a6e-121">Para obtener más información, vea [Cache Transform](../data-flow/transformations/cache-transform.md).</span><span class="sxs-lookup"><span data-stu-id="f3a6e-121">For more information, see [Cache Transform](../data-flow/transformations/cache-transform.md).</span></span>  
  
-   <span data-ttu-id="f3a6e-122">Cambiar los metadatos de las columnas almacenadas en la caché.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-122">Change metadata for the columns stored in the cache.</span></span>  
  
-   <span data-ttu-id="f3a6e-123">Actualizar el nombre del archivo caché en tiempo de ejecución con una expresión para establecer la propiedad ConnectionString.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-123">Update the cache file name at runtime by using an expression to set the ConnectionString property.</span></span> <span data-ttu-id="f3a6e-124">Para más información, vea [Usar expresiones de propiedad en paquetes](../expressions/use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f3a6e-124">For more information, see [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md).</span></span>  
  
 <span data-ttu-id="f3a6e-125">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f3a6e-125">You can set properties through [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="f3a6e-126">Para obtener más información acerca de las propiedades que puede configurar en el Diseñador [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , vea [Editor del administrador de conexiones de caché](../cache-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="f3a6e-126">For more information about the properties that you can set in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Designer, see [Cache Connection Manager Editor](../cache-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="f3a6e-127">Para obtener más información sobre cómo configurar un administrador de conexiones mediante programación, vea <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> y [Agregar conexiones mediante programación](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="f3a6e-127">For information about how to configure a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="f3a6e-128">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="f3a6e-128">Related Tasks</span></span>  
 [<span data-ttu-id="f3a6e-129">Implementar una transformación de búsqueda en el modo de caché completa mediante el Administrador de conexiones de caché</span><span class="sxs-lookup"><span data-stu-id="f3a6e-129">Implement a Lookup Transformation in Full Cache Mode Using the Cache Connection Manager</span></span>](lookup-transformation-full-cache-mode-ole-db-connection-manager.md)  
  
  
