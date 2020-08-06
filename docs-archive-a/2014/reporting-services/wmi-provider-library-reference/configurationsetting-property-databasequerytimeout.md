---
title: Propiedad DatabaseQueryTimeout (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseQueryTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseQueryTimeout property
ms.assetid: 96faed97-9799-4bbf-a66f-fdd532d3eace
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e92e3e0f6752ea99fe89c962ebe96e343c0195b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748549"
---
# <a name="databasequerytimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="1743a-102">Propiedad DatabaseQueryTimeout (MSReportServer_ConfigurationSetting de WMI)</span><span class="sxs-lookup"><span data-stu-id="1743a-102">DatabaseQueryTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="1743a-103">Especifica el número de segundos que deben transcurrir antes de que el servidor de informes asuma un error del comando o que necesita demasiado tiempo para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="1743a-103">Specifies the number of seconds that must elapse before the report server assumes the command failed or took too much time to perform.</span></span> <span data-ttu-id="1743a-104">El servidor de informes ajusta el tiempo de la consulta con respecto al catálogo de SQL, no a un origen de datos para el informe.</span><span class="sxs-lookup"><span data-stu-id="1743a-104">The report server is timing the querying against the SQL catalog, not a data source for the report.</span></span> <span data-ttu-id="1743a-105">Lectura/escritura</span><span class="sxs-lookup"><span data-stu-id="1743a-105">Read/write.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1743a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1743a-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseQueryTimeout As UInt32  
```  
  
```csharp  
public UInt32 DatabaseQueryTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="1743a-107">Valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="1743a-107">Property Values</span></span>  
 <span data-ttu-id="1743a-108">Un objeto `integer` de 32 bits sin signo que representa el número de segundos en que puede ejecutarse la consulta.</span><span class="sxs-lookup"><span data-stu-id="1743a-108">A 32-bit unsigned `integer` object that represents the number of seconds that the query is allowed to run.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="1743a-109">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1743a-109">Example Code</span></span>  
 [<span data-ttu-id="1743a-110">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1743a-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="1743a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1743a-111">Requirements</span></span>  
 <span data-ttu-id="1743a-112">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1743a-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1743a-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1743a-113">See Also</span></span>  
 [<span data-ttu-id="1743a-114">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1743a-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
