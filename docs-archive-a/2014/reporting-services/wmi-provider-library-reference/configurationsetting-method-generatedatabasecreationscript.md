---
title: Método GenerateDatabaseCreationScript (MSReportServer_ConfigurationSetting WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseCreationScript method
ms.assetid: 25232dc7-00fe-4cd1-8a1c-7e36d552de00
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e798aa25bec1cc478a6ec2cbdd0c21f44fa8215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671913"
---
# <a name="generatedatabasecreationscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="cd7ad-102">Método GenerateDatabaseCreationScript (MSReportServer_ConfigurationSetting de WMI)</span><span class="sxs-lookup"><span data-stu-id="cd7ad-102">GenerateDatabaseCreationScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="cd7ad-103">Genera un script SQL que se puede utilizar para crear una base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-103">Generates a SQL Script that can be used to create a report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd7ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd7ad-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseCreationScript(ByVal DatabaseName As String, _  
    ByVal Lcid As Int32, ByVal IsSharePointMode As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseCreationScript(string DatabaseName, Int32 Lcid,   
    Boolean IsSharePointMode, out string Script, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd7ad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd7ad-105">Parameters</span></span>  
 <span data-ttu-id="cd7ad-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="cd7ad-106">*Databasename*</span></span>  
 <span data-ttu-id="cd7ad-107">Cadena que contiene el nombre de la base de datos del servidor de informes que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-107">A string containing the name of the report server database to create.</span></span>  
  
 <span data-ttu-id="cd7ad-108">*Lcid*</span><span class="sxs-lookup"><span data-stu-id="cd7ad-108">*Lcid*</span></span>  
 <span data-ttu-id="cd7ad-109">Valor usado para la localización de nombres de roles.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-109">Value used for localization of role names.</span></span>  
  
 <span data-ttu-id="cd7ad-110">*IsSharePointMode*</span><span class="sxs-lookup"><span data-stu-id="cd7ad-110">*IsSharePointMode*</span></span>  
 <span data-ttu-id="cd7ad-111">Indica si se desea crear la base de datos en modo nativo o en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-111">Indicates whether to create database in native mode or SharePoint mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cd7ad-112">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , *IsSharePointMode* = `True` no se admite porque en modo de SharePoint [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] es un servicio compartido de SharePoint y no está controlado por el proveedor WMI.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-112">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], *IsSharePointMode*=`True` is not supported because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is a SharePoint shared service and is not controlled by the WMI provider.</span></span> <span data-ttu-id="cd7ad-113">Este parámetro siempre debe establecerse en `False`.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-113">You should always set this parameter to `False`.</span></span>  
  
 <span data-ttu-id="cd7ad-114">*Script*</span><span class="sxs-lookup"><span data-stu-id="cd7ad-114">*Script*</span></span>  
 <span data-ttu-id="cd7ad-115">[out] Cadena que contiene el script SQL generado.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-115">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="cd7ad-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="cd7ad-116">*HRESULT*</span></span>  
 <span data-ttu-id="cd7ad-117">[out] Valor que indica si la llamada se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd7ad-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cd7ad-118">Return Value</span></span>  
 <span data-ttu-id="cd7ad-119">Devuelve *HRESULT* que indica si la llamada al método se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="cd7ad-120">Un valor de 0 indica que la llamada al método se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-120">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="cd7ad-121">Un valor distinto de cero indica que se ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-121">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd7ad-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cd7ad-122">Remarks</span></span>  
 <span data-ttu-id="cd7ad-123">Este método genera un script SQL que crea bases de datos del servidor de informes para la versión del servidor de informes al que se está conectado actualmente.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-123">This method generates an SQL script that creates report server databases for the version of the report server currently connected to.</span></span>  
  
 <span data-ttu-id="cd7ad-124">El valor proporcionado en el parámetro *DatabaseName* debe cumplir las convenciones de nomenclatura de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd7ad-124">The value supplied in the *DatabaseName* parameter must conform to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database naming conventions.</span></span>  
  
 <span data-ttu-id="cd7ad-125">El método no comprueba la existencia de la base de datos al generar el script.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-125">The method does not check the existence of the database when generating the script.</span></span>  
  
 <span data-ttu-id="cd7ad-126">Este método no comprueba la existencia de la base de datos del servidor de informes al generar el script.</span><span class="sxs-lookup"><span data-stu-id="cd7ad-126">This method does not check for the existence of the report server database when generating the script.</span></span>  
  
 <span data-ttu-id="cd7ad-127">El script generado admite [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 y [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd7ad-127">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd7ad-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd7ad-128">Requirements</span></span>  
 <span data-ttu-id="cd7ad-129">**Espacio de nombres:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd7ad-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7ad-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd7ad-130">See Also</span></span>  
 [<span data-ttu-id="cd7ad-131">Miembros MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="cd7ad-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
