---
title: ISSCommandWithParameters::GetParameterProperties (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::GetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetParameterProperties method
ms.assetid: 7f4cc5ea-d028-4fe5-9192-bd153ab3c26c
author: rothja
ms.author: jroth
ms.openlocfilehash: 2160c93748375a4aa3bee3d530d441182204134a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671032"
---
# <a name="isscommandwithparametersgetparameterproperties-ole-db"></a><span data-ttu-id="3a2c3-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3a2c3-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="3a2c3-103">Devuelve una matriz de estructuras de conjunto de propiedades SSPARAMPROPS, un conjunto de propiedades SSPARAMPROPS para cada parámetro XML o UDT.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-103">Returns an array of SSPARAMPROPS property set structures, one SSPARAMPROPS property set for each UDT or XML parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a2c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a2c3-104">Syntax</span></span>  
  
```  
  
HRESULT GetParameterProperties(  
DB_UPARAMS *pcParams,  
SSPARAMPROPS **prgParamProperties);  
```  
  
## <a name="arguments"></a><span data-ttu-id="3a2c3-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3a2c3-105">Arguments</span></span>  
 <span data-ttu-id="3a2c3-106">*pcParams*[out][in]</span><span class="sxs-lookup"><span data-stu-id="3a2c3-106">*pcParams*[out][in]</span></span>  
 <span data-ttu-id="3a2c3-107">Un puntero a la memoria que contiene el número de estructuras SSPARAMPROPS devueltas en *prgParamProperties*.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-107">A pointer to memory that contains the number of SSPARAMPROPS structures returned in *prgParamProperties*.</span></span>  
  
 <span data-ttu-id="3a2c3-108">*prgParamProperties*[out]</span><span class="sxs-lookup"><span data-stu-id="3a2c3-108">*prgParamProperties*[out]</span></span>  
 <span data-ttu-id="3a2c3-109">Un puntero a la memoria que devuelve una matriz de estructuras SSPARAMPROPS.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-109">A pointer to memory in which an array of SSPARAMPROPS structures is returned.</span></span> <span data-ttu-id="3a2c3-110">El proveedor asigna memoria a las estructuras y devuelve la dirección a esta memoria; el consumidor libera esta memoria con **IMalloc:: Free** cuando ya no necesita las estructuras.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-110">The provider allocates memory for the structures and returns the address to this memory; the consumer releases this memory with **IMalloc::Free** when it no longer needs the structures.</span></span> <span data-ttu-id="3a2c3-111">Antes de llamar a **IMalloc:: Free** para *prgParamProperties*, el consumidor también debe llamar a **VariantClear** para la propiedad *vValue* de cada estructura DBPROP con el fin de evitar una pérdida de memoria en los casos en los que la variante contiene un tipo de referencia (por ejemplo, un BSTR). Si *pcParams* es cero en la salida o se produce un error distinto de DB_E_ERRORSOCCURRED, el proveedor no asigna memoria y se asegura de que *prgParamProperties* sea un puntero nulo en la salida.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-111">Before calling **IMalloc::Free** for *prgParamProperties*, the consumer must also call **VariantClear** for the *vValue* property of each DBPROP structure in order to prevent a memory leak in cases where the variant contains a reference type (such as a BSTR.) If *pcParams* is zero on output or an error other than DB_E_ERRORSOCCURRED occurs, the provider does not allocate any memory and ensures that *prgParamProperties* is a null pointer on output.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="3a2c3-112">Valores de código de retorno</span><span class="sxs-lookup"><span data-stu-id="3a2c3-112">Return Code Values</span></span>  
 <span data-ttu-id="3a2c3-113">El método **GetParameterProperties** devuelve los mismos códigos de error que el método principal OLE DB **ICommandProperties:: GetProperties** , salvo que no se pueden generar DB_S_ERRORSOCCURRED y DB_E_ERRORSOCCURED.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-113">The **GetParameterProperties** method returns the same error codes as the core OLE DB **ICommandProperties::GetProperties** method, except that DB_S_ERRORSOCCURRED and DB_E_ERRORSOCCURED cannot be raised.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a2c3-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3a2c3-114">Remarks</span></span>  
 <span data-ttu-id="3a2c3-115">**ISSCommandWithParameters:: GetParameterProperties** se comporta de forma coherente con respecto a **GetParameterInfo**.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-115">**ISSCommandWithParameters::GetParameterProperties** behaves consistently with respect to **GetParameterInfo**.</span></span> <span data-ttu-id="3a2c3-116">Si no se ha llamado a [ISSCommandWithParameters:: SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) o **SetParameterInfo** o se ha llamado a cParams igual a cero, **GetParameterInfo** deriva la información de parámetros y devuelve this.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-116">If [ISSCommandWithParameters::SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) or **SetParameterInfo** have not been called or have been called with cParams equal to zero, **GetParameterInfo** derives parameter information and returns this.</span></span> <span data-ttu-id="3a2c3-117">Si se ha llamado a **ISSCommandWithParameters:: SetParameterProperties** o **SetParameterInfo** para al menos un parámetro, **ISSCommandWithParameters:: GetParameterProperties** devuelve propiedades solo para los parámetros para los que se ha llamado a **ISSCommandWithParameters:: SetParameterProperties** .</span><span class="sxs-lookup"><span data-stu-id="3a2c3-117">If **ISSCommandWithParameters::SetParameterProperties** or **SetParameterInfo** have been called for at least one parameter, **ISSCommandWithParameters::GetParameterProperties** returns properties only for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span> <span data-ttu-id="3a2c3-118">Si se llama a **ISSCommandWithParameters:: SetParameterProperties** después de **ISSCommandWithParameters:: GetParameterProperties** o **GetParameterInfo**, las llamadas subsiguientes a **ISSCommandWithParameters:: GetParameterProperties** devuelven los valores invalidados para los parámetros para los que se ha llamado a **ISSCommandWithParameters:: SetParameterProperties** .</span><span class="sxs-lookup"><span data-stu-id="3a2c3-118">If **ISSCommandWithParameters::SetParameterProperties** is called after **ISSCommandWithParameters::GetParameterProperties** or **GetParameterInfo**, subsequent calls to **ISSCommandWithParameters::GetParameterProperties** return the overridden values for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span>  
  
 <span data-ttu-id="3a2c3-119">La estructura SSPARAMPROPS se define del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="3a2c3-119">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
|<span data-ttu-id="3a2c3-120">Miembro</span><span class="sxs-lookup"><span data-stu-id="3a2c3-120">Member</span></span>|<span data-ttu-id="3a2c3-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a2c3-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3a2c3-122">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="3a2c3-122">*iOrdinal*</span></span>|<span data-ttu-id="3a2c3-123">El ordinal del parámetro que se ha pasado.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-123">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="3a2c3-124">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="3a2c3-124">*cPropertySets*</span></span>|<span data-ttu-id="3a2c3-125">El número de estructuras DBPROPSET de *rgPropertySets*.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-125">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="3a2c3-126">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="3a2c3-126">*rgPropertySets*</span></span>|<span data-ttu-id="3a2c3-127">Un puntero a la memoria que devuelve una matriz de estructuras DBPROPSET.</span><span class="sxs-lookup"><span data-stu-id="3a2c3-127">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a2c3-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a2c3-128">See Also</span></span>  
 [<span data-ttu-id="3a2c3-129">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="3a2c3-129">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
