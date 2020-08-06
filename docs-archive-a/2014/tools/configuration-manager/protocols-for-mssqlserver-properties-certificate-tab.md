---
title: Propiedades de Protocolos de MSSQLSERVER (pestaña Certificado) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.computermgr.cert.general.f1
helpviewer_keywords:
- MSSQLSERVER property protocols
ms.assetid: 776addd6-25f3-4875-9a71-064035787090
author: stevestein
ms.author: sstein
ms.openlocfilehash: 020d33eba7621f877f8622ca89dbd26a071f16a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748429"
---
# <a name="protocols-for-mssqlserver-properties-certificate-tab"></a><span data-ttu-id="90d3a-102">Propiedades de Protocolos de MSSQLSERVER (pestaña Certificado)</span><span class="sxs-lookup"><span data-stu-id="90d3a-102">Protocols for MSSQLSERVER Properties (Certificate Tab)</span></span>
  <span data-ttu-id="90d3a-103">Utilice la pestaña **Certificado** del cuadro de diálogo **Propiedades de Protocolos de MSSQLSERVER** para seleccionar un certificado para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]o ver las propiedades de un certificado.</span><span class="sxs-lookup"><span data-stu-id="90d3a-103">Use the **Certificate** tab on the **Protocols for MSSQLSERVER Properties** dialog box to select a certificate for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or to view the properties of a certificate.</span></span> <span data-ttu-id="90d3a-104">Todos los campos están en blanco hasta que se selecciona un certificado.</span><span class="sxs-lookup"><span data-stu-id="90d3a-104">All fields are blank until a certificate is selected.</span></span>  
  
 <span data-ttu-id="90d3a-105">Los certificados se almacenan localmente para los usuarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="90d3a-105">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="90d3a-106">Para cargar un certificado que se va a utilizar en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], debe ejecutar el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con la misma cuenta de usuario que el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="90d3a-106">To load a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="90d3a-107">Encabezado de página</span><span class="sxs-lookup"><span data-stu-id="90d3a-107">Page Header</span></span>  
 <span data-ttu-id="90d3a-108">**Vista**</span><span class="sxs-lookup"><span data-stu-id="90d3a-108">**View**</span></span>  
 <span data-ttu-id="90d3a-109">Proporciona acceso a detalles adicionales acerca del certificado.</span><span class="sxs-lookup"><span data-stu-id="90d3a-109">Provides access to additional details on the certificate.</span></span> <span data-ttu-id="90d3a-110">No está disponible hasta que se selecciona un certificado en el cuadro **Certificado** .</span><span class="sxs-lookup"><span data-stu-id="90d3a-110">Not available until a certificate is selected in the **Certificate** box.</span></span> <span data-ttu-id="90d3a-111">Para obtener información adicional acerca de los detalles del certificado, vea la documentación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="90d3a-111">For additional information on certificate details, see your [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
 <span data-ttu-id="90d3a-112">**Borrar**</span><span class="sxs-lookup"><span data-stu-id="90d3a-112">**Clear**</span></span>  
 <span data-ttu-id="90d3a-113">Quita la selección del cuadro **Certificado** .</span><span class="sxs-lookup"><span data-stu-id="90d3a-113">Removes the selection from the **Certificate** box.</span></span>  
  
 <span data-ttu-id="90d3a-114">**Certificate**</span><span class="sxs-lookup"><span data-stu-id="90d3a-114">**Certificate**</span></span>  
 <span data-ttu-id="90d3a-115">Nombre del certificado determinado por el proveedor de seguridad.</span><span class="sxs-lookup"><span data-stu-id="90d3a-115">Name of certificate as determined by security provider.</span></span> <span data-ttu-id="90d3a-116">Seleccione un certificado para ver los detalles en la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="90d3a-116">Select a certificate to see the details in the properties grid.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90d3a-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="90d3a-117">Options</span></span>  
 <span data-ttu-id="90d3a-118">Fecha de expiración</span><span class="sxs-lookup"><span data-stu-id="90d3a-118">Expiration Date</span></span>  
 <span data-ttu-id="90d3a-119">Fecha final del período de validez del certificado.</span><span class="sxs-lookup"><span data-stu-id="90d3a-119">The final date for the period in which the certificate is valid.</span></span>  
  
 <span data-ttu-id="90d3a-120">Nombre descriptivo</span><span class="sxs-lookup"><span data-stu-id="90d3a-120">Friendly Name</span></span>  
 <span data-ttu-id="90d3a-121">Nombre descriptivo o común para la persona o entidad de certificación a la que se emite el certificado.</span><span class="sxs-lookup"><span data-stu-id="90d3a-121">A friendly or common name for the individual or certification authority to whom the certificate is issued.</span></span>  
  
 <span data-ttu-id="90d3a-122">Emitido por</span><span class="sxs-lookup"><span data-stu-id="90d3a-122">Issued By</span></span>  
 <span data-ttu-id="90d3a-123">Información relativa a la entidad de certificación que ha emitido el certificado.</span><span class="sxs-lookup"><span data-stu-id="90d3a-123">Information regarding the certification authority that issued the certificate.</span></span>  
  
 <span data-ttu-id="90d3a-124">Emitido a</span><span class="sxs-lookup"><span data-stu-id="90d3a-124">Issued To</span></span>  
 <span data-ttu-id="90d3a-125">Información relativa al destinatario del certificado.</span><span class="sxs-lookup"><span data-stu-id="90d3a-125">Information regarding the recipient of the certificate.</span></span>  
  
  
