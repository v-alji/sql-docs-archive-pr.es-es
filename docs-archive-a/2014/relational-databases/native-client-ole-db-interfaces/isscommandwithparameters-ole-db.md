---
title: ISSCommandWithParameters (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSCommandWithParameters interface
ms.assetid: 3419b7f3-36a3-4863-816e-e641e4e90496
author: rothja
ms.author: jroth
ms.openlocfilehash: 295026497a97b4ce13d1a1a68de48079809390ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671033"
---
# <a name="isscommandwithparameters-ole-db"></a><span data-ttu-id="4d561-102">ISSCommandWithParameters (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="4d561-102">ISSCommandWithParameters (OLE DB)</span></span>
  <span data-ttu-id="4d561-103">**ISSCommandWithParameters** expone la compatibilidad con los tipos XML y definidos por el usuario (UDT) de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d561-103">**ISSCommandWithParameters** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML and user-defined types (UDT).</span></span> <span data-ttu-id="4d561-104">Ésta es una interfaz opcional que hereda de la interfaz OLE DB **ICommandWithParameters**básica.</span><span class="sxs-lookup"><span data-stu-id="4d561-104">This is an optional interface that inherits from the core OLE DB interface **ICommandWithParameters**.</span></span> <span data-ttu-id="4d561-105">Además de los tres métodos heredados de **ICommandWithParameters**; **GetParameterInfo**, **MapParameterNames**y **SetParameterInfo**; **ISSCommandWithParameters** proporciona dos nuevos métodos que se utilizan para administrar tipos de datos específicos de servidor.</span><span class="sxs-lookup"><span data-stu-id="4d561-105">In addition to the three methods inherited from **ICommandWithParameters**; **GetParameterInfo**, **MapParameterNames**, and **SetParameterInfo**; **ISSCommandWithParameters** provides two new methods that are used to handle server specific data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d561-106"> La interfaz **ISSCommandWithParameters** se puede utilizar cuando se utilizan componentes de servicio, pero los propios componentes de servicio no utilizarán esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="4d561-106">The **ISSCommandWithParameters** interface can be used when Service Components are used, but the Service Components themselves will not use this interface.</span></span>  
  
|<span data-ttu-id="4d561-107">Método</span><span class="sxs-lookup"><span data-stu-id="4d561-107">Method</span></span>|<span data-ttu-id="4d561-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d561-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d561-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="4d561-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-getparameterproperties-ole-db.md)|<span data-ttu-id="4d561-110">Devuelve la estructura del conjunto de propiedades **SSPARAMPROPS** en la matriz de cada parámetro UDT o XML pasado al comando, pero no devuelve nada en los demás tipos de parámetros.</span><span class="sxs-lookup"><span data-stu-id="4d561-110">Returns one **SSPARAMPROPS** property set structure in the array for each UDT or XML parameter passed to the command, but none is returned for other types of parameters.</span></span>|  
|[<span data-ttu-id="4d561-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="4d561-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-setparameterproperties-ole-db.md)|<span data-ttu-id="4d561-112">Establece las propiedades de parámetro por cada parámetro por ordinal o establece propiedades masivas de parámetro mediante la especificación de una matriz de estructuras **SSPARAMPROPS** .</span><span class="sxs-lookup"><span data-stu-id="4d561-112">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of **SSPARAMPROPS** structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d561-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d561-113">See Also</span></span>  
 <span data-ttu-id="4d561-114">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="4d561-114">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="4d561-115">[Usar tipos de datos XML](../native-client/features/using-xml-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="4d561-115">[Using XML Data Types](../native-client/features/using-xml-data-types.md) </span></span>  
 [<span data-ttu-id="4d561-116">Usar tipos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="4d561-116">Using User-Defined Types</span></span>](../native-client/features/using-user-defined-types.md)  
  
  
