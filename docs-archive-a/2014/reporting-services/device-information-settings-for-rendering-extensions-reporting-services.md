---
title: Configuración de información de dispositivos para las extensiones de representación (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 947b0ee1-bb35-4b4e-9527-dc501566e7d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f15e27e01cd43bafda3aede3deca7729f2c89756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747499"
---
# <a name="device-information-settings-for-rendering-extensions-reporting-services"></a><span data-ttu-id="d5fa5-102">Configuración de información de dispositivos para las extensiones de representación (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="d5fa5-102">Device Information Settings for Rendering Extensions (Reporting Services)</span></span>
  <span data-ttu-id="d5fa5-103">En [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], la configuración de información de dispositivos se utiliza para pasar los parámetros de representación a una extensión de representación.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-103">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="d5fa5-104">Cada extensión de representación acepta un conjunto de valores específico.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-104">Each rendering extension accepts a specific set of settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5fa5-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5fa5-105">In This Section</span></span>  
  
|<span data-ttu-id="d5fa5-106">Tema</span><span class="sxs-lookup"><span data-stu-id="d5fa5-106">Topic</span></span>|<span data-ttu-id="d5fa5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5fa5-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d5fa5-108">Configuración de la información del dispositivo ATOM</span><span class="sxs-lookup"><span data-stu-id="d5fa5-108">ATOM Device Information Settings</span></span>](../../2014/reporting-services/atom-device-information-settings.md)|<span data-ttu-id="d5fa5-109">Describe la configuración de información de dispositivos asociada a una salida de representación compatible con Atom.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-109">Describes the device information settings that are associated with Atom compliant rendering output.</span></span>|  
|[<span data-ttu-id="d5fa5-110">Configuración de la información del dispositivo CSV</span><span class="sxs-lookup"><span data-stu-id="d5fa5-110">CSV Device Information Settings</span></span>](csv-device-information-settings.md)|<span data-ttu-id="d5fa5-111">Describe la configuración de información de dispositivos asociada a una salida de representación CSV.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-111">Describes the device information settings that are associated with CSV rendering output.</span></span>|  
|[<span data-ttu-id="d5fa5-112">Configuración de la información del dispositivo Excel</span><span class="sxs-lookup"><span data-stu-id="d5fa5-112">Excel Device Information Settings</span></span>](excel-device-information-settings.md)|<span data-ttu-id="d5fa5-113">Describe la configuración de información de dispositivos asociada a una salida de representación de Excel.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-113">Describes the device information settings that are associated with Excel rendering output.</span></span>|  
|[<span data-ttu-id="d5fa5-114">Configuración de la información del dispositivo web</span><span class="sxs-lookup"><span data-stu-id="d5fa5-114">Word Device Information Settings</span></span>](word-device-information-settings.md)|<span data-ttu-id="d5fa5-115">Describe la configuración de información de dispositivos asociada a una salida de representación de Word.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-115">Describes the device information settings that are associated with Word rendering output.</span></span>|  
|[<span data-ttu-id="d5fa5-116">Configuración de la información del dispositivo HTML</span><span class="sxs-lookup"><span data-stu-id="d5fa5-116">HTML Device Information Settings</span></span>](html-device-information-settings.md)|<span data-ttu-id="d5fa5-117">Describe la configuración de información de dispositivos asociada a una salida de representación HTML.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-117">Describes the device information settings that are associated with HTML rendering output.</span></span>|  
|[<span data-ttu-id="d5fa5-118">Configuración de la información del dispositivo de imagen</span><span class="sxs-lookup"><span data-stu-id="d5fa5-118">Image Device Information Settings</span></span>](image-device-information-settings.md)|<span data-ttu-id="d5fa5-119">Describe la configuración de información de dispositivos asociada a una salida de representación IMAGE.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-119">Describes the device information settings that are associated with IMAGE rendering output.</span></span>|  
|[<span data-ttu-id="d5fa5-120">Configuración de la información del dispositivo MHTML</span><span class="sxs-lookup"><span data-stu-id="d5fa5-120">MHTML Device Information Settings</span></span>](mhtml-device-information-settings.md)|<span data-ttu-id="d5fa5-121">Describe la configuración de información de dispositivos asociada a una salida de representación de MHTML.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-121">Describes the device information settings that are associated with MHTML rendering output.</span></span>|  
|[<span data-ttu-id="d5fa5-122">Configuración de la información del dispositivo PDF</span><span class="sxs-lookup"><span data-stu-id="d5fa5-122">PDF Device Information Settings</span></span>](pdf-device-information-settings.md)|<span data-ttu-id="d5fa5-123">Describe la configuración de información de dispositivos asociada a una salida de representación PDF.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-123">Describes the device information settings that are associated with PDF rendering output.</span></span>|  
|[<span data-ttu-id="d5fa5-124">Configuración de la información del dispositivo XML</span><span class="sxs-lookup"><span data-stu-id="d5fa5-124">XML Device Information Settings</span></span>](xml-device-information-settings.md)|<span data-ttu-id="d5fa5-125">Describe la configuración de información de dispositivos asociada a una salida de representación XML.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-125">Describes the device information settings that are associated with XML rendering output.</span></span>|  
|[<span data-ttu-id="d5fa5-126">Configuración de la información del dispositivo RGDI</span><span class="sxs-lookup"><span data-stu-id="d5fa5-126">RGDI Device Information Settings</span></span>](rgdi-device-information-settings.md)|<span data-ttu-id="d5fa5-127">Describe la configuración de información de dispositivos asociada a una salida de representación RGDI.</span><span class="sxs-lookup"><span data-stu-id="d5fa5-127">Describes the device information settings that are associated with RGDI rendering output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5fa5-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5fa5-128">See Also</span></span>  
 [<span data-ttu-id="d5fa5-129">Personalización de los parámetros de extensión de representación en RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="d5fa5-129">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>](customize-rendering-extension-parameters-in-rsreportserver-config.md)  
  
  
