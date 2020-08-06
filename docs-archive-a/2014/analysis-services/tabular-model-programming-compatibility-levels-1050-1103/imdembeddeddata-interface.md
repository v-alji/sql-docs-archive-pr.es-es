---
title: Interfaz IMDEmbedded | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 9dba8c68-4bef-4c2b-815c-c286f1a1939b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 331f8c33f7748e6591acd6d6ecda7a03ef7d8137
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671227"
---
# <a name="imdembedded-interface"></a><span data-ttu-id="c52da-102">Interfaz IMDEmbedded</span><span class="sxs-lookup"><span data-stu-id="c52da-102">IMDEmbedded Interface</span></span>
  <span data-ttu-id="c52da-103">La interfaz IMDEmbedded es una interfaz pública utilizada para administrar una base de datos incrustada de PowerPivot o una base de datos de modelo tabular.</span><span class="sxs-lookup"><span data-stu-id="c52da-103">The IMDEmbedded interface is a public interface used to manage an embedded PowerPivot database or a tabular model database.</span></span> <span data-ttu-id="c52da-104">La interfaz hereda de la interfaz `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c52da-104">The interface inherits from the `IPersistStream` interface.</span></span> <span data-ttu-id="c52da-105">La interfaz permite las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="c52da-105">The interface allows for the following operations:</span></span>  
  
-   <span data-ttu-id="c52da-106">Obtenga un identificador para el flujo incrustado en el documento contenedor.</span><span class="sxs-lookup"><span data-stu-id="c52da-106">Get an identifier to the embedded stream in the container document.</span></span>  
  
-   <span data-ttu-id="c52da-107">Establezca la dirección URL del documento contenedor.</span><span class="sxs-lookup"><span data-stu-id="c52da-107">Set the URL of the containing document.</span></span>  
  
-   <span data-ttu-id="c52da-108">Establezca una marca para indicar si la aplicación de incrustación está en un entorno hospedado.</span><span class="sxs-lookup"><span data-stu-id="c52da-108">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
-   <span data-ttu-id="c52da-109">Establezca la ruta de acceso a los archivos temporales que usa la aplicación de incrustación.</span><span class="sxs-lookup"><span data-stu-id="c52da-109">Set the path to temporary files used by the embedding application.</span></span>  
  
-   <span data-ttu-id="c52da-110">Cancele la operación incrustada actual.</span><span class="sxs-lookup"><span data-stu-id="c52da-110">Cancel the current embedded operation.</span></span>  
  
-   <span data-ttu-id="c52da-111">Obtenga el tamaño calculado (en bytes) del flujo para guardar el objeto incrustado.</span><span class="sxs-lookup"><span data-stu-id="c52da-111">Get the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="c52da-112">Se hereda de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c52da-112">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="c52da-113">Compruebe si la base de datos incrustada ha cambiado desde que se guardó por última vez.</span><span class="sxs-lookup"><span data-stu-id="c52da-113">Verify if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="c52da-114">Se hereda de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c52da-114">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="c52da-115">Cargue la base de datos incrustada en el motor local o en proceso.</span><span class="sxs-lookup"><span data-stu-id="c52da-115">Load the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="c52da-116">Se hereda de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c52da-116">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="c52da-117">Guarde la base de datos local o en proceso en el flujo incrustado en el documento contenedor.</span><span class="sxs-lookup"><span data-stu-id="c52da-117">Save the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="c52da-118">Se hereda de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c52da-118">Inherited from `IPersistStream`.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c52da-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="c52da-119">Reference</span></span>  
 <span data-ttu-id="c52da-120">La siguiente referencia documenta la `IMDEmbedded` interfaz, tal como se presenta en el archivo de encabezado **msmd. h** .</span><span class="sxs-lookup"><span data-stu-id="c52da-120">The following reference documents the `IMDEmbedded` interface as presented in **msmd.h** header file.</span></span>  
  
### <a name="source-file-pxoembeddeddataidl"></a><span data-ttu-id="c52da-121">Archivo de origen: PXOEmbeddedData.idl</span><span class="sxs-lookup"><span data-stu-id="c52da-121">Source file: PXOEmbeddedData.idl</span></span>  
  
```  
[  
  local,                            
  object,                           
  uuid(6B6691CF-5453-41c2-ADD9-4F320B7FD421),                       
  pointer_default(unique)           
]  
interface IMDEmbeddedData : IPersistStream  
{  
 [id(1), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in] BOOL in_fIsHosted);  
  
 [id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
  
 [id(3), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
  
 [id(4), helpstring("Set the path used by the embedding application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
  
 [id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
};  
```  
  
### <a name="imdembeddeddatagetstreamidentifier"></a><span data-ttu-id="c52da-122">IMDEmbeddedData::GetStreamIdentifier</span><span class="sxs-lookup"><span data-stu-id="c52da-122">IMDEmbeddedData::GetStreamIdentifier</span></span>  
  
```  
HRESULT GetStreamIdentifier (  
    [out, retval] BSTR * out_pbstrStreamId  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c52da-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52da-123">Description</span></span>  
 <span data-ttu-id="c52da-124">Obtiene el identificador que usa la aplicación host para el flujo incrustado en el documento contenedor.</span><span class="sxs-lookup"><span data-stu-id="c52da-124">Gets the identifier used by the host application to the embedded stream in the container document.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c52da-125">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c52da-125">Parameters</span></span>  
 <span data-ttu-id="c52da-126">*out_pbstrStreamId*</span><span class="sxs-lookup"><span data-stu-id="c52da-126">*out_pbstrStreamId*</span></span>  
 <span data-ttu-id="c52da-127">Especifica la ubicación del identificador del flujo.</span><span class="sxs-lookup"><span data-stu-id="c52da-127">Specifies the location of the stream identifier.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c52da-128">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c52da-128">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c52da-129">El identificador del flujo se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c52da-129">The stream identifier was successfully returned.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="c52da-130">No hay ningún identificador del flujo.</span><span class="sxs-lookup"><span data-stu-id="c52da-130">There is no stream identifier.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c52da-131">Se produjo un error al tener acceso al identificador del flujo.</span><span class="sxs-lookup"><span data-stu-id="c52da-131">An error occurred accessing the stream identifier.</span></span>  
  
#### <a name="remarks"></a><span data-ttu-id="c52da-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c52da-132">Remarks</span></span>  
 <span data-ttu-id="c52da-133">Para comprobar si la conexión actual contiene una base de datos incrustada, el usuario debería comprobar el valor de la propiedad DBPROP_MSMD_EMBEDDED_DATA de las propiedades de conexión OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c52da-133">To verify if the current connection contains an embedded database, the user should check the value of the DBPROP_MSMD_EMBEDDED_DATA property from the OLE DB connection properties.</span></span>  
  
 <span data-ttu-id="c52da-134">Los valores posibles de DBPROP_MSMD_EMBEDDED_DATA son:</span><span class="sxs-lookup"><span data-stu-id="c52da-134">The possible values for DBPROP_MSMD_EMBEDDED_DATA are:</span></span>  
  
|<span data-ttu-id="c52da-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="c52da-135">Name</span></span>|<span data-ttu-id="c52da-136">Value</span><span class="sxs-lookup"><span data-stu-id="c52da-136">Value</span></span>|<span data-ttu-id="c52da-137">Definición</span><span class="sxs-lookup"><span data-stu-id="c52da-137">Definition</span></span>|  
|----------|-----------|----------------|  
|<span data-ttu-id="c52da-138">DBPROPVAL_EMBED_NONE</span><span class="sxs-lookup"><span data-stu-id="c52da-138">DBPROPVAL_EMBED_NONE</span></span>|<span data-ttu-id="c52da-139">0x00</span><span class="sxs-lookup"><span data-stu-id="c52da-139">0x00</span></span>|<span data-ttu-id="c52da-140">No hay ninguna base de datos incrustada</span><span class="sxs-lookup"><span data-stu-id="c52da-140">No embedded database available</span></span>|  
|<span data-ttu-id="c52da-141">DBPROPVAL_EMBED_EMBEDDED</span><span class="sxs-lookup"><span data-stu-id="c52da-141">DBPROPVAL_EMBED_EMBEDDED</span></span>|<span data-ttu-id="c52da-142">0x01</span><span class="sxs-lookup"><span data-stu-id="c52da-142">0x01</span></span>|<span data-ttu-id="c52da-143">La aplicación actual contiene la base de datos incrustada</span><span class="sxs-lookup"><span data-stu-id="c52da-143">The current application contains the embedded database</span></span>|  
|<span data-ttu-id="c52da-144">DBPROPVAL_EMBED_LINKED</span><span class="sxs-lookup"><span data-stu-id="c52da-144">DBPROPVAL_EMBED_LINKED</span></span>|<span data-ttu-id="c52da-145">0x02</span><span class="sxs-lookup"><span data-stu-id="c52da-145">0x02</span></span>|<span data-ttu-id="c52da-146">La base de datos incrustada se hospeda en una aplicación remota (es decir, el servidor de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="c52da-146">The embedded database is hosted in a remote application (i.e. SharePoint Server)</span></span>|  
  
#### <a name="source"></a><span data-ttu-id="c52da-147">Source</span><span class="sxs-lookup"><span data-stu-id="c52da-147">Source</span></span>  
  
```  
[id(1), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
```  
  
### <a name="imdembeddeddatasetcontainerurl"></a><span data-ttu-id="c52da-148">IMDEmbeddedData::SetContainerURL</span><span class="sxs-lookup"><span data-stu-id="c52da-148">IMDEmbeddedData::SetContainerURL</span></span>  
  
```  
HRESULT SetContainerURL (  
    [in] BSTR in_bstrURL  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c52da-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52da-149">Description</span></span>  
 <span data-ttu-id="c52da-150">Establece la dirección URL del archivo que contiene el flujo incrustado.</span><span class="sxs-lookup"><span data-stu-id="c52da-150">Sets the URL for the file containing the embedded stream.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c52da-151">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c52da-151">Parameters</span></span>  
 <span data-ttu-id="c52da-152">*in_bstrURL*</span><span class="sxs-lookup"><span data-stu-id="c52da-152">*in_bstrURL*</span></span>  
 <span data-ttu-id="c52da-153">Especifica la dirección URL del documento contenedor.</span><span class="sxs-lookup"><span data-stu-id="c52da-153">Specifies the URL for the containing document.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c52da-154">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c52da-154">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c52da-155">La dirección URL del elemento contenedor se estableció correctamente.</span><span class="sxs-lookup"><span data-stu-id="c52da-155">The container URL was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c52da-156">Se produjo un error al establecer la dirección URL del elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="c52da-156">An error occurred while setting the container URL.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="c52da-157">Source</span><span class="sxs-lookup"><span data-stu-id="c52da-157">Source</span></span>  
  
```  
[id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
```  
  
### <a name="imdembeddeddatasethosted"></a><span data-ttu-id="c52da-158">IMDEmbeddedData::SetHosted</span><span class="sxs-lookup"><span data-stu-id="c52da-158">IMDEmbeddedData::SetHosted</span></span>  
  
```  
HRESULT SetHosted (  
    [in] BOOL in_fIsHosted  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c52da-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52da-159">Description</span></span>  
 <span data-ttu-id="c52da-160">Establezca una marca para indicar si la aplicación de incrustación está en un entorno hospedado.</span><span class="sxs-lookup"><span data-stu-id="c52da-160">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c52da-161">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c52da-161">Parameters</span></span>  
 <span data-ttu-id="c52da-162">*in_ftHosted*</span><span class="sxs-lookup"><span data-stu-id="c52da-162">*in_ftHosted*</span></span>  
 <span data-ttu-id="c52da-163">TRUE, si el autor de la llamada se hospeda en una aplicación de servicio (como IIS).</span><span class="sxs-lookup"><span data-stu-id="c52da-163">TRUE if caller is in a hosted in a service application (like IIS).</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c52da-164">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c52da-164">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c52da-165">La marca se estableció correctamente.</span><span class="sxs-lookup"><span data-stu-id="c52da-165">The flag was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c52da-166">Se produjo un error al establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="c52da-166">An error occurred while setting the flag.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="c52da-167">Source</span><span class="sxs-lookup"><span data-stu-id="c52da-167">Source</span></span>  
  
```  
[id(5), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in]  BOOL in_fIsHosted);  
```  
  
### <a name="imdembeddeddatasettempdirpath"></a><span data-ttu-id="c52da-168">IMDEmbeddedData::SetTempDirPath</span><span class="sxs-lookup"><span data-stu-id="c52da-168">IMDEmbeddedData::SetTempDirPath</span></span>  
  
```  
HRESULT SetTempDirPath (  
    [in] BSTR in_bstrPath  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c52da-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52da-169">Description</span></span>  
 <span data-ttu-id="c52da-170">Establezca la ruta de acceso a los archivos temporales que usa la aplicación de incrustación.</span><span class="sxs-lookup"><span data-stu-id="c52da-170">Set the path to temporary files used by the embedding application.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c52da-171">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c52da-171">Parameters</span></span>  
 <span data-ttu-id="c52da-172">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="c52da-172">*in_bstrPath*</span></span>  
 <span data-ttu-id="c52da-173">Ruta de acceso que usa la aplicación host para los archivos temporales.</span><span class="sxs-lookup"><span data-stu-id="c52da-173">The path used by the host application for temporary files.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c52da-174">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c52da-174">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c52da-175">El directorio de archivo temporal se estableció correctamente.</span><span class="sxs-lookup"><span data-stu-id="c52da-175">The temporary file directory was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c52da-176">Se produjo un error al establecer la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c52da-176">An error occurred while setting the path.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="c52da-177">Source</span><span class="sxs-lookup"><span data-stu-id="c52da-177">Source</span></span>  
  
```  
[id(4), helpstring("Set the path used by the host application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
```  
  
### <a name="imdembeddeddatacancel"></a><span data-ttu-id="c52da-178">IMDEmbeddedData::Cancel</span><span class="sxs-lookup"><span data-stu-id="c52da-178">IMDEmbeddedData::Cancel</span></span>  
  
```  
HRESULT Cancel ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="c52da-179">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52da-179">Description</span></span>  
 <span data-ttu-id="c52da-180">Cancela la operación de base de datos incrustada actual</span><span class="sxs-lookup"><span data-stu-id="c52da-180">Cancels the current embedded database operation</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c52da-181">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c52da-181">Parameters</span></span>  
 <span data-ttu-id="c52da-182">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c52da-182">None.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c52da-183">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c52da-183">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c52da-184">La operación se canceló correctamente.</span><span class="sxs-lookup"><span data-stu-id="c52da-184">The operation was successfully cancelled.</span></span>  
  
 `DB_E_CANTCANCEL`  
 <span data-ttu-id="c52da-185">No hay ninguna operación cancelable actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="c52da-185">No cancellable operation is currently in progress.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c52da-186">Se produjo un error al cancelar la operación incrustada.</span><span class="sxs-lookup"><span data-stu-id="c52da-186">An error occurred while cancelling the embedded operation.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="c52da-187">Source</span><span class="sxs-lookup"><span data-stu-id="c52da-187">Source</span></span>  
  
```  
[id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
```  
  
### <a name="imdembeddeddatagetsizemax-ipersiststreamgetsizemax"></a><span data-ttu-id="c52da-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span><span class="sxs-lookup"><span data-stu-id="c52da-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span></span>  
  
```  
HRESULT GetSizeMax (  
    [out] ULARGE_INTEGER * out_pcbSize  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c52da-189">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52da-189">Description</span></span>  
 <span data-ttu-id="c52da-190">Obtiene el tamaño calculado (en bytes) del flujo para guardar el objeto incrustado.</span><span class="sxs-lookup"><span data-stu-id="c52da-190">Gets the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="c52da-191">Se hereda de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c52da-191">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c52da-192">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c52da-192">Parameters</span></span>  
 <span data-ttu-id="c52da-193">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="c52da-193">*in_bstrPath*</span></span>  
 <span data-ttu-id="c52da-194">Tamaño calculado (en bytes) de la imagen de la base de datos incrustada.</span><span class="sxs-lookup"><span data-stu-id="c52da-194">The estimated size (in bytes) of the embedded database image.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="c52da-195">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c52da-195">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="c52da-196">El tamaño se obtuvo correctamente.</span><span class="sxs-lookup"><span data-stu-id="c52da-196">The size was successfully obtained.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c52da-197">Se produjo un error al obtener el tamaño.</span><span class="sxs-lookup"><span data-stu-id="c52da-197">An error occurred while obtaining the size.</span></span>  
  
### <a name="imdembeddeddataisdirty-ipersiststreamisdirty"></a><span data-ttu-id="c52da-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span><span class="sxs-lookup"><span data-stu-id="c52da-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span></span>  
  
```  
HRESULT IsDirty ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="c52da-199">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52da-199">Description</span></span>  
 <span data-ttu-id="c52da-200">Comprueba si la base de datos incrustada ha cambiado desde que se guardó por última vez.</span><span class="sxs-lookup"><span data-stu-id="c52da-200">Verifies if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="c52da-201">Se hereda de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c52da-201">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c52da-202">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c52da-202">Parameters</span></span>  
 <span data-ttu-id="c52da-203">ninguno</span><span class="sxs-lookup"><span data-stu-id="c52da-203">none</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="c52da-204">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="c52da-204">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="c52da-205">La base de datos ha cambiado desde que se guardó por última vez.</span><span class="sxs-lookup"><span data-stu-id="c52da-205">The database has changed since it was last saved.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="c52da-206">La base de datos no ha cambiado desde que se guardó por última vez.</span><span class="sxs-lookup"><span data-stu-id="c52da-206">The database has not changed since it was last saved.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c52da-207">Se produjo un error al obtener el estado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c52da-207">An error occurred while obtaining the database state.</span></span>  
  
### <a name="imdembeddeddataload-ipersiststreamload"></a><span data-ttu-id="c52da-208">IMDEmbeddedData::Load (IPersistStream::Load)</span><span class="sxs-lookup"><span data-stu-id="c52da-208">IMDEmbeddedData::Load (IPersistStream::Load)</span></span>  
  
```  
HRESULT Load (   
    [in] IStream * in_pStm   
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c52da-209">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52da-209">Description</span></span>  
 <span data-ttu-id="c52da-210">Carga la base de datos incrustada en el motor local o en proceso.</span><span class="sxs-lookup"><span data-stu-id="c52da-210">Loads the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="c52da-211">Se hereda de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c52da-211">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c52da-212">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c52da-212">Parameters</span></span>  
 <span data-ttu-id="c52da-213">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="c52da-213">*in_pStm*</span></span>  
 <span data-ttu-id="c52da-214">Puntero a una interfaz de flujo desde donde cargar la base de datos incrustada.</span><span class="sxs-lookup"><span data-stu-id="c52da-214">A pointer to a stream interface from where to load the embedded database.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="c52da-215">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="c52da-215">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="c52da-216">La base de datos se cargó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c52da-216">The database was successfully loaded.</span></span>  
  
 `E_OUTOFMEMORY`  
 <span data-ttu-id="c52da-217">No hay suficiente memoria para cargar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c52da-217">Not enough memory to load the database.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="c52da-218">Se produjo un error al cargar la base de datos, diferente de `E_OUTOFMEMORY`.</span><span class="sxs-lookup"><span data-stu-id="c52da-218">An error occurred while loading the database, different than `E_OUTOFMEMORY`.</span></span>  
  
### <a name="imdembeddeddatasave-ipersiststreamsave"></a><span data-ttu-id="c52da-219">IMDEmbeddedData::Save (IPersistStream::Save)</span><span class="sxs-lookup"><span data-stu-id="c52da-219">IMDEmbeddedData::Save (IPersistStream::Save)</span></span>  
  
```  
HRESULT Save (   
    [in] IStream * in_pStm,  
    [in] BOOL in_fClearDirty  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="c52da-220">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52da-220">Description</span></span>  
 <span data-ttu-id="c52da-221">Guarda la base de datos local o en proceso en el flujo incrustado en el documento contenedor.</span><span class="sxs-lookup"><span data-stu-id="c52da-221">Saves the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="c52da-222">Se hereda de `IPersistStream`.</span><span class="sxs-lookup"><span data-stu-id="c52da-222">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="c52da-223">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c52da-223">Parameters</span></span>  
 <span data-ttu-id="c52da-224">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="c52da-224">*in_pStm*</span></span>  
 <span data-ttu-id="c52da-225">Puntero a una interfaz de flujo donde guardar la base de datos incrustada.</span><span class="sxs-lookup"><span data-stu-id="c52da-225">A pointer to a stream interface to where to save the embedded database.</span></span>  
  
 <span data-ttu-id="c52da-226">*in_fClearDirty*</span><span class="sxs-lookup"><span data-stu-id="c52da-226">*in_fClearDirty*</span></span>  
 <span data-ttu-id="c52da-227">Marca que indica si la marca modificada se debería borrar después de esta operación.</span><span class="sxs-lookup"><span data-stu-id="c52da-227">A flag that indicates whether the dirty flag should be cleared after this operation.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="c52da-228">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="c52da-228">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="c52da-229">La base de datos se guardó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c52da-229">The database was successfully saved.</span></span>  
  
 `STG_E_CANTSAVE`  
 <span data-ttu-id="c52da-230">Se produjo un error al guardar la base de datos, diferente de `STG_E_MEDIUMFULL`.</span><span class="sxs-lookup"><span data-stu-id="c52da-230">An error occurred while saving the database, different than `STG_E_MEDIUMFULL`.</span></span>  
  
 `STG_E_MEDIUMFULL`  
 <span data-ttu-id="c52da-231">La base de datos no se pudo guardar porque no queda ningún espacio en el dispositivo de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="c52da-231">The database could not be saved because there is no space left on the storage device.</span></span>  
  
  
