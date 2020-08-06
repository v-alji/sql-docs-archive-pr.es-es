---
title: Procesamiento de los resultados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, results processing
- OLE DB, processing results
- rowsets [SQL Server], results processing
- results [SQL Server Native Client]
ms.assetid: 20887ac4-f649-4e7f-92e6-f929e2e70952
author: rothja
ms.author: jroth
ms.openlocfilehash: b9e5bf00b4d2e554536c9f2ba1a328390b93a8a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675825"
---
# <a name="processing-results"></a><span data-ttu-id="7a760-102">Procesar los resultados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="7a760-102">Processing Results</span></span>
  <span data-ttu-id="7a760-103">Si se crea un objeto de conjunto de filas por la ejecución de un comando o por la generación de un objeto de conjunto de filas directamente del proveedor, el consumidor necesita recuperar y tener acceso a los datos del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="7a760-103">If a rowset object is produced by either the execution of a command or the generation of a rowset object directly from the provider, the consumer needs to retrieve and access data in the rowset.</span></span>  
  
 <span data-ttu-id="7a760-104">Los conjuntos de filas son los objetos centrales que habilitan al proveedor OLE DB de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client para exponer los datos en formato tabular.</span><span class="sxs-lookup"><span data-stu-id="7a760-104">Rowsets are the central objects that enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider to expose data in tabular form.</span></span> <span data-ttu-id="7a760-105">Conceptualmente, un conjunto de filas es un conjunto de filas en las que cada fila tiene datos de columna.</span><span class="sxs-lookup"><span data-stu-id="7a760-105">Conceptually, a rowset is a set of rows in which each row has column data.</span></span> <span data-ttu-id="7a760-106">Un objeto de conjunto de filas expone interfaces como **IRowset** (contiene los métodos para capturar secuencialmente las filas del conjunto de filas), **IAccessor** (permite la definición de un grupo de enlaces de columna que describen la manera en que los datos tabulares se enlazan a las variables de programa del consumidor), **IColumnsInfo** (proporciona información sobre las columnas en el conjunto de filas) e **IRowsetInfo** (proporciona información sobre el conjunto de filas).</span><span class="sxs-lookup"><span data-stu-id="7a760-106">A rowset object exposes interfaces such as **IRowset** (contains methods for fetching rows from the rowset sequentially), **IAccessor** (permits the definition of a group of column bindings describing the way tabular data is bound to consumer program variables), **IColumnsInfo** (provides information about columns in the rowset), and **IRowsetInfo** (provides information about rowset).</span></span>  
  
 <span data-ttu-id="7a760-107">Un consumidor puede llamar al método **IRowset::GetData** para recuperar una fila de datos del conjunto de filas en un búfer.</span><span class="sxs-lookup"><span data-stu-id="7a760-107">A consumer can call the **IRowset::GetData** method to retrieve a row of data from the rowset into a buffer.</span></span> <span data-ttu-id="7a760-108">Antes de llamar a **GetData**, el consumidor describe el búfer mediante un conjunto de estructuras DBBINDING.</span><span class="sxs-lookup"><span data-stu-id="7a760-108">Before **GetData** is called, the consumer describes the buffer using a set of DBBINDING structures.</span></span> <span data-ttu-id="7a760-109">Cada enlace describe cómo una columna en un conjunto de filas se almacena en un búfer del consumidor y contiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a760-109">Each binding describes how a column in a rowset is stored in a consumer buffer and contains the following:</span></span>  
  
-   <span data-ttu-id="7a760-110">Ordinal de la columna (o parámetro) al que se aplica el enlace.</span><span class="sxs-lookup"><span data-stu-id="7a760-110">Ordinal of the column (or parameter) to which the binding applies.</span></span>  
  
-   <span data-ttu-id="7a760-111">Información acerca de qué se enlaza (por ejemplo, valor de los datos, longitud de los datos y su estado de enlace).</span><span class="sxs-lookup"><span data-stu-id="7a760-111">Information about what is bound (for example, data value, length of the data, and its binding status).</span></span>  
  
-   <span data-ttu-id="7a760-112">Información acerca de qué se desplaza en el búfer a cada una de estas partes.</span><span class="sxs-lookup"><span data-stu-id="7a760-112">Information about what is offset in the buffer to each of these parts.</span></span>  
  
-   <span data-ttu-id="7a760-113">La longitud y el tipo de los valores de datos tal y como existen en el búfer del consumidor.</span><span class="sxs-lookup"><span data-stu-id="7a760-113">Length and type of the data values as they exist in the consumer buffer.</span></span>  
  
 <span data-ttu-id="7a760-114">Al obtener datos, el proveedor usa información en cada enlace para determinar donde y cómo recuperar los datos del búfer del consumidor.</span><span class="sxs-lookup"><span data-stu-id="7a760-114">When getting the data, the provider uses information in each binding to determine where and how to retrieve data from the consumer buffer.</span></span> <span data-ttu-id="7a760-115">Al establecer datos en el búfer del consumidor, el proveedor usa información en cada enlace para determinar donde y cómo devolver los datos en el búfer del consumidor.</span><span class="sxs-lookup"><span data-stu-id="7a760-115">When setting data in the consumer buffer, the provider uses information in each binding to determine where and how to return data in the consumer's buffer.</span></span>  
  
 <span data-ttu-id="7a760-116">Una vez especificadas las estructuras DBBINDING, se crea un descriptor de acceso (**IAccessor::CreateAccessor**).</span><span class="sxs-lookup"><span data-stu-id="7a760-116">After the DBBINDING structures are specified, an accessor is created (**IAccessor::CreateAccessor**).</span></span> <span data-ttu-id="7a760-117">Un descriptor de acceso es una colección de enlaces que se usa para obtener o establecer los datos en el búfer del consumidor.</span><span class="sxs-lookup"><span data-stu-id="7a760-117">An accessor is a collection of bindings and is used to get or set the data in the consumer buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a760-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a760-118">See Also</span></span>  
 <span data-ttu-id="7a760-119">[Creación de una aplicación de proveedor de OLE DB de SQL Server Native Client](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="7a760-119">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="7a760-120">Temas de procedimientos de OLE DB</span><span class="sxs-lookup"><span data-stu-id="7a760-120">OLE DB How-to Topics</span></span>](../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
