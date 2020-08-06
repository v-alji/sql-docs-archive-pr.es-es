---
title: Propiedad UnattendedExecutionAccount (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- UnattendedExecutionAccount
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- UnattendedExecutionAccount property
ms.assetid: ab5203ba-c01e-4020-8619-ee290cf9da07
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f032cd8a9e8d5305f4eef82f815b4f0e328756a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748532"
---
# <a name="unattendedexecutionaccount-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="06d1c-102">Propiedad UnattendedExecutionAccount (MSReportServer_ConfigurationSetting de WMI)</span><span class="sxs-lookup"><span data-stu-id="06d1c-102">UnattendedExecutionAccount Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="06d1c-103">Devuelve la cuenta de usuario que el servidor de informes suplanta al realizar la ejecución desatendida de informes.</span><span class="sxs-lookup"><span data-stu-id="06d1c-103">Returns the user account that the report server impersonates when running reports unattended.</span></span> <span data-ttu-id="06d1c-104">Solo lectura.</span><span class="sxs-lookup"><span data-stu-id="06d1c-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d1c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06d1c-105">Syntax</span></span>  
  
```vb  
Public Dim UnattendedExecutionAccount As String  
```  
  
```csharp  
public string UnattendedExecutionAccount;  
```  
  
## <a name="property-values"></a><span data-ttu-id="06d1c-106">Valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="06d1c-106">Property Values</span></span>  
 <span data-ttu-id="06d1c-107">Un objeto `String` que representa el nombre de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="06d1c-107">A `String` object that represents the account name.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="06d1c-108">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="06d1c-108">Example Code</span></span>  
 [<span data-ttu-id="06d1c-109">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="06d1c-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="06d1c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06d1c-110">Requirements</span></span>  
 <span data-ttu-id="06d1c-111">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06d1c-111">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d1c-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06d1c-112">See Also</span></span>  
 [<span data-ttu-id="06d1c-113">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="06d1c-113">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  