---
title: Método GenerateDatabaseUpgradeScript (MSReportServer_ConfigurationSetting de WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseUpgradeScript method
ms.assetid: 88534e8e-2877-41cd-b5c2-b1d33a0fd203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a619584b9f1cc095f8f624670386d388426e4a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671910"
---
# <a name="generatedatabaseupgradescript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="f70b7-102">Método GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="f70b7-102">GenerateDatabaseUpgradeScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="f70b7-103">Genera un script que se puede utilizar para actualizar la base de datos del servidor de informes al esquema de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f70b7-103">Generates a script that can be used to upgrade the report server database to the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f70b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f70b7-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseUpgradeScript(DatabaseName as String, _  
    ServerVersion as String, ByRef Script as String, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GenerateDatabaseUpgradeScript (string DatabaseName,   
    string ServerVersion, out string Script,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f70b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f70b7-105">Parameters</span></span>  
 <span data-ttu-id="f70b7-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="f70b7-106">*Databasename*</span></span>  
 <span data-ttu-id="f70b7-107">Cadena que contiene el nombre de la base de datos del servidor de informes que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="f70b7-107">A string containing the name of the report server database to upgrade.</span></span>  
  
 <span data-ttu-id="f70b7-108">*ServerVersion*</span><span class="sxs-lookup"><span data-stu-id="f70b7-108">*ServerVersion*</span></span>  
 <span data-ttu-id="f70b7-109">Cadena que contiene la versión del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="f70b7-109">A string containing the version of the report server.</span></span>  
  
 <span data-ttu-id="f70b7-110">*Script*</span><span class="sxs-lookup"><span data-stu-id="f70b7-110">*Script*</span></span>  
 <span data-ttu-id="f70b7-111">[out] Cadena que contiene el script SQL generado.</span><span class="sxs-lookup"><span data-stu-id="f70b7-111">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="f70b7-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="f70b7-112">*HRESULT*</span></span>  
 <span data-ttu-id="f70b7-113">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="f70b7-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f70b7-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f70b7-114">Return Value</span></span>  
 <span data-ttu-id="f70b7-115">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="f70b7-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="f70b7-116">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f70b7-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="f70b7-117">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="f70b7-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f70b7-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f70b7-118">Remarks</span></span>  
 <span data-ttu-id="f70b7-119">El script generado admite [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]y [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f70b7-119">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f70b7-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f70b7-120">Requirements</span></span>  
 <span data-ttu-id="f70b7-121">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f70b7-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70b7-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f70b7-122">See Also</span></span>  
 [<span data-ttu-id="f70b7-123">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="f70b7-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
