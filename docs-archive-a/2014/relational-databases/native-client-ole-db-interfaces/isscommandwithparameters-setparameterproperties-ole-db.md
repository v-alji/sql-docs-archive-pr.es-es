---
title: ISSCommandWithParameters::SetParameterProperties (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::SetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- SetParameterProperties method
ms.assetid: 4cd0281a-a2a0-43df-8e46-eb478b64cb4b
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bf8e5cde9885a5d9b55d84c6384b76aecf50b8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744675"
---
# <a name="isscommandwithparameterssetparameterproperties-ole-db"></a><span data-ttu-id="fa6f5-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="fa6f5-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="fa6f5-103">Establece las propiedades de los parámetros por cada parámetro por ordinal o establece las propiedades masivas de los parámetro especificando una matriz de estructuras SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-103">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of SSPARAMPROPS structures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa6f5-104">Syntax</span></span>  
  
```  
  
HRESULT SetParameterProperties(  
DB_UPARAMS cParams,   
SSPARAMPROPS rgParamProperties[]);  
```  
  
## <a name="arguments"></a><span data-ttu-id="fa6f5-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fa6f5-105">Arguments</span></span>  
 <span data-ttu-id="fa6f5-106">*cParams*[in]</span><span class="sxs-lookup"><span data-stu-id="fa6f5-106">*cParams*[in]</span></span>  
 <span data-ttu-id="fa6f5-107">El número de estructuras SSPARAMPROPS en la matriz *rgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-107">The number of SSPARAMPROPS structures in the *rgParamProperties* array.</span></span> <span data-ttu-id="fa6f5-108">Si este número es cero, `ISSCommandWithParameters::SetParameterProperties` eliminará todas las propiedades que se puedan haber especificado para los parámetros del comando.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-108">If this number is zero, `ISSCommandWithParameters::SetParameterProperties` will delete all properties that might have been specified for any parameters in the command.</span></span>  
  
 <span data-ttu-id="fa6f5-109">*rgParamProperties*[in]</span><span class="sxs-lookup"><span data-stu-id="fa6f5-109">*rgParamProperties*[in]</span></span>  
 <span data-ttu-id="fa6f5-110">Una matriz de estructuras SSPARAMPROPS que se van a establecer.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-110">An array of SSPARAMPROPS structures to be set.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="fa6f5-111">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="fa6f5-111">Return Code Values</span></span>  
 <span data-ttu-id="fa6f5-112">El `ISSCommandWithParameters::SetParameterProperties` método devuelve los mismos códigos de error que el método básico OLE DB **ICommandProperties:: SetProperties** .</span><span class="sxs-lookup"><span data-stu-id="fa6f5-112">The `ISSCommandWithParameters::SetParameterProperties` method returns the same error codes as the core OLE DB **ICommandProperties::SetProperties** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa6f5-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa6f5-113">Remarks</span></span>  
 <span data-ttu-id="fa6f5-114">La configuración de las propiedades de parámetro con este método se permite por cada parámetro por ordinal o con una sola `ISSCommandWithParameters::SetParameterProperties` llamada una vez que SSPARAMPROPS se ha creado a partir de la matriz de propiedades.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-114">Setting parameter properties with this method is allowed on a per parameter basis by ordinal, or with a single `ISSCommandWithParameters::SetParameterProperties` call once the SSPARAMPROPS has been built from the property array.</span></span>  
  
 <span data-ttu-id="fa6f5-115">Se debe llamar al método **SetParameterInfo** antes de llamar al `ISSCommandWithParameters::SetParameterProperties` método.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-115">The **SetParameterInfo** method must be called before calling the `ISSCommandWithParameters::SetParameterProperties` method.</span></span> <span data-ttu-id="fa6f5-116">La llamada a `SetParameterProperties(0, NULL)` borra todas las propiedades de parámetro especificadas, en tanto que la llamada a `SetParameterInfo(0,NULL,NULL)` borra toda la información de parámetros, incluidas las propiedades que puedan estar asociadas a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-116">Calling `SetParameterProperties(0, NULL)` clears all specified parameter properties, while calling `SetParameterInfo(0,NULL,NULL)` clears all the parameter info including any properties that might be associated with a parameter.</span></span>  
  
 <span data-ttu-id="fa6f5-117">Llamar `ISSCommandWithParameters::SetParameterProperties` a para especificar las propiedades de un parámetro que no es del tipo DBTYPE_XML o DBTYPE_UDT devuelve DB_E_ERRORSOCCURRED o DB_S_ERRORSOCCURRED y marca el campo *dwStatus* de todos los DBPROP contenidos en SSPARAMPROPS para ese parámetro con DBPROPSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-117">Calling `ISSCommandWithParameters::SetParameterProperties` to specify properties for a parameter which is not of type DBTYPE_XML or DBTYPE_UDT returns DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED and marks the *dwStatus* field of all DBPROPs contained in SSPARAMPROPS for that parameter with DBPROPSTATUS_NOTSET.</span></span> <span data-ttu-id="fa6f5-118">Se debe recorrer la matriz DBPROP de cada DBPROPSET incluido en SSPARAMPROPS para detectar a qué parámetro hace referencia DB_E_ERRORSOCCURRED o DB_S_ERRORSOCCURRED.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-118">The DBPROP array of each DBPROPSET contained in SSPARAMPROPS should be traversed to detect which parameter the DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED refers to.</span></span>  
  
 <span data-ttu-id="fa6f5-119">Si `ISSCommandWithParameters::SetParameterProperties` se llama a para especificar las propiedades de los parámetros cuya información de parámetros no se ha establecido todavía con **SetParameterInfo**, el proveedor devuelve E_UNEXPECTED con el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="fa6f5-119">If `ISSCommandWithParameters::SetParameterProperties` is called to specify the properties of parameters whose parameter info have not been set yet with **SetParameterInfo**, the provider returns E_UNEXPECTED with the following error message:</span></span>  
  
 <span data-ttu-id="fa6f5-120">No se puede llamar al método SetParameterProperties para los parámetros especificados sin llamar primero al método SetParameterInfo.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-120">SetParameterProperties method cannot be called for the specified parameters without first calling SetParameterInfo method.</span></span> <span data-ttu-id="fa6f5-121">La información de parámetro debe configurarse antes que las propiedades de parámetro.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-121">The parameter information must be set before setting the parameter properties.</span></span>  
  
 <span data-ttu-id="fa6f5-122">Si la llamada a `ISSCommandWithParameters::SetParameterProperties` contiene algunos parámetros en los que se ha establecido la información de parámetros y algunos parámetros en los que no se ha establecido la información de parámetros, las propiedades de dwStatus del DBPROPSET del conjunto de propiedades SSPARAMPROPS devolverán con DBSTATUS_NOTSET.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-122">If the call to `ISSCommandWithParameters::SetParameterProperties` contains some parameters where the parameter info has been set, and some parameters where the parameter info has not been set, the dwStatus properties in the DBPROPSET of the SSPARAMPROPS property set will return with DBSTATUS_NOTSET.</span></span>  
  
 <span data-ttu-id="fa6f5-123">La estructura SSPARAMPROPS se define del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="fa6f5-123">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
 <span data-ttu-id="fa6f5-124">Las mejoras en el motor de base de datos a partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] permiten a ISSCommandWithParameters::SetParameterProperties obtener descripciones más precisas de los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-124">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ISSCommandWithParameters::SetParameterProperties to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="fa6f5-125">Estos resultados más precisos pueden diferir de los valores que devuelve ISSCommandWithParameters::SetParameterProperties en las versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa6f5-125">These more accurate results may differ from the values returned by ISSCommandWithParameters::SetParameterProperties in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fa6f5-126">Para obtener más información, vea [Detección de metadatos](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="fa6f5-126">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
|<span data-ttu-id="fa6f5-127">Miembro</span><span class="sxs-lookup"><span data-stu-id="fa6f5-127">Member</span></span>|<span data-ttu-id="fa6f5-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa6f5-128">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fa6f5-129">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="fa6f5-129">*iOrdinal*</span></span>|<span data-ttu-id="fa6f5-130">El ordinal del parámetro que se ha pasado.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-130">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="fa6f5-131">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="fa6f5-131">*cPropertySets*</span></span>|<span data-ttu-id="fa6f5-132">El número de estructuras DBPROPSET de *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-132">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="fa6f5-133">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="fa6f5-133">*rgPropertySets*</span></span>|<span data-ttu-id="fa6f5-134">Un puntero a la memoria que devuelve una matriz de estructuras DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="fa6f5-134">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa6f5-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa6f5-135">See Also</span></span>  
 [<span data-ttu-id="fa6f5-136">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="fa6f5-136">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
