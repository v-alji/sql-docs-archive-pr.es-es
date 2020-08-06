---
title: Editor del administrador de conexiones WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmiconnection.f1
helpviewer_keywords:
- WMI Connection Manager Editor
ms.assetid: 0ef2c913-0779-4a07-989e-3361cd83170b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e85cdd2157c8ebe4cb9e6b53f8c3b47ff102a7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676548"
---
# <a name="wmi-connection-manager-editor"></a><span data-ttu-id="38622-102">Editor del administrador de conexiones WMI</span><span class="sxs-lookup"><span data-stu-id="38622-102">WMI Connection Manager Editor</span></span>
  <span data-ttu-id="38622-103">Use el cuadro de diálogo **Administrador de conexiones WMI** para especificar una conexión del Instrumental de administración de Microsoft Windows (WMI) a un servidor.</span><span class="sxs-lookup"><span data-stu-id="38622-103">Use the **WMI Connection Manager** dialog box to specify a Microsoft Windows Management Instrumentation (WMI) connection to a server.</span></span>  
  
 <span data-ttu-id="38622-104">Para obtener más información acerca del administrador de conexiones WMI, vea [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="38622-104">To learn more about the WMI connection manager, see [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="38622-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="38622-105">Options</span></span>  
 <span data-ttu-id="38622-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="38622-106">**Name**</span></span>  
 <span data-ttu-id="38622-107">Proporcione un nombre único para el administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="38622-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="38622-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="38622-108">**Description**</span></span>  
 <span data-ttu-id="38622-109">Describa el administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="38622-109">Describe the connection manager.</span></span> <span data-ttu-id="38622-110">Como método recomendado, describa el administrador de conexiones desde el punto de vista de su propósito, para que los paquetes estén autodocumentados y sean más fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="38622-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="38622-111">**Nombre del servidor**</span><span class="sxs-lookup"><span data-stu-id="38622-111">**Server name**</span></span>  
 <span data-ttu-id="38622-112">Proporcione el nombre del servidor con el que desea realizar la conexión WMI.</span><span class="sxs-lookup"><span data-stu-id="38622-112">Provide the name of the server to which you want to make the WMI connection.</span></span>  
  
 <span data-ttu-id="38622-113">**Espacio de nombres**</span><span class="sxs-lookup"><span data-stu-id="38622-113">**Namespace**</span></span>  
 <span data-ttu-id="38622-114">Especifique el espacio de nombres WMI.</span><span class="sxs-lookup"><span data-stu-id="38622-114">Specify the WMI namespace.</span></span>  
  
 <span data-ttu-id="38622-115">**Usar autenticación de Windows**</span><span class="sxs-lookup"><span data-stu-id="38622-115">**Use Windows authentication**</span></span>  
 <span data-ttu-id="38622-116">Seleccione el uso de la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="38622-116">Select to use Windows Authentication.</span></span> <span data-ttu-id="38622-117">Si utiliza la autenticación de Windows, no será necesario que proporcione un nombre de usuario o una contraseña para la conexión.</span><span class="sxs-lookup"><span data-stu-id="38622-117">If you use Windows Authentication, you do not need to provide a user name or password for the connection.</span></span>  
  
 <span data-ttu-id="38622-118">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="38622-118">**User name**</span></span>  
 <span data-ttu-id="38622-119">Si no utiliza la autenticación de Windows, deberá proporcionar un nombre de usuario para la conexión.</span><span class="sxs-lookup"><span data-stu-id="38622-119">If you do not use Windows Authentication, you must provide a user name for the connection.</span></span>  
  
 <span data-ttu-id="38622-120">**Contraseña**</span><span class="sxs-lookup"><span data-stu-id="38622-120">**Password**</span></span>  
 <span data-ttu-id="38622-121">Si no utiliza la autenticación de Windows, deberá proporcionar la contraseña para la conexión.</span><span class="sxs-lookup"><span data-stu-id="38622-121">If you do not use Windows Authentication, you must provide the password for the connection.</span></span>  
  
 <span data-ttu-id="38622-122">**Test**</span><span class="sxs-lookup"><span data-stu-id="38622-122">**Test**</span></span>  
 <span data-ttu-id="38622-123">Permite probar la configuración del administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="38622-123">Test the connection manager settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38622-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38622-124">See Also</span></span>  
 <span data-ttu-id="38622-125">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="38622-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="38622-126">[Conceptos del proveedor WMI para la administración de configuración](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="38622-126">[WMI Provider for Configuration Management Concepts](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="38622-127">Conceptos del proveedor WMI para eventos de servidor</span><span class="sxs-lookup"><span data-stu-id="38622-127">WMI Provider for Server Events Concepts</span></span>](../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md)  
  
  
