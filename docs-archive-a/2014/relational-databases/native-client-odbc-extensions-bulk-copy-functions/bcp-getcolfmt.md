---
title: bcp_getcolfmt | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_getcolfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_getcolfmt function
ms.assetid: f8bdada5-7b2d-4475-8c98-f93e9d77b130
author: rothja
ms.author: jroth
ms.openlocfilehash: aabc811a5aa0babe5119c4ef0ed0e649586d73cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671055"
---
# <a name="bcp_getcolfmt"></a><span data-ttu-id="da4fa-102">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="da4fa-102">bcp_getcolfmt</span></span>
  <span data-ttu-id="da4fa-103">Se utiliza para buscar el valor de propiedad del formato de columna.</span><span class="sxs-lookup"><span data-stu-id="da4fa-103">Used to find the column format property value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da4fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da4fa-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_getcolfmt (  
HDBC   
hdbc  
,  
INT   
field  
,  
INT   
property  
,  
void*   
pValue  
,  
INT   
cbvalue,  
INT*   
pcbLen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="da4fa-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="da4fa-105">Arguments</span></span>  
 <span data-ttu-id="da4fa-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="da4fa-106">*hdbc*</span></span>  
 <span data-ttu-id="da4fa-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="da4fa-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="da4fa-108">*campo*</span><span class="sxs-lookup"><span data-stu-id="da4fa-108">*field*</span></span>  
 <span data-ttu-id="da4fa-109">Es el número de columnas para las que se recupera la propiedad.</span><span class="sxs-lookup"><span data-stu-id="da4fa-109">Is the column number for which the property is retrieved.</span></span>  
  
 <span data-ttu-id="da4fa-110">*property*</span><span class="sxs-lookup"><span data-stu-id="da4fa-110">*property*</span></span>  
 <span data-ttu-id="da4fa-111">Es una de las constantes de propiedad.</span><span class="sxs-lookup"><span data-stu-id="da4fa-111">Is one of the property constants.</span></span>  
  
 <span data-ttu-id="da4fa-112">*pValue*</span><span class="sxs-lookup"><span data-stu-id="da4fa-112">*pValue*</span></span>  
 <span data-ttu-id="da4fa-113">Es el puntero al búfer del que se recupera el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="da4fa-113">Is the pointer to the buffer from which to retrieve the property value.</span></span>  
  
 <span data-ttu-id="da4fa-114">*cbValue*</span><span class="sxs-lookup"><span data-stu-id="da4fa-114">*cbValue*</span></span>  
 <span data-ttu-id="da4fa-115">Es la longitud del búfer de propiedad en bytes.</span><span class="sxs-lookup"><span data-stu-id="da4fa-115">Is the length of the property buffer in bytes.</span></span>  
  
 <span data-ttu-id="da4fa-116">*pcbLen*</span><span class="sxs-lookup"><span data-stu-id="da4fa-116">*pcbLen*</span></span>  
 <span data-ttu-id="da4fa-117">Puntero a la longitud de los datos que se devuelven en el búfer de propiedad.</span><span class="sxs-lookup"><span data-stu-id="da4fa-117">Pointer to length of the data that is being returned in the property buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="da4fa-118">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="da4fa-118">Returns</span></span>  
 <span data-ttu-id="da4fa-119">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="da4fa-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da4fa-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="da4fa-120">Remarks</span></span>  
 <span data-ttu-id="da4fa-121">Los valores de propiedad del formato de columna se muestran en el tema [bcp_setcolfmt](bcp-setcolfmt.md) .</span><span class="sxs-lookup"><span data-stu-id="da4fa-121">Column format property values are listed in the [bcp_setcolfmt](bcp-setcolfmt.md) topic.</span></span> <span data-ttu-id="da4fa-122">Los valores de propiedad del formato de columna se establecen llamando a la función **bcp_setcolfmt** , y se utiliza la función **bcp_getcolfmt** para buscar el valor de propiedad del formato de columna.</span><span class="sxs-lookup"><span data-stu-id="da4fa-122">The column format property values are set by calling the **bcp_setcolfmt** function, and the **bcp_getcolfmt** function is used to find the column format property value.</span></span>  
  
 <span data-ttu-id="da4fa-123">Los cambios de comportamiento pueden observarse al establecer conexión con un equipo servidor de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (o versiones posteriores) en comparación con versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da4fa-123">Behavior changes may be observed when connecting to a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (or later) server computer, compared to earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions.</span></span> <span data-ttu-id="da4fa-124">Para obtener más información, vea [Detección de metadatos](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="da4fa-124">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="bcp_getcolfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="da4fa-125">bcp_getcolfmt admite las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="da4fa-125">bcp_getcolfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="da4fa-126">Los tipos utilizados con la `BCP_FMT_TYPE` propiedad para los tipos de fecha y hora se especifican en [cambios de copia masiva para los tipos de fecha y hora mejorados &#40;OLE DB y&#41;ODBC ](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="da4fa-126">The types used with the `BCP_FMT_TYPE` property for date/time types are as specified in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="da4fa-127">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="da4fa-127">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4fa-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da4fa-128">See Also</span></span>  
 [<span data-ttu-id="da4fa-129">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="da4fa-129">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
