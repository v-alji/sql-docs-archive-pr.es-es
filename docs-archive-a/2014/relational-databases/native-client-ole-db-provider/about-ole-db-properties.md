---
title: Acerca de las propiedades de OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, properties
- SQL Server Native Client OLE DB provider, properties
- properties [OLE DB]
- property values [SQL Server Native Client]
ms.assetid: 0b36a61e-b542-400d-a3d2-e6f643caf2c6
author: rothja
ms.author: jroth
ms.openlocfilehash: d4eb80ab9c0ab90da11d8580e9a2983455b676bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745272"
---
# <a name="about-ole-db-properties"></a><span data-ttu-id="d24dd-102">Acerca de las propiedades de OLE DB</span><span class="sxs-lookup"><span data-stu-id="d24dd-102">About OLE DB Properties</span></span>
  <span data-ttu-id="d24dd-103">Los consumidores establecen valores de propiedades para solicitar el comportamiento de un objeto específico.</span><span class="sxs-lookup"><span data-stu-id="d24dd-103">Consumers set property values to request specific object behavior.</span></span> <span data-ttu-id="d24dd-104">Por ejemplo, los consumidores usan propiedades para especificar las interfaces que va a exponer un conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="d24dd-104">For example, consumers use properties to specify the interfaces to be exposed by a rowset.</span></span> <span data-ttu-id="d24dd-105">Los consumidores obtienen los valores de las propiedades para determinar las capacidades de un objeto, como un conjunto de filas, una sesión o un objeto de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="d24dd-105">Consumers get the property values to determine the capabilities of an object, such as a rowset, a session, or a data source object.</span></span>  
  
 <span data-ttu-id="d24dd-106">Cada propiedad incluye un valor, un tipo, una descripción y un atributo de lectura/escritura y, en el caso de las propiedades de conjunto de filas, un indicador de si puede aplicarse columna por columna.</span><span class="sxs-lookup"><span data-stu-id="d24dd-106">Each property has a value, type, description, and read/write attribute, and for rowset properties, an indicator of whether it can be applied on a column-by-column basis.</span></span>  
  
 <span data-ttu-id="d24dd-107">Una propiedad se identifica mediante un GUID y un número entero que representa el identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="d24dd-107">A property is identified by a GUID and an integer representing the property ID.</span></span> <span data-ttu-id="d24dd-108">Un conjunto de propiedades es un conjunto de todas las propiedades que comparten el mismo GUID.</span><span class="sxs-lookup"><span data-stu-id="d24dd-108">A property set is a set of all properties that share the same GUID.</span></span> <span data-ttu-id="d24dd-109">Además de los conjuntos de propiedades OLE DB predefinidos, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proveedor de OLE DB de Native Client implementa las propiedades y los conjuntos de propiedades específicos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="d24dd-109">In addition to the predefined OLE DB property sets, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements provider-specific property sets and properties in them.</span></span> <span data-ttu-id="d24dd-110">Cada propiedad pertenece a uno o varios grupos de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d24dd-110">Each property belongs to one or more property groups.</span></span> <span data-ttu-id="d24dd-111">Un grupo de propiedades es el grupo de todas las propiedades que se aplican a un objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="d24dd-111">A property group is the group of all properties that apply to a particular object.</span></span> <span data-ttu-id="d24dd-112">Algunos grupos de propiedades incluyen el grupo de propiedades de inicialización, el grupo de propiedades de origen de datos, el grupo de propiedades de sesión, el grupo de propiedades de conjunto de filas, el grupo de propiedades de tabla y el grupo de propiedades de columna.</span><span class="sxs-lookup"><span data-stu-id="d24dd-112">Some property groups include the initialization property group, data source property group, session property group, rowset property group, table property group, and column property group.</span></span> <span data-ttu-id="d24dd-113">Hay propiedades en todos estos grupos de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d24dd-113">There are properties in each of these property groups.</span></span>  
  
 <span data-ttu-id="d24dd-114">El establecimiento de valores de propiedades implica:</span><span class="sxs-lookup"><span data-stu-id="d24dd-114">Setting property values involves:</span></span>  
  
1.  <span data-ttu-id="d24dd-115">Determinar las propiedades para las que van a establecerse valores.</span><span class="sxs-lookup"><span data-stu-id="d24dd-115">Determining the properties for which to set values.</span></span>  
  
2.  <span data-ttu-id="d24dd-116">Determinar los conjuntos de propiedades que contienen las propiedades identificadas.</span><span class="sxs-lookup"><span data-stu-id="d24dd-116">Determining the property sets that contain the identified properties.</span></span>  
  
3.  <span data-ttu-id="d24dd-117">Asignar una matriz de estructuras DBPROPSET, una para cada conjunto de propiedades identificado.</span><span class="sxs-lookup"><span data-stu-id="d24dd-117">Allocating an array of DBPROPSET structures, one for each identified property set.</span></span>  
  
4.  <span data-ttu-id="d24dd-118">Asignar una matriz de estructuras DBPROP para cada conjunto de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d24dd-118">Allocating an array of DBPROP structures for each property set.</span></span> <span data-ttu-id="d24dd-119">El número de elementos de cada matriz es igual al número de propiedades (identificado en el paso 1) que pertenecen a ese conjunto de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d24dd-119">The number of elements in each array is the number of properties (identified in Step 1) that belong to that property set.</span></span>  
  
5.  <span data-ttu-id="d24dd-120">Rellenar la estructura DBPROP para cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="d24dd-120">Filling in the DBPROP structure for each property.</span></span>  
  
6.  <span data-ttu-id="d24dd-121">Rellenar la información (GUID del conjunto de propiedades, recuento del número de elementos y un puntero a la matriz DBPROP correspondiente) de la estructura DBPROPSET para cada conjunto de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d24dd-121">Filling in information (property set GUID, count of number of elements, and a pointer to the corresponding DBPROP array) in the DBPROPSET structure for each property set.</span></span>  
  
7.  <span data-ttu-id="d24dd-122">Llamar a un método para establecer las propiedades y pasar el recuento y la matriz de estructuras DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="d24dd-122">Calling a method to set properties and passing the count and the array of DBPROPSET structures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d24dd-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d24dd-123">See Also</span></span>  
 <span data-ttu-id="d24dd-124">[Creación de una aplicación de proveedor de OLE DB de SQL Server Native Client](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="d24dd-124">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="d24dd-125">Propiedades (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="d24dd-125">Properties (OLE DB)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112207)  
  
  
