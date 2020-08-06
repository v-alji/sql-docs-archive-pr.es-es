---
title: Propiedad ConnectionPoolSize (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ConnectionPoolSize
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ConnectionPoolSize property
ms.assetid: b80c8e5d-b725-4fe4-aec6-02fb18ec4434
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 24a180fde90ff406d40a0f0c89bf82dfe5138b88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748557"
---
# <a name="connectionpoolsize-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="360cc-102">Propiedad ConnectionPoolSize (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="360cc-102">ConnectionPoolSize Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="360cc-103">Tamaño de grupo de conexiones utilizado por el servidor de informes para comunicarse con la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="360cc-103">The connection pool size used by the report server to communicate with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that hosts the report server database.</span></span> <span data-ttu-id="360cc-104">Solo lectura.</span><span class="sxs-lookup"><span data-stu-id="360cc-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="360cc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="360cc-105">Syntax</span></span>  
  
```vb  
Public Dim ConnectionPoolSize As UInt32  
```  
  
```csharp  
public UInt32 ConnectionPoolSize;  
```  
  
## <a name="property-values"></a><span data-ttu-id="360cc-106">Valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="360cc-106">Property Values</span></span>  
 <span data-ttu-id="360cc-107">Un objeto **Integer** de solo lectura que devuelve un valor de `768` .</span><span class="sxs-lookup"><span data-stu-id="360cc-107">A read-only **integer** object that returns a value of `768`.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="360cc-108">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="360cc-108">Example Code</span></span>  
 [<span data-ttu-id="360cc-109">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="360cc-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="360cc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="360cc-110">Requirements</span></span>  
 <span data-ttu-id="360cc-111">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="360cc-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="360cc-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="360cc-112">See Also</span></span>  
 [<span data-ttu-id="360cc-113">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="360cc-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
