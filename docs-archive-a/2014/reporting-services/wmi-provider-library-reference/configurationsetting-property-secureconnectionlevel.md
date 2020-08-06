---
title: Propiedad SecureConnectionLevel (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SecureConnectionLevel
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SecureConnectionLevel property
ms.assetid: fd5549e7-b874-41e2-866e-2f58caf6f733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5d1b3bccc8a7fee3899fa21208d83a718a33f5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748540"
---
# <a name="secureconnectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="49868-102">Propiedad SecureConnectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="49868-102">SecureConnectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="49868-103">Devuelve el nivel de conexión segura especificado en el archivo RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="49868-103">Returns the secure connection level specified in the RSReportServer.config file.</span></span> <span data-ttu-id="49868-104">Solo lectura.</span><span class="sxs-lookup"><span data-stu-id="49868-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49868-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49868-105">Syntax</span></span>  
  
```vb  
Public Dim SecureConnectionLevel As Integer  
```  
  
```csharp  
public Integer SecureConnectionLevel;  
```  
  
## <a name="property-values"></a><span data-ttu-id="49868-106">Valores de propiedad</span><span class="sxs-lookup"><span data-stu-id="49868-106">Property Values</span></span>  
 <span data-ttu-id="49868-107">`Integer`Valor que representa el nivel de conexión segura.</span><span class="sxs-lookup"><span data-stu-id="49868-107">An `Integer` value that represents the secure connection level.</span></span> <span data-ttu-id="49868-108">Los valores devueltos indican que el SSL está configurado o no.</span><span class="sxs-lookup"><span data-stu-id="49868-108">The return values indicate that the SSL is either configured or not.</span></span> <span data-ttu-id="49868-109">Un valor mayor o igual que 1 indica que SSL está activado.</span><span class="sxs-lookup"><span data-stu-id="49868-109">A value of greater than or equal to 1 indicates that SSL is turned on.</span></span> <span data-ttu-id="49868-110">El valor 0 indica que SSL está desactivado.</span><span class="sxs-lookup"><span data-stu-id="49868-110">A value of 0 indicates that SSL is turned off.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="49868-111">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="49868-111">Example Code</span></span>  
 [<span data-ttu-id="49868-112">Clase MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="49868-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="49868-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49868-113">Requirements</span></span>  
 <span data-ttu-id="49868-114">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49868-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49868-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49868-115">See Also</span></span>  
 [<span data-ttu-id="49868-116">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="49868-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
