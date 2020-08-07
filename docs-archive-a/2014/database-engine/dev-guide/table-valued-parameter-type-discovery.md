---
title: Detección de tipos de parámetros con valores de tabla | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- table-valued parameters, type discovery
ms.assetid: f55818c2-ebb5-4cf6-8c0c-0da41f592560
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab8d837e4ddf74256e4bae70f772557ec8ff67f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746465"
---
# <a name="table-valued-parameter-type-discovery"></a><span data-ttu-id="36316-102">Detección de tipos de parámetros con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="36316-102">Table-Valued Parameter Type Discovery</span></span>
  <span data-ttu-id="36316-103">El consumidor, es decir, la aplicación cliente que usa el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client, puede detectar el tipo de cada parámetro de comando si se ha proporcionado el texto del comando al proveedor de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="36316-103">The consumer-that is, the client application using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Provider-can discover the type of each command parameter if the command text has been given to the OLE DB Provider.</span></span> <span data-ttu-id="36316-104">Después de conocer el tipo de un parámetro con valores de tabla, el consumidor puede detectar la información de metadatos de cada columna individual del parámetro con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="36316-104">After the type of a table-valued parameter is known, the consumer can discover the metadata information for each individual column of the table-valued parameter.</span></span>  
  
 <span data-ttu-id="36316-105">La información de tipo de los parámetros de procedimiento es compatible con ICommandWithParameters::GetParameterInfo en la mayoría de tipos de parámetro.</span><span class="sxs-lookup"><span data-stu-id="36316-105">The type information of procedure parameters is supported by ICommandWithParameters::GetParameterInfo for most parameter types.</span></span> <span data-ttu-id="36316-106">A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , con la introducción de tipos definidos por el usuario y el `xml` tipo de datos, el método GetParameterInfo no era suficiente para este propósito porque no era posible proporcionar información de tipo definido por el usuario (nombre, esquema y catálogo) a través de ICommandWithParameters.</span><span class="sxs-lookup"><span data-stu-id="36316-106">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], with the introduction of user-defined types and the `xml` data type, the GetParameterInfo method was not sufficient for this purpose because it was not possible to provide user-defined type information (name, schema, and catalog) through ICommandWithParameters.</span></span> <span data-ttu-id="36316-107">Se definió una nueva interfaz, ISSCommandWithParameters, para proporcionar información de tipo extendido.</span><span class="sxs-lookup"><span data-stu-id="36316-107">A new interface, ISSCommandWithParameters, was defined to provide extended type information.</span></span>  
  
 <span data-ttu-id="36316-108">En el caso de los parámetros con valores de tabla, también usará la interfaz ISSCommandWithParameters para detectar información detallada.</span><span class="sxs-lookup"><span data-stu-id="36316-108">For table-valued parameters, you also use the ISSCommandWithParameters interface to discover detailed information.</span></span> <span data-ttu-id="36316-109">El cliente llama a ISSCommandWithParameters::GetParameterInfo después de preparar el objeto de comando.</span><span class="sxs-lookup"><span data-stu-id="36316-109">The client calls ISSCommandWithParameters::GetParameterInfo after preparing the command object.</span></span> <span data-ttu-id="36316-110">Para los parámetros con valores de tabla, el proveedor establece el miembro *wType* de la estructura DBPARAMINFO en DBTYPE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="36316-110">For table-valued parameters, the *wType* member of the DBPARAMINFO structure is set to DBTYPE_TABLE by the provider.</span></span> <span data-ttu-id="36316-111">El campo *ulParamSize* de la estructura de DBPARAMINFO tiene un valor de ~0.</span><span class="sxs-lookup"><span data-stu-id="36316-111">The *ulParamSize* field of DBPARAMINFO structure has a value of ~0.</span></span>  
  
 <span data-ttu-id="36316-112">El consumidor solicitará después propiedades adicionales (el nombre de catálogo del tipo de parámetro con valores de tabla, el nombre de esquema del tipo de parámetro con valores de tabla, el nombre del tipo de parámetro con valores de tabla, el orden de las columnas y las columnas predeterminadas) mediante ISSCommandWithParameters::GetParameterProperties.</span><span class="sxs-lookup"><span data-stu-id="36316-112">The consumer would then request additional properties (table-valued parameter type catalog name, table-valued parameter type schema name, table-valued parameter type name, column ordering, and default columns) by using ISSCommandWithParameters::GetParameterProperties.</span></span>  
  
 <span data-ttu-id="36316-113">Una vez conocido el nombre de tipo, para recuperar la información de cada columna individual, el consumidor debe llamar a IOpenRowset::OpenRowsetor u obtener el conjunto de filas DBSCHEMA_TABLE_TYPE_COLUMNS al especificar el nombre del tipo de parámetro con valores de tabla como el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="36316-113">After the type name is known, to retrieve the individual column information the consumer must either call IOpenRowset::OpenRowsetor obtain the DBSCHEMA_TABLE_TYPE_COLUMNS rowset by specifying the table-valued parameter type name as the table name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36316-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36316-114">See Also</span></span>  
 <span data-ttu-id="36316-115">[Parámetros con valores de tabla &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="36316-115">[Table-Valued Parameters &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md) </span></span>  
 [<span data-ttu-id="36316-116">Usar parámetros con valores de tabla &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="36316-116">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
